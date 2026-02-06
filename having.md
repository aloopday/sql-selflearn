# SQL HAVING CLAUSE
[sql having clause](https://www.w3schools.com/sql/sql_having.asp)

The SQL HAVING Clause
The `HAVING` cluase was added to SQL because the `WHERE` keyword cannot be used wit aggregate functions.

## HAVING Syntax
```
SELECT column_name(S)
FROM table_name
WHERE condtion
GROUP BY column_name(S)
HAVING condition
ORDER BY column_name(s);
```
## SQL HAVING Examples
The following SQL statemenmt lists the number of customers in each country. Only include countries with more than 5 customers.
```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) >5;
```
The following SQL  statement lists the number of customers in each country, sorted high to low(Only include countries with more than 5 customers):
```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) >5
ORDER BY COUNT(CustomerID) DESC;
```

## More Having examples
The following SQL statement lists the employees that have registered more than 10 orders.

```
SELECT Employees.LastName, COUT(Orders.OrderID) AS NumberOfOrders
FROM(Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)
GROUP BY LastName
HAVING COUNT(Orders.OrderID)>20;
```
##  SQL Statement

```
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
WHERE LastName ='Davolio' OR LastName ='Fuller'
GROUP BY LastName
HAVING COUNT(Orders.OrderID) >25;
```
