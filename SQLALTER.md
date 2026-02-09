# SQL ALTER TABLE Statement

THE `ALTER TABLE` statement is used to add, delete, or modify columns in an existing table.
The `ALTER TABLE` statement is also used to add an drop various constraints on an existing table.

## ALTER TABLE - ADD Column

to add a column in a table , use the following syntax:
```
ALTER TABLE table_name
ADD column_name datatype;
```
## The following SQL adds an "Email" column to the "Customers" table:
```
ALTER TABLE Customers
ADD Email varchar(255);
```
## ALTER TABLE - DROP COLUMN
To delete a column in a table, use the following syntax (notice that some database systems don't allow deleting a column)

```
ALTER TABLE table_name
DROP COLUMN column_name;
```

## The following SQL deletes the "Email" column from the "Customers" table:

```
ALTER TABLE Customers
DROP COLUMN Email;
```

## ALTER TABLE - RENAME COLUMN
To rename a column in a table, use the following syntax:
```
ALTER TABLE table_name
RENAME COLUMN old_name to new_name;
```
To rename a column in a table in SQL Server, use the following syntax:

## SQL Server:
```
EXEC sp_rename 'table_name.old_name', 'new_name', 'COLUMN';
```


## ALTER TABLE - ALTER/MODIFY DATATYPE
To change the data type of a column in a table, use the following syntax:
## SQL Server /MS Access:
```
ALTER TABLE table_name
ALTER COLUMN column_name datatype;
```
## My SQL/Oracle(prior version 10G):
```
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

## Oracle 10G and later:
```
ALTER TABLE table_name
MODIFY column_name datatype;
```

example:
## ADD tabble Persons

```
ALTER TABLE Persons
ADD DateOfBirth date;
```
## Change Date Type Example
Now we want to change the data type of the column named "DateOfBith" in the "Person" table
```
ALTER TABLE Persons
ALTER COLUMN DateOfBirth year;
```

## DROP COLUMN Example
```
ALTER TABLE Persons
DROP COLUMN DateOfBirth
```
## SQL Constraints
[SQL constraints are used to specify rules for data in a table.](https://www.w3schools.com/sql/sql_constraints.asp)

## SQL Create Constraints
Constaints can be specified when the table is created with the `
CREATE TABLE` statement, or after the table is created with the `ALTER TABLE` statement.
## Syntax
```
CREATE TABLE table_name(
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ...
);
```
## SQL Constraints
SQL constraints are used to specify rules for the data in a table.

Constraints can be column level or table level. Column level constraints apply to a column, and table level constrainst apply to the whole table.

## The following constriants are commonly used in SQL:
- NOT NULL -Ensures that a column cannot have a NULL value.
- UNIQUE -Ensures that all values in a column are different
- PRIMARY KEY - A combination of a `NOT NULL` AND `UNIQUE`.Uniquely indentifies each row in a table.
- FOREIGN KEY - Prevents actions that would destroy links between tables.
- CHECK - Ensures that the values in a columnh satisfies a specific condition
- `DEFAULT` - Sets a default VALUE FOR a column if no value is specified
- `CREATE INDEX` - Used to create and retrieve data from the database very quickly\

## SQL NOT NULL Constraint 
[null constraint](https://www.w3schools.com/sql/sql_notnull.asp)

## By default, a column can hold NULL values.
The `NOT NULL` constraint enforces a column to NOT accept NULL values.

## SQL NOT NULL on CREATE TABLE 
The following SQL ensures that the columns will not accept NULL values when the "Persons" table is created:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

## SQL NOT NULL on ALTER TABLE
To create a `NOT NULL` constraint on the "Age" column when the "Persons" table is already created, use the following SQL:
## SQL Server/MS Access:
```
ALTLER TABLE Persons
ALTER COLUMN Age int NOT NULL;
```
## MY SQL /Oracle (prior version 10G):
```
ALTER TABLE Persons
MODIFY COLUMN Age int NOT NULL;
```

## Oracle 10G and later:
```
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

