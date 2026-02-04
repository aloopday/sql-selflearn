# SQL INNER JOIN
[sql inner join](https://www.w3schools.com/sql/sql_join_inner.asp)

## INNER JOIN
The `INNER JOIN` keyword selects records that have matching values in both tables.

## We will join the Products table with the Categories table,by using the `CategryID` field from both tables.

```
SELECT ProductID, ProductName, CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

***NOte***: The ```INNER JOIN``` keyword returns only rows with a match in both tables. Which means that if you have a product with no CategoryID, or with a CategoryID that is not present in the Categories table, that record would not be returned in the result.

## Syntax
```
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

## JOIN OR INNER JOIN

`JOIN` and `INNER JOIN` will return the same result.
`INNER` is the default join type for `JOIN`, so when you write `JOIN` the parser actually writes `INNER JOIN`.


```
SELECT Products.ProductID, Products.ProductName,Categories.CategoryName
FROM Products
JOIN Categories ON Products.CategoryID = Categories.CaategoryID;
```

## JOIN Three Tables
The following SQL statement selects all orders with customer and shipper information:

```
SELECT Orders.OrderID, Customers.CustomerName,Shippers.ShipperName 
FROM((Orders
INNER JOIN Customers ON Orders.CustomerID =Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);
```

## SQL LEFT JOIN Keyword

[sql left join](https://www.w3schools.com/sql/sql_join_left.asp)

The `LEFT JOIN` keyword returns all records from the left table(table1), and the matching records from the right table(table2). The result is 0 records from the right side, if there is no match.

LEFT JOIN Syntax
```
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```
***NOTE*** in some databases LEFT JOIN is called LEFT OUTER JOIN.

![alt text](image-1.png)

## SQL LEFT JOIN EXAMPLE
The following SQL statement will select all customers , and any orders they minght have:
```
SELECT Customers.CustomerName,Orers.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerName;
```
***Note*** The `LEFT JOIN` keyword returns all records from the left table (Customers), even if there are no matches in the ritht table (Orders).

## SQL RIGHT JOIN KEYWORD
[right join keyword](https://www.w3schools.com/sql/sql_join_right.asp)

## SQL RIGHT JOIN Keyword
The `RIGHT JOIN` keyword returns all records from the right table(table2),and the matching records from the left table(table1). The result is o records form the left isde, if there is no match.

## RIGHT JOIN Syntax
```
SELECT column_name(s)
FROM table1
RGITH JOIN table2
ON table1.column_name =table2.column_name;
```
## ***NOTE*** In some databases `RIGHT JOIN` IS called 
`RIGHT OUTER JOIN`.
![alt text](image-2.png)

## sql RIGHT JOIN Example
The following SQL statement will return all employees, and any orders they might have placed
```
SELECT Orders.OrderID, Employees.LastName,Employees.Firstname
FROM Orders
RIGHT JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```
**NOTE** The `RIGHT JOIN` keyword returns all records from the right table(Employees), even if there are no matches in the left table(Orders).
## SQL FULL OUTER JOIN Keyword
[full join](https://www.w3schools.com/sql/sql_join_full.asp)

The `FULL OUTER JOIN` keyword returns all records when there is a match in left (table1) and right (table2) table records.

Tips: `Full OUTER JOIN` and `FULL JOIN` are  the same.

## FULL OUTER JOIN SYntax
```
SELECT column_name(S)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name =table2.column_name
WHERE condition;
```
![alt text](image-3.png)

**NOTE** ```FULL OUTER JOIN``` can potentially return very large result-sets@

## SQL FULL OUTER JOIN Example
The following SQL statement selects all customers , and all orders
```
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```
## SQL SELF JOIN
[sql self join](https://www.w3schools.com/sql/sql_join_self.asp)

A self join is a regular join,but the table is joined with itself.

## Self Join Syntax
```
SELECT column_name(S)
FROM table1 T1,table2 T2
WHERE condition;
```
## T1 and T2 are different table aliases for the same table.
```
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerNAME2, A.City 
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
ORDER BY A.City;
```

## SQL UNION Operator
