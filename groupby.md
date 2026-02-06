## sql group by statement
[group by](https://www.w3schools.com/sql/sql_groupby.asp)

## The SQL GROUP BY Statement
The `GROUP BY` statement groups rows that have the same values into summary rows, like "find the number of customers in each ountry"
The `GROUP BY` statement is oftern used with aggregate functions(`COUNT(), MAX(), MIN(), SUM(), AVG()`) to group the result-set by one or more columns.
## GROUP BY Syntax
```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
```
## The following SQL statement lists the number of customers in each country, sorted high to low:
```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;
```

GROUP BY With JOIN Example

## [菜鸟 SQL ](https://www.runoob.com/sql/sql-join-left.html)

```
SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders FROM Orders

LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID
GROUP BY ShipperName;
```
## SQL HAVING Clause 
