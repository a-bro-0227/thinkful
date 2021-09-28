---
title: 'Counting, grouping, and listing distinct records'
author: Thinkful
team: grading
time: 120 minutes
uuid: bb2ed47c-ed04-4077-8e4e-056886999640
timeHours: 2
---

**Reminder:** Make sure that you're using pgAdmin 4 v5.0 or newer!

At the end of the previous module, you briefly explored the concept of aggregates. Specifically, you learned about the `COUNT` operator and `SELECT DISTINCT`. You looked at both `SELECT COUNT(*)` and `SELECT COUNT`, and you analyzed a key difference between them: `SELECT COUNT` will not include any `NULL` records in the aggregation. 

In this checkpoint, you'll consider further possibilities for using `COUNT`. You'll practice listing and counting unique records and drilling down on a `COUNT` aggregate with the `GROUP BY` clause.

Feel free to follow along and try visualizing these code snippets in the database as you go through.

Pick up where you left off with `SELECT DISTINCT`. You might remember the statement shown below, which will get you a count of all the records in which *yearbuilt* is greater than `1950`.

```SQL
SELECT COUNT(*)
FROM houseprices
WHERE yearbuilt > 1950;
```
And the following statement will return all unique values for *yearbuilt* in which *yearbuilt* is greater than `1950`. In other words, you'll get no duplicates.

```SQL
SELECT DISTINCT yearbuilt
FROM houseprices
WHERE yearbuilt > 1950;
```
You may remember that it's also possible to list the unique combinations of different records' values.

```SQL
SELECT DISTINCT yearbuilt, neighborhood
FROM houseprices;
```

But this next statement will not execute. This is because you can't get a unique list for two different fields at once.

```SQL
SELECT DISTINCT yearbuilt, DISTINCT neighborhood
FROM houseprices;
```
What can you do to resolve this error? One approach is to aggregate the aggregation by using `COUNT(DISTINCT)`.

## `COUNT(DISTINCT)`

Although you can't get the separate unique value lists of *yearbuilt* and *neighborhood* at the same time, you can get the count of unique values for each. It's a subtle difference. In the statement below, you're counting all of the unique values, rather than listing them. `DISTINCT` goes inside the parentheses with the identifier, to be evaluated as a single expression. 

```SQL
SELECT COUNT(DISTINCT yearbuilt), COUNT(DISTINCT neighborhood)
FROM houseprices;
```

It's important to note that SQL aggregations are sensitive to changes in a `WHERE` clause. You'll get fewer results with the following command than with the one above, for example.

```SQL
SELECT COUNT(DISTINCT yearbuilt), COUNT(DISTINCT neighborhood)
FROM houseprices
WHERE yearbuilt < 2000 AND neighborhood NOT LIKE 'G%';
```

## Using aggregates and nonaggregates together

`COUNT` and `DISTINCT` can be used together seamlessly. But using the `SELECT` operator on an aggregate and a nonaggregate in the same statement will lead to problems.

```SQL
SELECT COUNT(neighborhood), yearbuilt
FROM houseprices;
```

A statement like the one above will not execute. You'll receive an error message like this:

```
ERROR:  column "houseprices.yearbuilt" must appear in the GROUP BY clause or be used in an aggregate function
LINE 1: SELECT COUNT(neighborhood), yearbuilt
```

This error message is fairly straightforward—a real treat in programming! The problem lies in the tension between the aggregate and nonaggregate fields in your statement. There are two ways that you can resolve this issue.

### Approach 1: Aggregate them both

This is the first possible solution. Remember, it's possible to `COUNT` by individual records in one statement, as shown below.


```SQL
SELECT COUNT(neighborhood), COUNT(yearbuilt)
```

You already know how to do this. So keep learning about the ins and outs of aggregating by moving on to the next possible solution.

### Approach 2: Group the aggregated field by the other field

Imagine that you wanted to count how many unique *yearbuilt* values existed for each neighborhood.

```SQL
SELECT neighborhood, COUNT(DISTINCT(yearbuilt))
FROM houseprices
GROUP BY neighborhood;
```

The count of *yearbuilt* is now grouped by neighborhood. In SQL, having an aggregated field grouped by another field requires an aptly named special statement: `GROUP BY`.


## Introducing `GROUP BY`

Moving down the list of SQL tools, take a look at the `GROUP BY` clause. 


| Clause   | What to do with it                                            |
| -------- | ------------------------------------------------------------- |
| `SELECT`   | Specify what fields you want information from                 |
| `FROM`     | Specify what tables those fields are coming from              |
| `WHERE`    | Specify any criteria that records in those fields should meet |
| **`GROUP BY`** | **Specify how to aggregate the results**                          |
|<span style="color:lightgray"> `HAVING`</span>   | <span style="color:lightgray">Specify any criteria that the aggregate results should meet</span>   |
| `ORDER BY`| Specify how to sort the results                              |
| <span style="color:lightgray">`LIMIT`</span>    | <span style="color:lightgray">Specify how many records to return in results</span>                 |

For those of you keeping score at home, you've (literally) flipped the script on how SQL clauses are ordered. `ORDER BY` will follow any use of `GROUP BY`. But functionally, this clause will work the same as how you've been using it.

`GROUP BY` is essentially the missing link between the aggregate and nonaggregate fields in `SELECT BY`. If a field isn't aggregated in `SELECT`, it needs to be summarized with a `GROUP BY`.

So, revisit the problematic statement below:

```SQL
SELECT COUNT(neighborhood), yearbuilt
FROM houseprices;
```

The second way to fix this statement is shown in the following statement:

```SQL
SELECT COUNT(neighborhood), yearbuilt
FROM houseprices
GROUP BY yearbuilt;
```

It's also possible to reorder the way that the output appears. You can do that by aliasing and rewriting the `SELECT` clause, as shown below.

```SQL
SELECT yearbuilt AS yearbuilt, COUNT(neighborhood) AS number_of_neighborhoods
FROM houseprices
GROUP BY yearbuilt;
```

## `COUNT(*) … GROUP BY`

In the last checkpoint, you used `COUNT(*)` with `WHERE` to return a count of all the records in which *saleprice* is above `100,000` and *yearbuilt* is less than `1950`. This can be seen again below.  

```SQL
SELECT COUNT(*)
FROM houseprices
WHERE saleprice > 100000 AND yearbuilt < 1950;
```

Using these same criteria together with `GROUP BY`, you can group this `COUNT` aggregation by the number of records per neighborhood. 

```SQL
SELECT COUNT(*), neighborhood
FROM houseprices
WHERE saleprice > 100000 AND yearbuilt < 1950
GROUP BY neighborhood;
```

You can, of course, sort this output alphabetically. Remember, `ORDER BY` follows `GROUP BY`.

```SQL
SELECT COUNT(*), neighborhood
FROM houseprices
WHERE saleprice > 100000 AND yearbuilt < 1950
GROUP BY neighborhood
ORDER BY neighborhood;
```

## `GROUP BY` and aliasing

What if you want to sort from high to low instead of alphabetically? This might not be intuitive, but it's perfectly acceptable to use an aggregate in an `ORDER BY` clause, as shown below. 

```SQL
SELECT COUNT(*), neighborhood
FROM houseprices
WHERE saleprice > 100000 AND yearbuilt < 1950
GROUP BY neighborhood
ORDER BY COUNT(*);
```

However, it's far more common to accomplish this by using an alias. Remember: *aliasing* is the practice of temporarily assigning a name to a field. So far, you've used aliasing primarily as a cosmetic improvement to the table that you get back from your SQL command. 

So it's good data hygiene to use an alias anyway. But there's more to it than that. Once defined, an alias can be referred to later on in the statement. So the statement above becomes the following:

```SQL
SELECT COUNT(*) AS count_houses, neighborhood
FROM houseprices
WHERE saleprice > 100000 AND yearbuilt < 1950
GROUP BY neighborhood
ORDER BY count_houses DESC;
```

So far, you've been experimenting on a statement with one aggregate field and one field to group by. With SQL, it's possible to work with multiple `GROUP BY` fields at once. Take a look at some examples below.


## `GROUP BY` multiple fields

`GROUP BY` with multiple fields adds more granularity to a query. Say, for example, that you want to get a count of records by year, sorted in descending order. You could do the following.

```SQL
SELECT COUNT(*), yearbuilt
FROM houseprices
GROUP BY yearbuilt
ORDER BY yearbuilt DESC;
```

But there are so many other fields in the *houseprices* table—79, to be exact. Wouldn't it be nice to break this count into records by both *yearbuilt* and *housestyle*? In the statement below, a third field goes into the `SELECT` clause, and a second field goes into the `GROUP BY` clause.

```SQL
SELECT COUNT(*), yearbuilt, housestyle
FROM houseprices
GROUP BY yearbuilt, housestyle
ORDER BY yearbuilt DESC;
```

And just like with other SQL statements, you can rearrange the ordering of fields and re-sort the ordering of records.

```SQL
SELECT yearbuilt, housestyle, COUNT(*)
FROM houseprices
GROUP BY yearbuilt, housestyle
ORDER BY yearbuilt DESC, housestyle;
```


## `COUNT` multiple fields

It's important to remember that `COUNT` will yield different results on different fields because of how `NULL` is treated. You may have noticed that the *alley* field is sparsely populated. What happens when you want to group both a count of *alley* and a count of all records, and order by a count of *alley* in ascending order? You'll notice that the majority of neighborhoods do not have an alley, which may be useful information.

```SQL
SELECT COUNT(*) AS count_records, COUNT(alley) AS count_alleys, neighborhood
FROM houseprices
GROUP BY neighborhood
ORDER BY count_alleys ASC;
```

Other than that, including additional `COUNT` clauses in a query is straightforward. The usual rules of SQL apply, as shown below.

```SQL
SELECT COUNT(*) AS count_records, COUNT(alley) as count_alleys, neighborhood
FROM houseprices
WHERE yearbuilt > 1990
GROUP BY neighborhood
ORDER BY count_alleys DESC;
```

## `COUNT` and `GROUP BY` multiple fields

There should be no surprises when it comes to including multiple `COUNT` and `GROUP BY` fields. For example, try getting a count of all records (`*`) and a count of *alley*, grouped by *neighborhood*, sorted ascending, and *street*. Voila!

```SQL
SELECT COUNT(*) AS count_records, COUNT(alley) as count_alleys, neighborhood, street
FROM houseprices
GROUP BY neighborhood, street
ORDER BY neighborhood;
```

## `COUNT` and `GROUP BY` the same field

The *houseprices* table has a *roofstyle* field and a *neighborhood* field. How would you go about creating a list of roof styles in each neighborhood and a count of those roof styles? 

Your first pass might look something like the statement below. This does give you the total count of records in the *roofstyle* field. But it provides no additional information about the records that make up the count.

```SQL
SELECT COUNT(roofstyle), neighborhood
FROM houseprices
GROUP BY neighborhood;
```

Before you try anything too crazy, what if you used `SELECT COUNT DISTINCT` to get a count of unique roof styles in each neighborhood?

```SQL
SELECT COUNT (DISTINCT roofstyle), neighborhood
FROM houseprices
GROUP BY neighborhood;
```

This statement is slightly more helpful. But what you really want is a `COUNT` of *roofstyle* records grouped by *roofstyle*. So, incorporating that into your statement, you have the following:

```SQL
SELECT COUNT (roofstyle), neighborhood
FROM houseprices
GROUP BY neighborhood, roofstyle;
```

Amazing! You can `GROUP BY` the same field that you used for the aggregation itself. Here is an example. To get a count of *roofstyle* and to group by unique roof styles per neighborhood, you can use the following statement. 

```SQL
SELECT neighborhood, roofstyle, COUNT(roofstyle) AS count_roofstyle
FROM houseprices
GROUP BY roofstyle, neighborhood
ORDER BY neighborhood, roofstyle, count_roofstyle;
```

Check out the video below for a screencast demonstration of the topics covered in this checkpoint.

<iframe id="kaltura_player_1590583812" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590583812&entry_id=1_z727lwll" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Aggregations: To `COUNT` and beyond! 

In this checkpoint, you looked at the launching point for aggregations in SQL: the `COUNT` operator. But SQL allows you to aggregate data in several different ways. You'll explore some of those approaches in the next checkpoint.
