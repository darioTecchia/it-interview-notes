# SQL

## Key Types
- `PRIMARY KEY`: The `PRIMARY KEY` constraint uniquely identifies each record in a table. It must contain UNIQUE values, and cannot contain `NULL` values.
- `UNIQUE`: The `UNIQUE` constraint ensures that all values in a column are different, and can contain `NULL` values.
- `COLUMN INDEX`: Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.
- `FULLTEXT`: Used to speed up searches inside text fields.
- `FOREIGN KEY`: The `FOREIGN KEY` constraint is used to prevent actions that would destroy links between tables. A `FOREIGN KEY` is a field (or collection of fields) in one table, that refers to the `PRIMARY KEY` in another table.

> Note: Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

### Referential integrity of mysql foreign keys rules
1. Each element in the secondary table must correspond to an element in the primary table.
2. In case of deletion or modification of data in the primary table there must be a corresponding action in the secondary table.

## JOIN
A `JOIN` clause is used to combine rows from two or more tables, based on a related column between them.

Here are the different types of the JOINs in SQL:
<center>

  ![joins](assets/sql/joins.jpg "joins")

</center>

### (INNER) JOIN
Returns records that have matching values in both tables.

#### Example
"__Orders__" table:
|OrderID|CustomerID|EmployeeID|OrderDate|ShipperID|
|-|-|-|-|-|
|10308|2|7|1996-09-18|3|
|10309|37|3|1996-09-19|1|
|10310|77|8|1996-09-20|2|


"__Customers__" table:
|CustomerID|CustomerName|ContactName|Address|City|PostalCode|Country|
|-|-|-|-|-|-|-|
|1|Alfreds Futterkiste|Maria Anders|Obere Str. 57|Berlin|12209|Germany|
|2|Ana Trujillo Emparedados y helados|Ana Trujillo|Avda. de la Constitución 2222|México D.F.|05021|Mexico|
|3|Antonio Moreno Taquería|Antonio Moreno|Mataderos 2312|México D.F.|05023|Mexico|

```SQL
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID
LIMIT 4;

```

__Result__:
|OrderID|CustomerName|
|-|-|
|10248|Wilman Kala|
|10249|Tradição Hipermercados|
|10250|Hanari Carnes|
|10251|Victuailles en stock|

### LEFT (OUTER) JOIN
Returns all records from the left table, and the matched records from the right table. The result is 0 records from the right side, if there is no match.

#### Example
"__Customers__" table:
|CustomerID|CustomerName|ContactName|Address|City|PostalCode|Country|
|-|-|-|-|-|-|-|
|1|Alfreds Futterkiste|Maria Anders|Obere Str. 57|Berlin|12209|Germany|
|2|Ana Trujillo Emparedados y helados|Ana Trujillo|Avda. de la Constitución 2222|México D.F.|05021|Mexico|
|3|Antonio Moreno Taquería|Antonio Moreno|Mataderos 2312|México D.F.|05023|Mexico|

"__Orders__" table:
|OrderID|CustomerID|EmployeeID|OrderDate|ShipperID|
|-|-|-|-|-|
|10308|2|7|1996-09-18|3|
|10309|37|3|1996-09-19|1|
|10310|77|8|1996-09-20|2|

```SQL
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerName;
```

__Result__:
|CustomerName|OrderID|
|-|-|
|Alfreds Futterkiste|null|
|Ana Trujillo Emparedados y helados|10308|
|Antonio Moreno Taquería|10365|
|Around the Horn|10355|

### RIGHT (OUTER) JOIN
Returns all records from the right table, and the matched records from the left table. The result is 0 records from the left side, if there is no match.

#### Example
"__Orders__" table:
|OrderID|CustomerID|EmployeeID|OrderDate|ShipperID|
|-|-|-|-|-|
|10308|2|7|1996-09-18|3|
|10309|37|3|1996-09-19|1|
|10310|77|8|1996-09-20|2|

"__Employee__" table:
|EmployeeID|LastName|FirstName|BirthDate|Photo|
|-|-|-|-|-|
|1|Davolio|Nancy|12/8/1968|EmpID1.pic|
|2|Fuller|Andrew|2/19/1952|EmpID2.pic|
|3|Leverling|Janet|8/30/1963|EmpID3.pic|

```SQL
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```

__Result__:
|OrderID|LastName|FirstName|
|-|-|-|
||West|Adam|
|10248|Buchanan|Steven|
|10249|Suyama|Michael|
|10250|Peacock|Margaret|

### FULL (OUTER) JOIN
Returns all records when there is a match in either left or right table. Tip: `FULL OUTER JOIN` and `FULL JOIN` are the same.

"__Customers__" table:

|CustomerID|CustomerName|ContactName|Address|City|PostalCode|Country|
|--- |--- |--- |--- |--- |--- |--- |
|1|Alfreds Futterkiste|Maria Anders|Obere Str. 57|Berlin|12209|Germany|
|2|Ana Trujillo Emparedados y helados|Ana Trujillo|Avda. de la Constitución 2222|México D.F.|05021|Mexico|
|3|Antonio Moreno Taquería|Antonio Moreno|Mataderos 2312|México D.F.|05023|Mexico|

"__Orders__" table:
|OrderID|CustomerID|EmployeeID|OrderDate|ShipperID|
|--- |--- |--- |--- |--- |
|10308|2|7|1996-09-18|3|
|10309|37|3|1996-09-19|1|
|10310|77|8|1996-09-20|2|

```SQL
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```
__Result__:
|CustomerName|OrderID|
|--- |--- |
|Null|10309|
|Null|10310|
|Alfreds Futterkiste|Null|
|Ana Trujillo Emparedados y helados|10308|
|Antonio Moreno Taquería|Null|

> Note: The `FULL OUTER JOIN` keyword returns all matching records from both tables whether the other table matches or not. So, if there are rows in "Customers" that do not have matches in "Orders", or if there are rows in "Orders" that do not have matches in "Customers", those rows will be listed as well.

## Aggregation functions and UNION
### Aggregation functions
Among the __aggregation functions__, we find:
- `COUNT`: returns the number of elements;
- `COUNT (DISTINCT)`: variant of `COUNT` that considers duplicate values only once;
- `MAX`: returns the maximum value of the set;
- `MIN`: returns the minimum value of the set;
- `AVG`: returns the average value of the set;
- `SUM`: sums the values.

### UNION clause
The `UNION` clause is used to merge the results of two queries.

In order for this to work it is necessary that the projections of the two `SELECT`s involved are composed of the same number of fields, and that the data types of the same are compatible with the corresponding ones in the other query.

Example:
```SQL
SELECT description, total FROM data
UNION
SELECT description, total FROM archived_data
```

> Instead of `UNION` you can use `UNION ALL`, which will also show duplicate values, while `UNION`'s default behavior does not.

## MySQL subquery
A subquery is nothing more than a `SELECT` within another statement. Subqueries can also be nested to considerable depths.

We have already seen that every `SELECT` logically returns a table made up of rows and columns. In the case of subqueries it is necessary to make a distinction: they can return a __single value (scalar)__, a __single row__, a __single column__, or a normal table. The different types of subqueries can be found in different points of the instruction.

## Single Value
```SQL
SELECT column1
FROM t1
WHERE column1 = (SELECT MAX(column2) FROM t2);
```

## Single Column
When a subquery returns a column, it can be used to make comparisons through the `ANY`, `SOME`, `IN` and `ALL` operators:

```sql
SELECT s1 FROM t1 WHERE s1 > ANY (SELECT s1 FROM t2);
SELECT s1 FROM t1 WHERE s1 IN (SELECT s1 FROM t2);
```

The first query means "_select from t1 the values of s1 that are greater than at least 1 of the values of s1 on t2_". The second query selects the values of s1 that are equal to __at least 1__ of the values of s1 on t2. "IN" is synonymous with "`= ANY`". "`SOME`" is equivalent to "`ANY`".

```sql
SELECT s1 FROM t1 WHERE s1 > ALL (SELECT s1 FROM t2);
```

The meaning here is "_select from t1 the values of s1 that are greater than all the values of s1 on t2_". The "`NOT IN`" clause is equivalent to "`<> ALL`".

## Single Row (Multiple Columns)
When a subquery returns a single row, it can be used to make comparisons through __row constructors__:

```sql
SELECT column1, column2
FROM t1
WHERE (column1, column2)
IN (SELECT column1, column2 FROM t2);
```

This query extracts the rows of t1 where the values of column1 and column2 are repeated in a row of t2. The expression "`(column1, column2)`" is, in fact, a row constructor, which could also be expressed as "`ROW(column1, column2)`".

## Transactions and Locks
A __lock__ can be requested in reading or writing: in the first case the table cannot be used in writing but only in reading, in the second case the lock prevents any kind of access.

```sql
LOCK TABLES tabella [AS alias] {READ [LOCAL] | [LOW_PRIORITY] WRITE} [, tabella [AS alias] {READ [LOCAL] | [LOW_PRIORITY] WRITE}] ...
---
UNLOCK TABLES
```

The use of __transactions__ allows us to "consolidate" changes to the database only at a very specific time: from the moment we start a transaction, updates remain suspended (and invisible to other users) until we confirm them (__commit__); as an alternative to confirmation, it is possible to cancel them (__rollback__).
```sql
START TRANSACTION
... update instructions (1) ...
SAVEPOINT sp1;
... update instructions (2) ...
ROLLBACK TO SAVEPOINT sp1;
... update instructions (3) ...
COMMIT
```

## Views
In SQL, a view is a virtual table based on the result-set of an SQL statement.

A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

You can add SQL statements and functions to a view and present the data as if the data were coming from one single table.

A view is created with the `CREATE VIEW` statement. 

## Stored Procedures e Stored Functions
A __stored procedure__ is a set of SQL statements that are stored in the server with a name that identifies them; this name allows you to later re-execute the set of statements by simply referring to it.

__Stored functions__ are similar to stored procedures, but they have a simpler purpose, that is to define real functions, like those already provided by MySQL. They return a value, and therefore cannot return resultsets, unlike stored procedures.

## Trigger
__Triggers__ are objects associated with tables, which are triggered when a certain event occurs in relation to that table. We will then have the following types of triggers:
- `BEFORE INSERT`
- `BEFORE UPDATE`
- `BEFORE DELETE`
- `AFTER INSERT`
- `AFTER UPDATE`
- `AFTER DELETE`

The trigger will establish an instruction (or a series of instructions) that will be executed for each row affected by the event.

> The trigger is associated with a table, but it is part of a database, so its name must be unique within the db itself.