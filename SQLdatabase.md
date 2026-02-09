
## SQL CREATE DATABASE Statement

```CREATE DATABASE``` statement is used to create a new SQL  database.
## Syntax
```
CREATE DATABASE  databasename
```
## example
The following `SQL` statement creates a database called "testDB";
``` 
CREATE DATABASE  testDB;
```

**TIP** :
Make sure you have admin privilege  before creating any database.
Once a database is created. You can check it in the list of 
databases with the following SQL command:
```SHOW DATABASES```;

## SQL DROP DAATABASE STATEMENT

THE `DROP DATABASE` statement is used to drop an existing SQL database.

## Syntax
```
DROP DATABASE databasename;
```
**Note** : Be careful before dropping a database.
Deleting a database will result in loss of complete information stored 
in a database!

## Example
## The following SQL statement drops the existing database "testDB"
```
DROP DATABASE testDB;
```

**Tip**:
Make sure you have admin privilege before dropping any database.
Once a database is drooped, you can check it in the list of database
with the following SQL command: ``` SHOW DATABASES```:

## SQL BACKUP DATABASE FOR SQL Server

the SQL backup database statement

The `Backup DATABASE` statement is used in SQL Server to create a full
back up of an existing SQL database.

## Syntax
```
BACKUP DATABASE databasename
TO DISK = 'filepath';
```
## The SQL BACKUP WITH DIFFERENTIAL Statement
A  differential back up only backs up the parts of the database that
have changed since the last full database backup.

## Syntax
```
BACKUP DATABASE databasename
TO DISK = 'filepath'
WITH DIFFERENTIAL;
```
## BACKUP DADTABASE Example

The following SQL statement creates a full back up of the existing database "testDB"
to the 'D' disk:
```
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak';
```
Tip:
Always back up the database to a different drive than the actual database. 
Then, if you get a disk crash, you will not lose your backup file along with the
database.


## DIFFERENTIAL Example
```
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak'
WITH DIFFERENTIAL;
```
## tip: A differential back up reduces the back up time (since only the changes are 
backed up).

