# SQL AVG() Function
[SQL AVG](https://www.w3schools.com/sql/sql_avg.asp)

The SQLL AVG() Function
The `AVG()` function returns the average value of a numeric column.
```
SELECT AVG(Price)
FROM Products
```
note : ***NULL*** values are ignored.

## syntax

```
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```
## Add a WHERE Clause 
You can add a `WHERE` clause to specify conditions.

Example
Return the average price of products in category 1:
```
SELECT AVG(Price)
FROM Products
WHERE CategoryID =1;
```
## Use an Alias
Give the AVG column a name by using the `AS` keyword.

Example
## Name the column "average price"
```
SELECCT AVG(Price) AS [average price]
FROM Products;
```

## Higher Than Average
To list all records with a higher  price than average, we can use the `AVG()`function in a sub query:

example
Return all products with a higher price than the average price:
```
SELECT * FROM Products
WHERE price > (SELECT AVG(price) FROM Products)
```

## Use AVG() with GROUP BY

here we use the `AVG()`function and the `GROUP BY` clause, to return the average price for each category in the Products table:
```
SELECT AVG(Price) AS AveragePrice,CategoryID
FROM Products
GROUP BY CategoryID;
```
You will learn more about the `GROUP BY` clause later in this tutorial.
