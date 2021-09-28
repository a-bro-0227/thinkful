---
title: 'AVG, SUM, MAX, and MIN'
author: Thinkful
team: grading
time: 80 minutes
uuid: 931810b9-f88f-4f7e-aea9-e641f4889e63
timeHours: 1.3333333333333333
---

The previous checkpoint introduced the concept of aggregating results by group. As you learned, this is made possible by the `GROUP BY` clause; you explored this primarily with the `COUNT` operator. Now, you'll continue your exploration of aggregation by focusing on the following operators: `AVG`, `SUM`, `MAX`, and `MIN`.

In this checkpoint, you'll continue to work with the *houseprices* table. This is located in the *houseprices* database of the shared Thinkful server.


## `AVG`

As a data scientist, you'll regularly find yourself computing averages. It's one of the most common calculations that you'll need to make. In SQL, this can be accomplished with `AVG`.

The query below will return the average *saleprice* per *neighborhood* and per *yearbuilt*. The result will be sorted by *neighborhood* and *yearbuilt*, in descending order. 

```SQL
SELECT AVG(saleprice), yearbuilt, neighborhood
FROM houseprices
GROUP BY yearbuilt, neighborhood
ORDER BY neighborhood, yearbuilt DESC;
```

This looks a lot like what you were doing earlier with `COUNT`. But there's a key difference. Here, you're using the `AVG` operator to compute an average. Even though writing the statement itself wasn't too difficult, you have to keep a couple of things in mind as you proceed.

First, the output goes to small fractions of a penny. This is not helpful information. You can use `ROUND` to clean up your results.

```SQL
SELECT ROUND(AVG(saleprice),0), yearbuilt, neighborhood
FROM houseprices
GROUP BY yearbuilt, neighborhood
ORDER BY neighborhood, yearbuilt DESC;
```

The second idea to keep in mind is this: think like a scientist as you review your SQL syntax and outputs. You might have noticed that many of these averaged numbers are very round. In other words, they end in 0's and 5's. This raises the question of how many numbers you're actually averaging in the first place. Do you know how to find out that information? That's right—with a `COUNT` aggregation.

```SQL
SELECT ROUND(AVG(saleprice),0) AS avg_houseprice, COUNT(saleprice) AS count_houseprice, yearbuilt, neighborhood
FROM houseprices
GROUP BY yearbuilt, neighborhood
ORDER BY neighborhood, yearbuilt DESC;
```

Indeed, you see here that many of the results include just one or two records. So it's up to you, the data scientist, to decide whether or not this is useful information, depending on the business use case. This example also serves as an important reminder: using several aggregates in conjunction provides a more holistic exploratory look at the data. 

Like `COUNT`, `AVG` does not include `NULL` values in its calculations. Consider the statement below, for example.

```SQL
SELECT AVG(lotfrontage)
FROM houseprices;
```

You know that an average is a sum of records divided by their count. But what `COUNT` is `AVG` using here? Is it using the count of all records or the count of nonnull *lotfrontage* records? You can get an answer using the statement below.

```SQL
SELECT SUM(lotfrontage) AS sum_lotfrontage, 
COUNT(*) AS count_all_records,
COUNT(lotfrontage) AS count_lotfront_records,
AVG(lotfrontage) AS avg_lotfrontage
FROM houseprices;
```

Here, you can do the math yourself. You'll see that `AVG` in SQL excludes `NULL` values from the denominator, which is the count of records. 

The above statement also makes use of the `SUM` operator, which you'll learn about shortly.

But first, take a look at an operation in which you can counterintuitively use the aggregative properties of `NULL`. In the next statement, create this metric: *avg_area_per_garage_bay*. This is a ratio of *garagearea* to *garagecars* for each record. You'll group this aggregation by *garagetype*, as shown below.

```SQL
SELECT garagetype, AVG(garagearea/garagecars) AS avg_area_per_garage_bay
FROM houseprices
GROUP BY garagetype;
```
This will return an error.

```SQL
ERROR:  division by zero
SQL state: 22012
```

You can't divide records by zero. But you can use conditional logic to replace desired values. In this case, use `NULLIF`.

This function takes two arguments, as shown below.

```SQL
NULLIF(x, y)
```

If `x` and `y` are equal to each other, SQL returns a `NULL`. If they are not equal, SQL returns the value of `x`. Therefore, you can use this function to replace any potential zeroes in the denominators with `NULL` values. SQL will then exclude these records from aggregation. 


```SQL
SELECT garagetype, avg(garagearea/NULLIF(garagecars,0)) as avg_area_per_garage_bay
FROM houseprices
GROUP BY garagetype;
```

## `SUM`

At this point, the remaining aggregations should be fairly straightforward. They follow the same rules as the ones covered so far. Take a more in-depth look at the sum of *lotfrontage* for records where *yearbuilt* is less than `1980`, sorted by the sum of *lotfrontage*, descending. You will group the results by lot shape and street type, which means that you need to include the fields *lotshape* and *street* in both the `SELECT` and the `GROUP BY` statements.

```SQL
SELECT SUM(lotfrontage) AS sum_lotfront, lotshape, street
FROM houseprices
WHERE yearbuilt < 1980
GROUP BY lotshape, street
ORDER BY sum_lotfront DESC;
```

Again, you see here that `NULL` isn't treated as a `0` when summing. It's its own value that actually defaults to the top of the list when sorting in descending order.

## `MIN`

Now, try a `MIN` operation. What is the smallest lot area for each style of roof for houses built in 1970 or later, sorted from high to low?

```SQL
SELECT MIN(lotarea) AS min_lotarea, roofstyle
FROM houseprices
WHERE yearbuilt >= 1970
GROUP BY roofstyle
ORDER BY min_lotarea DESC;
```

## `MAX`

Now, try a `MAX` operation. What's the maximum sale price for all records, grouped by the year they were sold and the style of house? Sort the output by style of house from A to Z and then by sale price from high to low.

```SQL
SELECT MAX(saleprice) AS max_salesprice, yrsold, housestyle
FROM houseprices
GROUP BY yrsold, housestyle
ORDER BY housestyle, max_salesprice DESC;
```

## Recap

In this checkpoint, you explored additional operators that you can use to aggregate data.The ability to aggregate in several ways, and sometimes in the same statement, is a handy data exploration tool. In the next checkpoint, you'll finish this module with one last clause. You'll also take a comprehensive look at aggregation.
