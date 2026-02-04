# SQL LIKE Operator
[sql-operator](https://www.w3schools.com/sql/sql_like.asp)

## The SQL LIKE Operator
The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.


There are two wildcards often used in conjuction with the `LIKE` operator.

- The percent sign `%` represents zero, one , or multiple characters
- The underscore sign `_` represents one ,single character


```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%';
```

Syntax
```
SELECT column1, column2, ...
FROM table_name
WHERE column LIKE pattern;

```
## The _ Wildcard
The `_` wildcard represents a single character.
It can be any character or number, but each `_` represents one, and only one , character.
```
SELECT * FROM Customers
WHERE City LIKT `L_nd__`;
```
## The % Wildcard
The `%` wildcard represents any number of characters,even zero characters.

```
SELECT * FROM Customers
WHERE city LIKE `%L%`
```
## Start With
To return records that starts with a specific letter or phrase, add the `%` at the end of the letter or phrase.

```
SELECT * FROM Customers
WHERE CustomerName LIKE `La%`;
```

Tip: You can also combine any number of conditions using `AND` or `OR` operators.

Example
## Return all customers that starts with `a` or starts with `b`:

```
SELECT * FROM Customers
WHERE CustomerName LIKE `a%` OR CustomerName LIKE `B%`
```
## Ends With
To return records that ends with a specific letter or phrase, add the `%` at the beginning of the letter or phrase.

```
SELECT * FROM Customers
WHERE CustomerName LIKE `%a`;
```
## Tips: You can also combine "starts with " and "ends with"

```
SELECT * FROM Customers
WHERE CustomerName LIKE `b%s`;
```
## Contains
To return records that contains a specific letter or phrase, add the `%` both before and after the letter or phrase

## Example
Return all customers that contains the phrase `or`
```
SELECT * FROM Customers
WHERE CustomerName LIKE `%or&`;
```
## Combine Wildcards
**Any wildcard** like `%` and `_`, can be used in combination with other wildcards.

## Return all customers that starts with "a`and are at least 3 characters in length:
```
SELECT * FROM Customers
WHERE CustomerName LIKE `a___%;
```

## Return all customers that have "r" in the second position.
```
SELECT * FROM Customers
WHERE CustomerName LIKE '_r%';
```
## Without Wildcard
If on wildcard is specified, the phrase has to have an exact match to return a result.

```
SELECT * FROM Customers
WHERE Country LIKE 'Spain';
```

## SQL Wildcards

[SQL Wildcard Characters](https://www.w3schools.com/sql/sql_wildcards.asp)

A wildcard character is used to `substitute` one or more characters in a string.

Wildcard characters are used with the `LIKE` operator. The 

## Wild Characters
|Symbol|Description|
|------|-----------|
|%     | Represents zero or more characters|
|_    |Represents a single character|
| []| Represents any single character within the brackets*|
|^    | Represents any character not in the brackets *|
|-  | Represents any single character within the specified range *|
| {}| Represents any escaped character ** |

* Not suported in PostgreSQL and MySQL databases.
** Supported only in Oracle databases.

## Using the % Wildcard 
The `%` wildcard represents any number of characters, even zero characters.

```
SELECT * FROM Customers
WHERE CustomerName LIKE `%es`;
```
## Example
Return all customers that contains the pattern 'mer`;
```
SELECT * FROM Customers
WHERE CustomerName LIKE `%mer%`
```

## Using the _ Wildcard
The `_`wildcard represents a single character.
It can be any character or number, but each`_` represents one, and only one 

## Example
Returns all customers with a `city` starting with any character, followed by "ondon"
```
SELECT * FROM Customers
WHERE City LIKE '_ONDON`;
```

## Using the []Wildcard
The ```[]``` wildcard returns a result if ```any``` of the characters inside gets a match.

## Example
Returns all customers starting with either "b","s", or "p":
```
SELECT * FROM Customers
WHERE CustomerName LIKE `[BSP]%`;
```
## Using the - Wildcard

The `-`wildcard allows you to specify a range of characters inside the `[]` wildcard.

## example
Returns all customers starting with "a","b","c","d","e",or "f":\
## Combine Wildcards
Any wildcard,like `%` and `-` ,can be used in combination with other wildcards.

Example: return all customers that start with "a” and are ** least 3 
characters in length

```
SELECT * FROM Customers
WHERE CustomerName LIKE 'A___%';
```


## Example 
Return all customers that have "r" in the second position:
```
SELECT * FROM Customers
WHERE CustomerName LIKE '_R%';
```


## WITHout Wildcard
If no wildcard is specified,the phrase has to have an exact match to return a result.

Microsoft Access Wildcards
The Microsoft Access Database has some other wildcards:

Symbol	Description	Example
*	Represents zero or more characters	bl* finds bl, black, blue, and blob
?	Represents a single character	h?t finds hot, hat, and hit
[]	Represents any single character within the brackets	h[oa]t finds hot and hat, but not hit
!	Represents any character not in the brackets	h[!oa]t finds hit, but not hot and hat
-	Represents any single character within the specified range	c[a-b]t finds cat and cbt
#	Represents any single numeric character	2#5 finds 205, 215, 225, 235, 245, 255, 265, 275, 285, and 295

## SQL IN Operator
The SQL in Operator
The SQL In Operator 
The `IN` operator allows you to specify multiple values in a `WHERE` clause.
THe `IN`operator is a shorthand for multiple `OR` conditions

```
SELECT * FROM Customers
WHERE Country IN（'German','France','UK'）;
```
## Syntax
SELECT column_name(s)
FROM table_name
WHERE column_name IN(value1,value2,...);

## NOT IN 
By using the `NOT` keyword in front of the `IN` operator, you return all records that are `NOT` any of the values in the list 

```
SELECT * FROM Customers
WHERE Country NOT IN ('Germany','France','uk');
```


IN(SELECT)
You can also use `IN` with a subquery in the `WHERE`clause.

**tips** With a subquery you can return all records from the main query that are present in the result of the subquery.

## Example 
Return all customers that have an order in the `Orders` table:

```
SELECT * FROM Customers
WHERE CustomerID IN (SELECT CustomerID FROM Orders);
```
## NOT IN (SELECT)
The result in the example above returned 74 records, that means that there are 17 customers that haven't placed any orders.
Let us check if that is correct, by using the `NOT IN ` operator

```
SELECT * FROM Customers
WHERE CustomerID NOT IN (SELECT CustomerID FROM Orders);
```
## SQL Between Operator

The SQL BETWEEN Operator
THE `BETWEEN` operator selects values within a given range. The values can be numbers, text, or dates.
The `BETWEEN` operator is inclusive: begin and end values are included.

## Example
Selects all products with a price between 10 and 20:
```
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 30;
```
## Syntax
```
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

## NOT BETWEEN
To display the produts outside the range of the previous example, use `NOT BETWEEN`

```
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

BETWEEN with IN
The following SQL statement selects all products with a price between 10 and 20. In addition, the CategoryID must be either 1,2, or 3.

```
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID IN (1,2,3);
```
## BETWEEN Text Values
The following SQL statement selects all prodcuts with a ProductName alphabetically between Carnarvon Tigers and Mozzarella di Giovanni

```
SELECT * FROM Products
WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'
ORDER BY ProductName;
```
## The following SQL statement selects all products with a ProductName  between Carnarvon Tigers and Chef Anton's Cajun Seasoning:
```
SELECT * FROM Products
WHERE ProductName BETWEEN "Carnarvon Tigers" AND "Chef Anton's Cajun Seasoning"
ORDER BY ProductName
```

## NOT BETWEEN Text Values
The following SQL statement selects all products with a ProductName not between Carnarvon Tigers and Mozzarella di Giovanni:
```
SELECT * FROM Products
WHERE ProductsName NOT BETWEEN 'carnarvon Tigers ' AND 'Mozzarella di Giovanni'
ORDER BY ProductName;
```
## Between Dates
The following SQL statement selects all orders with an OrderDate between '01-JULY-1996' and '31-july-1998'
```
SELECT * FROM Orders
WHERE OrderDate BETWEEN #07/01/1996# AND #07/31/1996#
```
## SQL Aliases
[SQL Aliases](https://www.w3schools.com/sql/sql_alias.asp)

## SQL Aliases
SQL aliases are used to give a table, or a column in a table, a 
temporaty name.
Aliases are often used to make column names more readable.
An alias only exists for the duration of that query.
An alias is created with the `AS` keyword.

```
SELECT CustomerID AS ID
FROM Customers;
```

## AS is Optional
Actually, in most database languages, you can skip the and get the same result:
## example
```
SELECT CustomerID ID
FROM Customers;
```

## Syntax
When alias is used on column:
```
SELECT column_name AS alias_name
FROM table_name;
```
When alias is used on table:
```
SELECT column_name(s)
FROM table_name AS alias_name;
```
## Alias for Columns
The following SQL statement creates two aliases,one for the CustomerID column and one for the CustomerName column:
```
SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;
```
## Using Aliases With a Space Character
If you want your alias to contain one or more spaces, like "My Great Products",surround your alias with square brackets or double quotes.

```
SELECT ProductName AS [My Great Produts]
FROM Products
```

## or Using "double quotes" for aliases with space characters:
```
SELECT ProductName AS "My Great Products"
FROM Products
```
***NOTE*** Some database systems allows both [] and "", and some only allows one of them.

## Concatenate Columns
 The following SQL statement creates an alias named "Address" that combine four columns 
 ```
 SELECT CustomerName, Address + ', ' +PostalCode + ' ' + City + ', ' + Country AS
 Address

 FROM Customers;
 ```

 ## MySQL Example
 ```
 SELECT CustomerName, CONCAT(Address, ', ',PostalCode, ', ',City,', ',Country)
 AS Address
 FROM Customers;
 ```
 ## Oracle Example
 ```
 SELECT CustomerName, (Address || ', ' || PostalCode || ' '|| City || ',' ||Country)
 AS Address
 FROM Customers;
 ```
 ## Alias for Tables
 The same rules applies when you want to use an alias for a table.
 
 Example 
 Refer to the Customers table as Persons instead:
 ```
 SELECT * FROM Customers AS Persons;

 
 ```

 ## Useful
 It might seem useless to use aliases on tables, but when you are using more than one table in your queries, it can make the SQL statement shorter.
 The following SQL statement selects all the orders from the customer with CustomerID =4 (Around the Horn). We use the "Customers" and "Orders" tables, and give them the table aliases of "c" and "o" respectively (Here we use aliases to make the SQL shorter):

 SQL Statement
 ```
 SELECT o.OrderID, o.OrderID, c.CusomerName
 FROM Customers AS c, Orders AS o
 WHERE c.CustomerName='Around the Horn' AND c.CustomerID=o.CustomerID;
 ```

 ## Aliases can be useful when:
 - There are more than one table involved in a query
 - Functinos are used in the query
 - Column names are big or not very readable
 - Two or more columns are combined together
 ![alt text](image.png)

 ## SQL Joins
 [SQL Joins](https://www.w3schools.com/sql/sql_join.asp)

 ## SQL JOIN 
 A `JOIN` clause is used to combine rows from two or more tables, based on a realated column betwwen them.

 Then, we can create the following SQL statement (that contains an `INNER JOIN`). that selects records that have matching values in both tables:
 ```
 SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
 FROM Orders
 INNER JOIN Customers
 ON Orders.CustomerID=Customers.CustomerID
 ```