# The SQL INSERT INTO SELECT Statement
 The `INSERT INTO SELECT` statement copies data from one table and inserts it into another table.
The `INSERT INTO SELECT` statement requires that the data types in source and target tables match.
 Note: The existing records in the target table are unaffected.

## INSERT INTO SELECT Syntax
Copay all columns from one table to another table:
```
INSERT INTO table2
SELECT * FROM table1
WHERE condition;
```
Copy only some columns from one table into another table:
```
INSERT INTO table2 (column1, column2, column3, ...)
SELECT column1, column2,column3, ...
FROM table1
WHERE condition;
```

## Examples


Copy "suppliers" into "CUSTOMERS" (CustomerName,City,Country)
SELECT SupplierName, City, Country FROM Suppliers;
```
INSERT INTO Customers (CustomerName,City,Country)
SELECT SupplierName, City, Country FROM Suppliers;
```
2:
## EXAMPLE 
Copy "Suppliers into" "Customers"(fill all columns):
```
INSERT INTO Customers (CustomerName, ContactName,Address,City,PostalCode, Country)
SELECT SupplierName, ContactName, Address, City, PostalCode, Country FROM Suppliers
```
3:
## EXAMPLE
Copy only the German suppliers into "Customers"
```
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers
WHERE Country ='Germany';
```

