
# SQL MIN() and MAX() Functions
[sql](https://www.w3schools.com/sql/sql_min_max.asp )

## The SQL MIN() and MAX（）Functions
The MIN() function returns the smallest value of the selected column.
The `MAX()` function returns the largest value of the selected column.

## Find the lowest price in the Price column:
```
SELECT MIN(Price)
FROM Products
```

## MAX Example
Finde the highest price in the Price column:
```
SELECT MAX(Price)
FROM Products;
```

## Syntax 

```
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```

```
SELECT MAX(column_name)
FROM  table_name
WHERE condition;
```

## Set Column Name(Alias)
When you use `MIN()` or `Max()`, the returned column will not have a descriptive name.To give the column a descriptive name, use the `AS` keyword:
```
SELECT MIN(Price) AS SmallestPrice
FROM Products;
```
## Use MIN() with GROUP BY

Here we use the `MIN()` function and the `GROUP BY` clause, to return the smallest price for each category in the Products table:
```
SELECT MIN(Price) AS SmallestPrice, CategoryID
FROM Products
GROUP BY CategoryID;
```

#3