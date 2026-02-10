
sql working with dates 


## sql dates
```
the most difficult part when working with dates is to be sure that the format of the 
date you are trying to insert, matches the format of the date column in the database.
```
##  sql date data types
## MySQL comes with the following data types for storing a date or a date/time value in the 
database
- DATE -format YYYY-MM-DD
- DATETIME -format: YYYY-MM-DD HH:MI:SS
- TIMESTAMP -format:YYYY-MM-DD HH:MI:SS
- YEAR -format YYYY or YY

## SQL SERver comes with the following data types for storing a date or a date/time value in 
the database:
- DATE - format YYYY-MM-DD
- DATETIME -format:YYYY-MM-DD HH:MI:SS
- SMALLDATETIME -format : YYYY-MM-DD HH:MI:SS
- TIMESTAMP -format: a unique number
**note** the data types are chosen for a column when you create a new table in your database!
##
SQL Working with Dates

Look at the following table:

## SQL Views
[SQL views](https://www.w3schools.com/sql/sql_view.asp)

## SQL CREATE VIEW Statement
A view is created with the `CRETE VIEW` statement.
```
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
**NOTE** A view always shows up-to-date data! The database engine recreates the view,
every time a user queries it.
## SQL CREATE VIEW Examples
```
CREATE VIEW  [Brazil Customers] AS 
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = 'Brazil';
```
## We can query the view above as follows:
```
SELECT * FROM [Brazil Customers];
```
The following SQL creates a view that selects every product in the "Products"
table with a price higher than the average price:
```
CREATE VIEW [Products Above Average Price] AS 
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```
## we can query the view above as follows:
```
SELECT * FROM [Products Above Average Price];
```
## sql Updating a View
A view can be updated with the `CREATE OR REPLACE VIEW` statement.
## SQL CREATE OR REPLACE VIEW Syntax
```
CREATE OR REPLACE VIEW view_name AS
SELECT column1，column2, ...
FROM table_name
WHERE condition;
```
## The following SQL adds the "City" column to the "Brazil Customers" view;:
```
CREATE OR REPLACE VIEW [Brazil Customers] AS
SELECT CustomerName,ContactName,City
FROM Customers
WHERE Country ='Brazil';
```
## SQL DROPPING a VIEW
A view is deleted with the `DROP VIEW` statement.

## SQL DROP VIEW Syntax
```
DROP VIEW view_name;
```
The following SQL drops the "Brazil Customers" view:

## EXample
```
DROP VIEW [Brazil Customers];
```

## SQL Injection

- sql injection is a code injection technique that might destroy your database.
- sql injection is one of the most common web hacking techniques.
- sql injection is the placement of malicious code in SQL statements, via web page input.

the user gives you an sql statement that you will `unknowingly` run on your database.
`SELECT` statement by adding a variable (txtUserId)
```
txtUserId = getRequestString("UserId")
txtSQL ="SELECT * FROM Users WHERE UserID = " + txtUserId;
```
## SQL Hosting

[sql hosting](https://www.w3schools.com/sql/sql_hosting.asp)

If you want your web site to be able to store and retrieve data from a 
database, your web server should have access to a database-system that uses the `SQL`
Language.

If your web server is hosted by an Internal Service Provider(ISP), you will have to 
look for SQL hosting plans.

[SQL Data Types](https://www.w3schools.com/sql/sql_datatypes.asp)
