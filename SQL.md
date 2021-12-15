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

> Note: The FULL OUTER JOIN keyword returns all matching records from both tables whether the other table matches or not. So, if there are rows in "Customers" that do not have matches in "Orders", or if there are rows in "Orders" that do not have matches in "Customers", those rows will be listed as well.