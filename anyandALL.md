# SQL ANY and ALL Operators
## The SQL ANY and ALL Operators
The  `ANY` and `ALL` operators allow you to perform a comparison between a single column value and a range of other values.

## The SQL ANY Operator 
The `ANY` operator:
- returns a boolean value as a result
- returns TRUE if ANY of the subquery values meet the condition.
`ANY` means that the condition will be true if the operation is true for any of the values in  the range.
## ANY Syntax
```
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
(SELECT column_name
FROM table_name
WHERE condition);
```

## Note: 
The operator must be a standard comparison operator(=, <>,!=,>,>=,<,or <=).


## The SQL ALL Operator
The `ALL` operator
- returns a boolean value as a result
- returns TRUE if ALL of the subquery values meet the conditon
- is used with `SELECT`,`WHERE` and `HAVING` statements
`ALL` means that the conditon will be true only if the operation is true for all values in the range.

ALL Syntax With SELECT

```
SELECT ALL column_name(s)
FROM table_name
WHERE condition;
```
## ALL Syntax With WHERE OR HAVING
```
SELECT column_name(s)
FROM table_name 
WHERE column_name operator ALL
   (SELECT column_name
   FROM table_bame
   WHERE condition);
```

***NOTE*** The operator must be a standard comparison operatro(=,<>,!=,>,>=,<,or <=).

example:
```
SELECT ProductName
FROM Products
WHERE Product = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);
```


## The following SQL statement lists the ProductName if it finds ANY records
IN the OrderDetails table has Quantity larger than 99 (this will return TRURE because the Quantity column has some values larger than 99):
```
SELECT ProductName
FROM Products
WHERE ProductID = ANY(SELECT ProductID FROM OrderDetails WHERE Quantity >99);

```

## SQL ALL Examples
The following SQL statement lists ALL the product names:
```
SELECT ALL ProductName
FROM Products
WHERE TRUE;
```