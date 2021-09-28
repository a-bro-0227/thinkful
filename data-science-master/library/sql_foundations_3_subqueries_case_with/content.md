---
title: 'Using subqueries, CASE, and WITH'
author: Thinkful
team: grading
time: 120 minutes
uuid: 27e39661-36b6-42af-8727-6479a6e8dab0
timeHours: 2
---

In the previous modules, you gained proficiency with the bread and butter of data retrieval in SQL. There is a *lot* more to SQL than the handful of clauses that you've covered so far. Consider this checkpoint as an introduction to some of these more exotic SQL operations. This is not a comprehensive overview of everything that each tool can do. Instead, you'll walk through basic use cases for each, with some examples.

These are extra SQL topics that will not be evaluated in your SQL self-sufficiency exam. 

In this checkpoint, you'll continue working from the *employees* database on the Thinkful data science server. 

## Subqueries

A *subquery* is a query nested inside of another query. Usually, you will use it for some calculation or conditional logic that provides data to be used in the main part of the query. 

### Basic structure

The rules of a subquery's syntax are entirely the same as the rules for the rest of SQL. You simply nest the subquery by placing it in parentheses. 

```SQL
SELECT select_list
FROM table
-- Result of the subquery is used by the "outer query"
WHERE expr operator
-- Subquery - this executes once before the main query
  (SELECT select_list
  FROM table);
```

### Subquery indentation and SQL style

It is common to indent subqueries in SQL. This is purely stylistic, but it greatly improves reader usability. 

Indent lines with either tabs or spaces. Which should you use? There's a fierce debate over [programming with spaces versus tabs](https://www.businessinsider.com/tabs-vs-spaces-from-silicon-valley-2016-5); each approach has its pros and cons. Indenting with tabs is often easier because it requires fewer clicks, but spaces have the upper hand for cutting and pasting.

Whichever you choose, be consistent. And get opinions from people you are networking with in the industry—this is a great icebreaker to use with anyone interested in data science and coding! 

### Types of questions that subqueries can solve

Back to the task at hand. By nesting one query inside another (with indentation, because you're a coder who cares), subqueries help you answer two-part questions. An example is something like this:

"Who has a salary greater than Clark?"

You need to break this problem down into two parts: 

1. What is Clark's salary?
2. Which employees have a salary greater than Clark's salary?

To do this, you will place the result of the first query inside parentheses. That's your subquery. You will then use this as the basis for answering the second query—your outer query.

```SQL
-- Get the names of all employees with higher salaries than Clark's
-- Outer query—which employees have a greater salary than...
SELECT ename
FROM EMP
WHERE sal >
-- The salary assigned to Clark 
  (SELECT sal
  FROM emp
  WHERE empno = 7782);
```

Now, consider another example. This statement will return the names, job titles, and hire dates for all employees in the same department as Clark. 

```SQL
-- Select employee name, job title, hiredate of all employees
-- in the same department as Clark
SELECT ename, job, hiredate
FROM EMP
WHERE deptno =
-- Get Clark's department number
  (SELECT deptno
  FROM emp
  WHERE empno = 7782);
```

### Subqueries and `GROUP BY`

Imagine that you want to know the employee with the highest salary in each department. Using what you learned in previous modules, your answer might be something like the following:

```SQL
SELECT MAX(sal), deptno
FROM emp
GROUP BY deptno;
```

This statement returns the maximum salary for each department, but it doesn't give you the name of the employee. To do that, you need to break the problem into a subquery and outer query:

1. What is the maximum salary for each department number?
2. What is the name associated with each department's maximum salary?

Your query then becomes the following:

```SQL
SELECT ename, sal, deptno
FROM EMP
WHERE sal IN
  (SELECT MAX(sal)
  FROM emp
  GROUP BY deptno );
```

### Conditional subqueries: `ANY`, `ALL`, and so forth

You can also use subqueries to create conditional logic expressions. This is often done with the `ANY` and `ALL` operators, in conjunction with `WHERE`.

#### `ANY`

First, answer the following question: who are the employees with a salary greater than any individual clerk? To answer in SQL, you can break this question down by using a subquery in your statement, as shown below. This time, you'll use the `ANY` operator to conditionally filter your results.

```SQL
SELECT empno, ename, job, sal
FROM emp
WHERE sal > ANY
  (SELECT sal
  FROM emp
  WHERE job = 'CLERK' );
```

The results here might surprise you. Why do you have salaries of clerks in the results? Didn't you ask for salaries greater than any clerk's salary? Well, yes—but that doesn't exclude those salaries of *other* clerks. James, Adams, and Miller, who are all clerks, have salaries greater than Smith. So they are included in the results.

If that's not what you are looking for, you can filter these clerks out of the results with another conditional logic operator outside of the query, as shown below:

```SQL
SELECT empno, ename, job, sal
FROM emp
WHERE sal > ANY
  (SELECT sal
  FROM emp
  WHERE job = 'CLERK' )
AND job <> 'CLERK';
```

#### `ALL`

Now, take a look at the `ALL` operator. This time, your question is this: who are the employees with a salary greater than *all* of the clerks?

In plain English, the distinction between *any* and *all* in this question is trivial. But in SQL, it results in a completely different answer. To see why that is, consider the example below:

```SQL
SELECT empno, ename, job, sal
FROM emp
WHERE sal > ALL
  (SELECT sal
  FROM emp
  WHERE job = 'CLERK' );
```

In this case, you only get nine records back, and none of them are clerks. This query returned only the employees with a higher salary than each and every clerk. The clerk with the highest salary is Miller, at `1300`. So every result will have a salary greater than that. 

You've seen it before, and you'll see it again—the slightest change in a SQL statement can result in big differences. Often, these differences are excruciatingly difficult to describe in plain English. Generally, people use *any* and *all* in the same way to answer the above question. But SQL is not so ambiguous, so you need to be extra careful about the logic of your expressions.

Now, consider one more example. You want to get all employees who have a hire date before *all* of the managers:

```SQL
SELECT ename, job, hiredate
FROM emp
WHERE hiredate < ALL
 (SELECT hiredate
  FROM emp
  WHERE job = 'MANAGER' );
```

The hire date of the longest-tenured manager, Jones, is April 2, 1981. So the above query returns the employees with a hire date before then. 

What about with an `ANY` operator?

```SQL
SELECT ename, job, hiredate
FROM emp
WHERE hiredate < ANY
 (SELECT hiredate
  FROM emp
  WHERE job = 'MANAGER' );
```

This time, you get all records with a start date before that of any manager—including other managers.

## `CASE`

The `CASE` operator works similar to `IF`/`THEN` logic. You can use it to create temporary fields which help you aggregate the data. A basic `CASE` structure looks something like the example below: 

```SQL
CASE selector
  WHEN condition THEN statement
  WHEN condition THEN statement
  ELSE statement
END;
```
This is very common, for example, if you want to assign ordinal rankings to a field.

```SQL
SELECT empno, ename, sal,

-- Case statement: map conditions to values of the corresponding field
CASE
        WHEN sal >= 2000 THEN 'HIGH'
        WHEN sal BETWEEN 1000 AND 1999 THEN 'MEDIUM'
        ELSE 'LOW'
END

FROM emp;
```
Similarly to other calculated fields, you can assign an alias to your `CASE` statement.

```SQL
SELECT empno, ename, sal,

-- Case statement: map conditions to values of the corresponding field
CASE
        WHEN sal >= 2000 THEN 'HIGH'
        WHEN sal BETWEEN 1000 AND 1999 THEN 'MEDIUM'
        ELSE 'LOW'
END as salary_level

FROM emp;
```

## `ORDER BY CASE`

Just as with other calculated fields, you cannot `ORDER BY` the alias of a `CASE` statement. Instead, you have to rewrite the statement in both `SELECT` and `ORDER BY` clauses: 

```SQL
SELECT empno, ename, sal,
CASE
        WHEN sal >= 2000 THEN 'HIGH'
        WHEN sal BETWEEN 1000 AND 1999 THEN 'MEDIUM'
        ELSE 'LOW' END
FROM emp
ORDER BY CASE
        WHEN sal >= 2000 THEN 'HIGH'
        WHEN sal BETWEEN 1000 AND 1999 THEN 'MEDIUM'
        ELSE 'LOW' 
        END ASC;
```
This is a nuisance, and fortunately, there's a way to get around it. You can refer to a field by its ordinal position inside the table. For example, your `CASE` statement is the fourth field in the `SELECT` clause, so you can `ORDER BY` the number `4`.

```SQL
SELECT empno, ename, sal,
CASE
        WHEN sal >= 2000 THEN 'HIGH'
        WHEN sal BETWEEN 1000 AND 1999 THEN 'MEDIUM'
        ELSE 'LOW'
END as salary_level
FROM emp
-- Order by ordinal indexing in the SELECT clause
ORDER BY 4;
```

This sorts your *salary_level* alphabetically, from `High` to `Low` to `Medium`. That's probably not what you want, so you would want to do something to adjust this, perhaps by renaming the levels. Next, sort by *salary_level* and then *sal*, descending:

```SQL
SELECT empno, ename, sal,
CASE
        WHEN sal >= 2000 THEN 'HIGH'
        WHEN sal BETWEEN 1000 AND 1999 THEN 'MEDIUM'
        ELSE 'LOW'
END as salary_level
FROM emp
ORDER BY 4, 3 DESC;
```

## `CASE` and aggregations

`CASE` statements are also handy in slicing the data into separate fields. For example: what is the average salary for employees hired before and after January 1, 1982?

For this, you need to somehow split the data into employees hired before and after January 1, 1982. Then, you'll take the average salary for each bucket. You can do this with two `CASE` statements. Each will return the average salary, conditional for your hire date constraint.

```SQL
SELECT 
AVG(CASE WHEN hiredate < '1981-12-31' THEN sal END) AS oldhiresal,
AVG(CASE WHEN hiredate > '1982-01-01' THEN sal END) AS newhiresal
FROM emp;
```
Using a more complex `CASE` statement, you can do the same to get percentages of records that meet some criteria. Imagine that you want to find the percentage of employees in each category with salaries greater than $1,000. By converting the corresponding records to `1` and `0` values, you can take an average—which results in a group percentage.

```SQL
SELECT job,
AVG(CASE WHEN sal < 999 THEN 1 WHEN sal > 1000 THEN 0 END) AS pct_lt1000,
AVG(CASE WHEN sal < 999 THEN 0 WHEN sal > 1000 THEN 1 END) AS pct_gt1000
FROM emp
GROUP BY job;
```    
## `WITH` and common table expressions 

`WITH` statements allow you to write auxiliary statements for use in a larger query. These statements are often referred to as *Common Table Expressions* (CTEs). With a CTE, you are essentially defining a temporary table that exists just for one query. The CTE is declared *before* the main query. 

If you think this sounds similar to how you used subqueries, good thinking! They share many traits. But CTEs are more robust than subqueries, and they are often more readable for very complex queries. However, subqueries are perfectly appropriate, too, depending on the specific use case. 

As you've seen throughout the program, there are usually multiple ways to do the same thing with any data science tool. So it comes down to considerations like ease of use and maintainability. But enough rumination—it's time to learn about CTEs!

A common CTE is structured like this: 

```SQL
-- Name the CTE
WITH cte AS  
-- Write a regular SQL statement
-- inside parentheses 
  (
    SELECT col1, col2
    FROM table)
-- "Feed" the CTE into a second query
SELECT
  AVG(col1) AS avg_col
FROM cte;
```
First, use the `WITH` statement to call the CTE. Then, use the CTE expression name. This is the name of the temporary table. You can name the CTE anything, subject to the usual SQL naming constraints.

Then, define the query in parentheses. The part inside the parentheses should look like any other SQL statement that you've written in the program. After writing the query, close it in parentheses. 

Then, feed the CTE into a second query. This way, you are able to write a query on top of a temporary table (which itself was created from a query). 

Start with a basic example from the *employees* database. You'll create a CTE, *title_sal*, containing the average salary for each job title. You will then feed *title_sal* into the second query.

```SQL
-- Create temporary table title_sal
-- and then query from it
WITH title_sal AS 
(
        SELECT job, AVG(sal) AS avg_sal
        FROM emp
        GROUP BY job
)
SELECT * FROM title_sal;
```
This is a pretty unexciting example—you just passed the CTE into the second query with no modifications. Now, try something more realistic. 

The below query uses the same CTE. But this time, you will filter the results. The query below will only return average group salaries that are over $1,500. See how you are filtering by an aggregated measure? This is an example of where CTEs come in handy. 

Essentially, you are creating a temporary table that stores *emp* values in aggregate, and then you're operating from that table. 

```SQL
-- Create temporary table title_sal
-- get only results where avg_sal > 1500
WITH title_sal AS 
(
        SELECT job, AVG(sal) AS avg_sal
        FROM emp
        GROUP BY job
)
SELECT * FROM title_sal
        WHERE avg_sal > 1500;
```

You could have done this same thing using the other clauses that you've learned about. With `HAVING`, for example, you can restrict the resulting table to just those results where the average salary is greater than $1,500: 

```SQL
-- Another approach: HAVING
SELECT job, AVG(sal) AS avg_sal
FROM emp
GROUP BY job
HAVING AVG(sal) > 1500;
```

So why are CTEs useful? Well, notice that you can alias the field inside the CTE and use that name in later expressions. The greater flexibility with field naming is a big benefit of CTEs. And, more generally, CTEs are a more robust solution than simple aggregations. 

For example, consider this use case: you can take an aggregate of an aggregate using a CTE. Imagine that you want the average of average salaries by job title. You can set up the *avg_title_sal* CTE and then feed it into the second query, which takes an average of the *avg_sal* field that you created.

```SQL
-- Get average of average salary
-- by job title 
WITH avg_title_sal AS 
(
        SELECT job, AVG(sal) AS avg_sal
        FROM emp
        GROUP BY job
)
SELECT AVG(avg_sal) AS avg_title_sal
        FROM avg_title_sal;
```
Check out the video below for a screencast demonstration of the topics covered in this checkpoint.

<iframe id="kaltura_player_1590584144" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590584144&entry_id=1_m1y8dopw" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Recap: Subqueries, `CASE`, and `WITH`

SQL may be 45 years old, but there is always something new to learn with SQL! This checkpoint gave you a sense of some of SQL's more exotic queries that might be used for real-life data wrangling challenges. Again, this is far from an exhaustive demonstration of what these expressions are capable of—let alone the broader world of SQL queries.

Scientists constantly play the role of code researcher, scouring the web for data science resources and tailoring them to their specific use cases. SQL is definitely no exception, and you will likely find your own favorite resources. Here are a few to get you started:

- [PostgreSQL documentation](https://www.postgresql.org/docs/): Why not go straight to the source? By reading the official documentation, you can learn more about how to use PostgreSQL from the people who know it best. 
- [WiseOwlTutorials YouTube channel](https://www.youtube.com/user/WiseOwlTutorials/search?query=sql): Many of these SQL tutorials are demonstrated in SQL Server, but they will translate to PostgreSQL just fine.
- [w3schools](https://www.w3schools.com/sql/): SQL is a foundational tool in web development, too. w3schools, which describes itself as "the world's largest web developer site," has a wealth of resources on SQL.

As you build your SQL skills, you'll want to write efficient, or *performant*, code. Check out the video below for some tips. 

<iframe id="kaltura_player_1590584237" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590584237&entry_id=1_5o4lrysj" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>
