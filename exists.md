## SQL EXISTS Operator

The `EXISTS` operator is used to test for the existence of any record in a subquery
The `Exists` operator returns TRUE if the subquery returns one or more records.
## Exists  Syntax
```
SELECT column_name(S)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```

## SQL Statement
```
SELECT SupplierName
FROM Suppliers
WHERE EXISTS(SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price <20);
```
## The  following SQL statement returns TRUE and lists the suppliers with a products price equal to 22 :
```
SELECT SupplierName
FROM Suppliers
WHERE EXISTS(SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price =22);
```