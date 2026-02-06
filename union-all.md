## SQL UNION ALL -Operator

[The SQL UNION ALL Operator](https://www.w3schools.com/sql/sql_union_all.asp)

`UNION ALL` combine the result-set of two or more `SELECT` statements.
include all rows from each statement, including any duplicates.

Requirements for `UNION ALL`:
- same number of columns
- The columns must also have similar data types
- The columns in every `SELECT` statement must also be in the 
same order.

## UNION ALL Syntax
`UNION All` includes duplicate values , by default.

```
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2

```
## Note: The column names in the result-set are usually 
equal to the column names in the first `SELECT` statement


## SQL Statement

```
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers
ORDER BY City;
```


## SQL Statement:
```
SELECT City, Country FROM Customers
WHERE Counry='German'
UNION ALL
SELECT City,Country FROM Suppliers
WHERE Counry="Germany"
ORDER BY City;
```

