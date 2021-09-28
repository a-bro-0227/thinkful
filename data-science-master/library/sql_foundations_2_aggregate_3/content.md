---
title: HAVING and clause ordering
author: Thinkful
team: grading
time: 80 minutes
uuid: e8a1beef-8c9e-4a7d-ad7a-6e3fe8c483c6
timeHours: 1.3333333333333333
---

This checkpoint covers one last SQL clause: `HAVING`. Then, you'll take a big-picture look at using all six of the clauses that you've learned. As in previous checkpoints, you'll use the *houseprices* table in the *houseprices* database, which is in the shared Thinkful server. 

## `HAVING`

Revisit the original SQL list of clauses. In this list, `HAVING` is the penultimate clause. (And you've already learned about `ORDER BY`, so you've done them all! Congratulations!) Like the `WHERE` clause, `HAVING` works sort of like a filter, but for aggregations. It falls in second-to-last place in the clause ordering in SQL statements. 

| Clause   | What to do with it                                            |
| -------- | ------------------------------------------------------------- |
| `SELECT`   | Specify what fields you want information from                 |
| `FROM`     | Specify what tables those fields are coming from              |
| `WHERE`    | Specify any criteria that records in those fields should meet |
| `GROUP BY` | Specify how to aggregate the results                          |
| **`HAVING`**   | **Specify any criteria that the aggregate results should meet**   |
| `ORDER BY`| Specify how to sort the results                               |
| `LIMIT`    | Specify how many records to return in results                 |

Have you noticed that `ORDER BY` keeps getting demoted to the bottom of the list in an actual query? It makes sense. `ORDER BY` is more about formatting query results. It doesn't do any real filtering or calculating itself.

In the previous checkpoint, a typical statement looked something like this:

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_saleprice, neighborhood
FROM houseprices
WHERE yrsold = 2010
GROUP BY neighborhood
ORDER BY avg_saleprice DESC;
```

The above query returns a table listing the average sale price of a home sold in the year 2010, grouped by neighborhood and sorted by average sales price from high to low. But with this list, how would you get the top five records?

You can add a `LIMIT` clause to the query, as shown below.

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_saleprice, neighborhood
FROM houseprices
WHERE yrsold = 2010
GROUP BY neighborhood
ORDER BY avg_saleprice DESC
LIMIT 5;
```

What if you want to get all of the records in which the average sale price is above $200,000? Of course, you could go back to the source data to do this. You could count down to the last record with a value above `200000`, and then you could modify the `LIMIT` clause accordingly. But this is an incredibly volatile and unstable way to query data.

So you'll do it in a different way. You need some way to filter your aggregated results. This is where `HAVING` comes in. Try running the statement below.

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_saleprice, neighborhood
FROM houseprices
WHERE yrsold = 2010
GROUP BY neighborhood
HAVING ROUND(AVG(saleprice),0) > 200000
ORDER BY avg_saleprice DESC;
```

Some database management systems, including PostgreSQL, do not support alias usage in the `HAVING` clause. As a result, you must aggregate a second time.

Any field used in `HAVING` must either appear in the `GROUP BY` clause or be used in an aggregate function. In other words, an operation like the one below is not possible.

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_saleprice, neighborhood
FROM houseprices
GROUP BY neighborhood
HAVING yrsold = 2010
ORDER BY avg_saleprice DESC;
```

But again, you can't filter by a field that doesn't exist in the aggregated results, can you? So that makes sense. Instead, you can use this query:

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_saleprice, neighborhood
FROM houseprices
WHERE yrsold = 2010
GROUP BY neighborhood
ORDER BY avg_saleprice DESC;
```

## Clause recap: SFWGHO

Congratulations! You've practiced using the six main SQL clauses to retrieve information from a table. You've also learned many other expressions and operators to use with those clauses. But up until this point, you've been exploring these clauses in discrete chunks. Now is a good time to review the ordering of these clauses and revisit their role as a bundle of related tools.

Throughout your education, you've likely learned some cringey mnemonics. Nevertheless, those mnemonics and cheesy sayings probably helped you commit important concepts to memory. Toward that end, here's a cringey acronym to teach you how to order SQL clauses when retrieving information from a table.


| Mnemonic | Clause |
| :-------- | :-------- |
| Sweaty   | `SELECT`   |
| Feet     | `FROM`     |
| Will     | `WHERE`    |
| Give     | `GROUP BY` |
| Horrible | `HAVING`   |
| Odors    | `ORDER BY` |

Let's go back to a previous example. In this example, every clause is working in unison.

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_saleprice, neighborhood
FROM houseprices
WHERE yrsold = 2010
GROUP BY neighborhood
HAVING ROUND(AVG(saleprice),0) > 200000
ORDER BY avg_saleprice DESC;
```

And here's another query with all six of these clauses. Try translating it into plain English.

```SQL
SELECT MAX(lotarea) AS max_lotarea, mszoning
FROM houseprices
WHERE yearbuilt > 1950
GROUP BY mszoning
HAVING MAX(lotarea) > 10000
ORDER BY max_lotarea DESC;
```

There are more than 75 fields in the *houseprices* table. And you know six clauses that can be used in conjunction with several logical and comparison operators. Needless to say, you could write many, many queries to retrieve data from this table!


### What about `LIMIT`?

Technically, there is one other clause that you covered: `LIMIT`. As you learned, `LIMIT` constrains the output to a specified number of rows. This clause is often excluded from tutorials on clause ordering. Like `ORDER BY`, `LIMIT` focuses on the output, not the source data. For that reason, `LIMIT` comes at the very end of the statement. This leaves you with a final acronym: Sweaty Feet Will Give Horrible Odors … Like? (And maybe this is why `LIMIT` is typically left off!)

## Recap

Check out the below video for a screencast demo of the topics covered in this checkpoint.

<iframe id="kaltura_player_1583695017" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/41734682/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1583695017&entry_id=1_f1getl12" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

*SQL Foundations I* focused on basic exploratory analysis on a table, and you learned how to select fields and sort and filter rows. *SQL Foundations II* took the analysis to the next level. In this module, you explored how to aggregate and group by records from a table.

In both of these modules, you operated on a single table at a time. However, as mentioned before, data in the real world is rarely so clean and prepackaged. In the next module, you'll learn about SQL tools to handle messier data.
