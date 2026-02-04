## SQL Not Operator

## The NOT Operator
The `NOT` operator is used in combination with other operators
to give the opposite result, also called the negative result.

In the select statement below we want to return all 
customers that are NOT from Spain.

```
SELECT * FROM Customers
WHERE NOT Country=`Spain`;
```

In the example above, the `NOT` operator is used in combination with
the `=` operator, but it can be used  in combination with other comparison and/ or logical operators. See examples below.

SELECT column1,column2,...
FROM table_name
WHERE NOT condition;

## sql not operator
[sql not operator](https://www.w3schools.com/sql/sql_not.asp)
