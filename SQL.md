# SQL

## Key Types
- `PRIMARY KEY`: The `PRIMARY KEY` constraint uniquely identifies each record in a table. It must contain UNIQUE values, and cannot contain `NULL` values.
- `UNIQUE`: The `UNIQUE` constraint ensures that all values in a column are different, and can contain `NULL` values.
- `COLUMN INDEX`: Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.
> Note: Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.
- `FULLTEXT`: Used to speed up searches inside text fields.
- `FOREIGN KEY`: The `FOREIGN KEY` constraint is used to prevent actions that would destroy links between tables. A `FOREIGN KEY` is a field (or collection of fields) in one table, that refers to the `PRIMARY KEY` in another table.