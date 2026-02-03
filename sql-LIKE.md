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
