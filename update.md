# UPdate SQL 
[Update-SQL](https://www.w3schools.com/sql/sql_update.asp)

The SQL UPDATE Statement

## The `UPDATE` statement is used to modify the existing records in a table.
## UPDATE Syntax

```
UPDTAE table_name
SET column1=value1, column2=value2,...
WHERE condition;
```

## NOTE
```
Be Careful when updating records in a table! Notice the `WHERE` clause specifies which record(S) that should be updated, if you omit the `WHERE` clause, all records in the table will be updated!

```

## UPDATE Table
The following SQL statement updatas the first customer(CustommerID=1) with a new contact person ***and*** a new city.

```
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City='Frankfurt'
WHERE CustomerID =1;
```

## UPDATE Multiple Records
[Multiple Records](https://www.w3schools.com/sql/sql_update.asp)


It is the `Where` clause that determines how many records will be updated.
The following SQL statement will update the ContactName to "Juan" for all records where country is "Mexico":
```
UPDATE Customers
SET ContactName="Juan"
WHERE Country='Mexico';
```
## Update Warning!
```
Be careful when updating records. If you omit the `WHERE` clause,ALL records will be updated!
```
## example
```
UPDATE Customers
SET ContactName='Charles';
```
## SQL DELETE Statement

The sql delete STATEMENT
the `DELETE` statement is used to delete existing records in a table.

## DELETE Syntax
```
DELETE FROM table_name WHERE condition;
```
**Note**
Be careful when deleting records in a table! Notice the `WHERE` clause in the `DELETE ` statement.
The `Where` clause specifies which record(s) should be deleted. If you omit the `WHERE` clause, all records in the table will be deleted!

## SQL DELETE Example
The following SQL statement delets the customer "Alfreds Futterkiste" from the "Customers" table:
```
DELETE FROM Customers WHERE CustomerName='charles';
```

Delete All Records
It is possible to delete all rows in a table without deleting the table.
This means that the table structure, attributes,and indexes will be intact:
```
DELETE FROM table_name;
```
The following SQL statement deletes all rows in the "Customers" table, without deleting the table:
```
DELETE FROM Customers ;
```


