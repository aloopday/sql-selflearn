## SQL UNIQUE Constraint
[unique](https://www.w3schools.com/sql/sql_unique.asp)

## SQL UNIQUE Constraint
The `UNIQUE` constraint ensures that all values in a column are different.
Both the `UNIQUE` and `PRIMARY KEY` constrs provide a guarantee for uniquenees for a column or set of columns.

***a `PRIMARY KEY`*** constraint automatically has a `UNIQUE` constraint.
**However, you can have many `UNIQUE` constraints per table, but only one `PRIMARY KEY` constraint per table.
## SQL UNIQUE Constraint on CREATE TABLE 
The following SQL creates a `UNIQUE` constraint on the 'id' column when then "Persons" table is created:
## SQL Server / Oracle /MS Access:
```
CREATE TABLE Persons(
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName  varchar(255),
    Age int
);
```
## mysql"
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE(ID)
);
```

## TO NAME A `  UNIQUE` constraint and to define a `UNIQUE` constraint on multiple columns,use the following SQL syntax:

## mysql/sql server/oracle/ms access:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT UC_Person UNIQUE (ID, LastName)
);
```

## SQL UNIQUE Constraint on ALTER TABLE
To careate a `UNIQUE` constraint on the "ID" column when the table is already created, use the following SQL:
## MYSQL / SQL SERVER / ORACLE /MS ACCESS:
```
ALTER TABLE Persons
ADD UNIQUE (ID);
```
TO name a `UNIQUE` constraint, and to defince a `UNIQUE` constraint on multiple columns, use the following SQL syntax:
## MYSQL/SQL SERVER/ORACLE/MS ASSESS:
```
ALTER TABLE Persons
ADD CONSTRAINT UC_Person UNIQUE (ID,LastName);
```
## DROP a UNIQUE Constraint
To drop a `UNIQUE` constraint, use the following SQL:
## MYSQL:
```
ALTER TABLE Persons
DROP INDEX UC_Person;
```
SQL Serever /Oracle/MS Access:
```
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```
## SQL PRIMARY KEY Constraint
[primary key constraint](https://www.w3schools.com/sql/sql_primarykey.asp)

## SQL PRIMARY KEY ConstrAINT
The `PRIMARY KEY` constraint is used to uniquely identify each record in a table.
Primary keys must contain unique values, and cannot contain NULL values.
Each table can have only ONE primary key. The primary key can be a single column or a combination of columns.

## SQL PRIMARY KEY on CREATE TABLE
The following SQL creates a `PRIMARY KEY` ON THE "ID" column when the "Persons" table is created:
## MYSQL:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY(ID)
);
```
## SQL Server/Oracle/MS Access:
```
CREATE TABLE Persons(
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```
## To define a `PRIMARY KEY` constraint on multiple columns, use the following SQL syntax:
## MySQL /SQL Server/Oracle /MS Access:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```
**Note**： If you use `ALTER TABLE` to add a primary key, the primary key column(S) must have been declared with NOT NULL, when the table was first created.
## DROP a PRIMARY KEY Constraint
To drop a `PRIMARY KEY` constraint, use the following SQL:
## mysql:
```
ALTER TABLE Persons
DROP PRIMARY KEY;
```
## sql server /Oracle / MS Access:
```
ALTER TABLE Persons
DROP CONSTRATNT PK_Person;
```
