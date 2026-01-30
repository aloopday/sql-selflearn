# sql SUM() Function
[sql SUM](https://www.w3schools.com/sql/sql_sum.asp)

The `SUM()` function returns the total sum of a numeric column.
```
Retrun the sum of all `Quantity` fields in the `QrderDetails` table:
SELECT SUM(Quantity)
FROM OrderDetails
```
## syntax
```
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```
## ADD A WHERE Clause
YOU CAN  add a `WHERE ` clause to specify conditions:

```
Retrun the sum of the `Quantity` field for the product with `ProductID`11:
SELECT SUM(Quantity)
FROM OrderDetails
WHERE ProductId=11;
```
## Use an Alias
Give the summarized column a name by using the `AS` keyword.

```
SELECT SUM(Quantity) AS total
FROM OrderDetails;
```

## Use SUM() with GROUP BY
```
SELECT OrderID, SUM(Quantity) AS [Total Quantity]
FROM OrderDetails
GROUP BY OrderID
ORDER BY OrderID DESC;
```
## SUM() With an Expression
The parameter inside the `SUM()` function can also be an expression.

If we assume that each product in the `OrderDetails` column costs 10 dollars, we can find the total earnings in dollars by multiply each quatity with 10:

```
SELECT SUM(Quantity *10)
FROM OrderDetails;
```
## We can join the 
`OrderDetails` table to the `Products` table to find the actual amount, instead of assuming it is 10 dollars:

Example
```
Join `OrderDetails` with `Products`, and use `SUM()` fo find the total amount:
```
the syntax
```
SELECT SUM(Price * Quantity)
FROM OrderDetails
LEFT JOIN Products ON OrderDetails.ProductID=Products.ProductsID;
```
