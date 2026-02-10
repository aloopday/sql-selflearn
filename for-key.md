## SQL FOREIGN KEY Constraint
[sql forrign](https://www.w3schools.com/sql/sql_foreignkey.asp)

The `FOREIGN KEY` constraint is used to prevent actions that would destroy likks between tables.

A `FOREIGN KEY` IS A field(or collection of fields) in one table, that refers to `PRIMARY KEY` in another table.

"PRIMARY KEY" referenced table or parent table.
"FOREIGN KEY" is child table 

## The `FOREIGN KEY` constraint prevents invalid data from being inserted into the 
foreign key column, because it has to be one of the values contained in the parent table.
## SQL FOREIGN KEY on CREATE TABLE

## mysql:
```
CREATE TABLE Orders(
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERNCES Persons(PersonID)
);
```
## SQL Server/Oracle /MS Access:
```
CREATE TABLE Orders(
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```
To allow naming of a `FOREIGN KEY` constraint, and for defining a `FOREIGN KEY` constraint on multiple columns, use the following SQL syntax:
## mysql/sql server/oracle/msaccess:
```
CREATE TABLE Orders(
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```
## sql foreign key on ALTER TABLE
To create a ```FOREIGN KEY``` constraint on the "PersonID" COLUMN WHEN the "Orders" table is already created ,use the dfollowing SQL:
## MySQL /SQL Server/Oracle / MS Access:
```
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```
to allow naming of a ```FOREIGN KEY``` constraint, and for defining a ```FOREIGN KEY``` constraint on multiple columns, use the following SQL SYNTAX:

## mysql/sql 
[the check constraint](https://www.w3schools.com/sql/sql_check.asp)

## SQL CHECK Constraint
[CHECK Constraint](https://www.w3schools.com/sql/sql_check.asp)

The `CHECK` constraint is used to limit the value range that can be placed in a column.
If you define a `CHECK` constraint on a column it will allow only certain values for this column.
## If you define a `CHECK` constraint on a table it can limit the values in certian
columns based on values in other columns in the row.

## SQL CHECK on CREATE TABLE
The `CHECK` constraint ensures that the age of a person muste be 18, older:
## MySQL:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age >=18)
);
```
## SQL Server/Oracle/MS Access:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);
```

To allow naming of a `CHECK` constraint and for defining a `CHECK` constraint no multiple columns, use the following SQL syntax:
MYSQL /SQL SERVER/ ORACLE/MS Access:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```
## SQL CHECK on ALTER TABLE

## MYSQL/SQL SERVER /ORACLE/MS ACCESS:
```
ALTER TABLE Persons
ADD CHECK (Age>18);
```

To allow naming of a `CHECK` constraint and for defining a  'CHECK` constraint on multiple columns, use the follwing SQL syntax:
## MySQL/SQL Server/Oracle/MS Access
```
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City ='Hong Kong ');
```
## DROP a CHECK Constraint
sql server/oracle/ms access
```
ALTER TABLE Persons
DROP CONSTRAINT CHK_PersonAge;
```
## MySQL:
```
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```
## SQL DEFAULT Constraint
[default Constraint](https://www.w3schools.com/sql/sql_default.asp)

## The `DEFAULT` constraunit is used to set a default value for a column.
The default value will be added to all new records,if no other value is specified.
## SQL DEFAULT on CREATE TABLE
The following SQL sets a `DEFAULT` value for the ``
## my sql/sql server/ oracle/ms access:
```
CREATE TABLE Persons(
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'BEIJING`
);
```
## INSERT SYSTEM VALUES
```
CREATE TABLE Orders(
    ID int NOT NULL,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT GETDATE()
);
```
## SQL DEFAULT on ALTER TABLE
To create a `DEFAULT` constraint on the "city" column when the table is already created, use the following SQL:
## MYSQL:
```
ALTER TABLE Persons
ALTER City SET DEFAULT 'NEW YORK'
```
## sql sERVER
````
ALTER TABLE Persons
ADD CONSTRAINT de_City
DEFAULT 'HONGKONG' FRO City;
````
## MS ACCESS:
```
ALTER TABLE Persons
ALTER COLUMN City SET DEFAULT 'haikou';
```
## Oracle:
```
ALTER TABLE Persons
MODIFY City DEFULT  'NANCHANG';
```
## DROP a DEFAULT Constraint
To drop a `DEFAULT` constraint , use the following SQL:
## MYSQL":
```
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```
## SQL Server /Oracle/MS Access:
```
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```
## SQL CREATE INDEX Statement
[sql create index](https://www.w3schools.com/sql/sql_create_index.asp)

The `CREATE INDEX` statement is used to create indexed in tables.

notice: Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.
```
NOTE: Updating a table with indexes takes more time than updating a table without(because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.
```
## CREATE INDEX Syntax
Creates an index on a table. Duplicate values are allowed:
```
CREATE INDEX index_name
ON table_name (column1,colum2,...)
```

## CREATE UNIQUE INDEX Syntax
Creates a unique index on a table . Duplicate values are not allowed:
```
CREATE UNIQUE INDEX     index_name
ON table_name (column1, column2, ...)
```

If you want to create an index on a combination of columns, you can list the column names within the parenthese, separated by commas:
```
CREATE INDEX idx_pname
ON Persons (LastName, FirstName);
```
## DROP INDEX Statement
The `DROP INDEX` statement is used to delete an index in a table.
## DROP INDEX Statement 
ms access:
```
DROP INDEX index_name ON table_name;
```
SQL Server:
```
DROP INDEX table_name.index_name;
```
## DB2/Oracle:
```
DROP INDEX index_name;
```
## MySQL:
```
ALTER TABLE table_name
DROP INDEX index_name
```
## SQL AUTO INCREMENT Field
[SQL AUTO INCREMENT Field](https://www.w3schools.com/sql/sql_autoincrement.asp)

## AUTO INCREMENT Field
Auto-increment allows a unique number to be generated automatically when 
a new record is inserted into a table.
Often this is the primary key field that we would like to be created automatically every time a new record is inserted.
## Syntax for MySQL

```
CREATE TABLE Persons (
    Personid int NOT NULL AUTO_INCREMENT,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (Personid)
);
```
MySQL USES the `AUTO_INCREMENT` keyword to perform an auto-increment feature.
By default, the starting value for `AUTO_INCREMENT` is 1, and it will increment by q for each new record.
To let the `AUTO_INCREMENT` sequence start with another value, the following SQL statement:
```
ALTER TABLE Persons AUTO_INCREMENT=100;
```
To insert a new record into the "Persons" table,we will NOT have to specify a value fo the "Personid" column (a unique value will be added automatically):
```
INSERT INTO Persons （FirstName,LastName)
values('Lars','Monsen');
```
The "SQL " state,emt above would insert a new record into the "Persons" table.
The "Personid" column would be assigned a unique value. The "FirstName" column would be set to "Lars" and "LastName" column would be set to "Monsen".
## Syntax for SQL Server

The following SQL statement defines the "Personid"
```
CREATE TABLE Persons(
    Personid int IDENTITY(1,1) PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```
## Syntax for Access
```
CREATE TABLE Persons(
    Personid AUTOINCREMENT(10,5) PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```
## Syntax for Oracle
In Oracle the code is a little bit more tricky.
You will have to create an auto-increment field with the sequence object(this
object genereates a number sequence).
Use the following `CREATE SEQUENCE` syntax:
```
CREATE SEQUENCE seq_person
MINVALUE 1
START WITH 1
INCREMENT BY 1
CACHE 10;
```
iT WILL ALSO  cache up to 10 values for performance. The cache option specifies how many sequence values will be stored in memory for faster access.
To insert a new record into the "Persons" table, we will have to use the nextval function (this function retrieves the next value from seq_person sequence:0
)
```
INSERT INTO Persons （Personid,FirstName,LastName)
values(seq_person.nextval,'lars','Monsen');
