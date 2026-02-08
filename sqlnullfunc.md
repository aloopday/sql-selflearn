
# SQL NULL Functions
[null functions](https://www.w3schools.com/sql/sql_isnull.asp)

## SQL IFNULL(),ISNULL(),COALESCE(), and NUL() Functions

Look at the following SELECT statement:
```
SELECT ProductName, UnitPrice * (UnitsInStock + UnitsOnOrder)
FROM Products;
```
## In the example above, if any of the "UnitsOnOrder" values
are NULL, the result will be NULL.

## Solutions

MySQL
The MySQL IFNULL() function lets you return an alternative value if an expression is 
NULL:
```
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0))
FROM Products;
```
or we can use the ```COALESCE()``` function, like this:
```
SELECT ProductName, UnitPrice * (UnitsInStock + COALESCE(UnitsOnOrder,0))
FROM Products;
```

## SQL Server
The SQL Server `ISNULL()` function lets you return an alternative value when 
an expression is NULL:
```
SELECT ProductName, UnitPrice * (UnitsInStock + ISNULL(UnitsOnOrder, 0))

```
or we can use the `COALESCE()` function, like this:
```
SELECT ProductName, UnitPrice * (UnitsInStock + COALESCE(UnitsOnOrder, 0))
```

## MS Access
THe MS Access `IsNull()` function returns TRUE(-1)  If the expression is a 
null value, otherwise FALSE(0):
```
SELECT ProductName, UnitPrice * (UnitsInStock + IIF(ISnull(UnitsOnOrder),0,UnitsOnOrder))
FROM Products;
```