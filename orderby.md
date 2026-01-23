## SQL ORDER BY Keyword

## The SQL ORDER BY 
The `ORDER BY` keyword is used to sort the result-set in ascending or descending order.

```
SELECT * FROM Products
ORDER BY Price;
```

## Syntax
```
SELECT column1, column2, ...
FROM table_name
ORDER BY column1,column2, ... ASC|DESC;
```

## DESC
The `ORDER BY` keyword sorts the records in ascending order by default. To sort the records in descending order, use the `DESC` keyword.

example
Sort the products from highest to lowest price:
```
SELECT * FROM Products
ORDER BY Price DESC;
```

## Order Alphabetically

For string values the `ORDER BY` keyword will order alphabetically.

example:
```
SELECT * FROM Products
ORDER BY ProductName;
```

## Alphabetically DESC

To sort the table reserse alphabetically, use the `DESE` keyword:

EXAMPLE:
```
SELECT * FROM Products
ORDER BY ProductName DESC
```
## ORDER BY Several Columns
The following SQL statement selects all customer from the "customers" table, sorted by the "Country" and the "customername   This means this ordered by countrys but the countryname is same by the "customersName"