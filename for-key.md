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