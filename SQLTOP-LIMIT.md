
## The SQL SELECT TOP Clause

The `SELECT TOP` clause is used to specify the number of records to return.
The `SELECT TOP` clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.

```
SELECT TOP 3 * FROM Customers;
```

```
Note: Not all database systems support the `SELECT TOP` clause. MySQL supports the `LIMIT` clause to select a limited number of records, while Oracle uses `FETCH FIRST nROWS ONLY` and `ROWUNM`
```

## sql server/MS Access Syntax:
```
SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;
```
## MySQL Syntax:
```
SELECT column_ame(s)
FROM table_name
WHERE condition
LIMIT number;
```
## Oracle 12 Syntax:
```
SELECT column_name(s)
FROM table_name
ORDER BY column_name(s)
FETCH FIRST number ROWS ONLY;
```
Older Oracle Syntax:
```
SELECT column_name(s)
FROM table_name
WHERE ROWNUM <=number;
```
Older Orancle Syntax(with ORDER BY):
```
SELECT *
FROM （SELECT  column_name(s) FROM table_name ORDER BY column_name(s))
WHERE ROWNUM <= number;
```
## LIMIT 
The following SQL statement shows the equivalent example for MySQL:

```
SELECT * FROM Customers
LIMIT 3;
```

## FETCH FIRST Oracle.

The following SQL statement shows the equivalent example for Oracle:
```
SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;
```
## SQL TOP PERCENT Example
The following SQL statement selects the first 50% of the records from the "Customers" table (for SQL Server/MS Access):
```
SELECT TOP 50 PERCENT * FROM Customers;
```
The following SQL statement shows the equivalent example for Oracle:
```
SELECT * FROM Customers
FETCH FIRST 50 PERCENT ROWS ONLY;
```
## ADD a WHERE CLAUSE 
THE following SQL Statement selects the first three records from the "Customers" table,
where the country is "Germany"(for SQL Server/MS Access):
```
SELECT TOP 3 * FROM Customers
WHERE Country='Germany';
```
## The following SQL statement shows the equivalent example for MySQL：
```
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;
```
## The following SQL statement shows the equivalent example  for Oracle:
```
SELECT * FROM Customers
WHERE Country='Germany'
FETCH FIRST 3 ROWS ONLY;
```

## ADD the ORDER BY Keyword
Add the `ORDER BY` keyword when you want to sort the result, and return the first 3 recores of the sorted result.

For ***SQL Server*** and ***MS Access***:

Example
sort the result reverse alphabetically by CustomerName, and return the first 3 records:
```
SELECT TOP 3 * FROM Customers
ORDER BY CustomerName DESC;
```
The following SQL statement shows the equivalent example for MySQL:
```
SELECT * FROM Customers
ORDER BY CusomerName DESC
LIMIT 3;
```

## THE following SQL statement shows the equivalent example for Oracle:
```
SELECT * FROM Customers
ORDER BY CustomerName DESC
FETCH FIRST 3 ROWS ONLY;
```

## SQL Aggregae Functions 

An ***aggregate*** function is a function that performs a calculation on a set of values, and returns a single value.

Aggregate functions are often used with the `GROUP BY` 

The most commonly used SQL aggregate functions are :
- MIN() - returns the smallest value within the selected column
- MAX() - returns the largest value within the selected column
- COUNT() - returns the number of rows in a set 
- SUM()- returns the total sum of numerical column
- AVG() -returns the average value of a numerical column

Aggregate functions ignore null values (expect for COUNT(*)).
