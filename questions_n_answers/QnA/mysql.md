# MySQL

## Differentiate between FLOAT and DOUBLE? 
Following are differences for `FLOAT` and `DOUBLE`:
- Floating point numbers are stored in `FLOAT` with eight place accuracy and it has four bytes.
- Floating point numbers are stored in `DOUBLE` with accuracy of 18 places and it has eight bytes.

## Differentiate CHAR_LENGTH and LENGTH?
`CHAR_LENGTH` is character count whereas the `LENGTH` is byte count. The numbers are same for Latin characters but they are different for Unicode and other encodings.

## Difference between CHAR and VARCHAR? 
Following are the differences between `CHAR` and `VARCHAR`:
- `CHAR` and `VARCHAR` types differ in storage and retrieval.
- `CHAR` column length is fixed to the length that is declared while creating table. The length value ranges from 1 and 255.
- When `CHAR` values are stored then they are right padded using spaces to specific length. Trailing spaces are removed when `CHAR` values are retrieved.

## What is the difference between primary key and candidate key?

Every row of a table is identified uniquely by __primary key__. There is only one __primary key__ for a table.

__Primary Key is also a candidate key__. By common convention, candidate key can be designated as primary and which can be used for any foreign key references.

## What is the difference between mysql_fetch_array and mysql_fetch_object?

Following are the differences between `mysql_fetch_array` and `mysql_fetch_object`:

- `mysql_fetch_array`: Returns a result row as an associated array or a regular array from database.

- `mysql_fetch_object`:  Returns a result row as object from database.