
## What is a NULL Value?
A field with a NULL value is a field with no value.
If a field in a table is optional,it is possible to insert a new record or update a  record without adding a value to this field.
Then, the field will be saved with a NULL value.

Note: A NULL value is different from a zero value or a field that 
contains spaces. A field with a NULL value is ont that has been
left blank during record creation!

## How to test fro NULL Values?
It is not possible to test NULL values with comparison operators.
such as =,<, or <>.
We will have to use the `IS NULL ` and `IS NOT NULL ` operators instead.

## IS NULL Syntax
```
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```
## IS NOT NULL SYNTAX
```
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```
## The IS NULL Operator
The `IS NULL ` operator is used to test for empty values (NULL values).
The following SQL lists all customers with a NULL value in the "Address" field:
```
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
```
## Tips Always use IS NULL to look for NULL values.

## The IS NOT NULL Operator
The `IS NOT NULL ` operator is used to test for non-empty values(NOT NULL values.)
The following SQL lists all customers with a value in the "Address" field:
```
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```

## SQL UPDATE Statement

## The SQL UPDATE Statement

The `UPDATE` statement is used to modify the existing records in a table.
## UPDATE Syntax

```
UPDATE table_name
SET column1 =value1,column2 =value2, ...
WHERE condition；
```