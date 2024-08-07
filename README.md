# SQL_Queries

# SHOW

```postgresql
SHOW DATABASES
```

It will show all the available databases.

```postgresql
USE {nameOfDatabase}
```

To select a particular database.

```postgresql
SHOW TABLES
```

To show all the table.In a selected database.

# CREATE

```postgresql
CREATE DATABASE {nameOfDatabase}
```

To create a database.

# CREATE TABLE

```postgresql
CREATE TABLE {tableName}
(
    {columname} {type} {constrants}

    id Integer primarykey,
    name varchar(100) NOTNULL,
    address varchar(250)
 );
```

It will create a table.

# DESC {table name}

It will show description of a table

# INSERT DATA

```postgresql
INSERT INTO TABLE {name} (id, name, address)
VALUES (1, "Akhlaq Ahmad", "kareli Ald");
```

Mapping will happen base on the column and value numbers. eg id=1

# SELECT

```postgresql
SELECT name, address
FROM {tableName};
```

It will select the name from the table and show it.

```postgresql
SELECT *
FROM {tableName};
```

It will select everything from the table.

# TABLE CONSTRAINTS

```postgresql
CREATE TABLE {tableName}
(
    {columname} {type} {constrants}
                ______________________
                  constraints
    id Integer primarykey NOTNULL,
    name varchar(100) UNIQUE NOT NULL,
    address varchar(250)
    );
```

constraints =>
default("user") : use to give default value to the colum

# Enum type

DB's support enums too.

{colum name} {Type}

gender ENUM("male","female")  //this is type of colums

# WHERE CLAUSE

```postgresql
SELECT name, age
FROM students
WHERE {any condition};
```

By using where clause you can manipulate data based on certain condition. U can also have multiple condition separated
by AND,OR,NOT etc. (just like the condition in if checks)

# LIKE

```postgresql
SELECT name
FROM table
WHERE name LIKE "%2";
```

It will select name where it will end with 2.

```postgresql
SELECT name
FROM table
WHERE name LIKE "2%";
```

It will select name where it will start with 2.

```postgresql
SELECT name
FROM table
WHERE name LIKE "%2%";
```

It will select name where 2 can be anywhere.

```postgresql
SELECT name
FROM table
WHERE name LIKE "_2%";
```

It will select name where 2 is the second character.

# OPERATORS

## CONDITIONAL OPERATORS

### OR

```postgresql
SELECT *
FROM table
WHERE {conditon 1} OR {conditon 2} OR {condition 3};
```

It will select data based on if anyone condition is fulfilled.
You can also add more or conditions.

### AND

```postgresql
SELECT *
FROM table
WHERE {conditon 1} AND {conditon 2} AND {condition 3};
```

It will select data based on if all the condition is fulfilled.

## RELATIONAL OPERATORS

### ">"

```postgresql
SELECT *
FROM table
WHERE age > 20
   OR status = "active"
   OR {condition 3};
```

You can use all the relational operators in where clause.

### "<="

```postgresql
SELECT *
FROM table
WHERE age <= 20
  AND status = "active"
  AND {condition 3};
```

You can use all the relational operators in where clause.

## NOT OPERATORS

```postgresql
SELECT *
FROM table
WHERE NOT gender = "others";
```

It will select all the data where gender is not others.

# ORDER

```postgresql
SELECT *
FROM table
ORDER BY name DESC;
```

It will select the data from table and order it by name in descending manner.
For ascending replace DESC with AESC.

# LIMIT

```postgresql
SELECT *
FROM table
WHERE location = "allahabad"
LIMIT 2;
```

It will limit the result set by only first two rows.

# OFFSET

```postgresql
SELECT *
FROM table
WHERE salary >= 10000
OFFSET 5;
```

It will leave the first 5 result and rest will be included in data set.

### LIMIT with OFFSET

```postgresql
SELECT *
FROM table
WHERE location = "deoria"
LIMIT 10 OFFSET 5;
```

It will leave first 5 results and consider only the next 10 after that.

* Q=> select 2 employs with minimal salary in reverse name order(Z->A) and
  age <= 20?

```postgresql
SELECT *
FROM table
WHERE age <= 20
ORDER BY salary DESC
LIMIT 2;
```

# DELETE

### DELETE A ROW

```postgresql
DELETE
FROM table
WHERE {condition };
```

It will delete the table row base on the condition.

```postgresql
DELETE
FROM table
WHERE name LIKE "%e%";
```

### DElETE A FULL TABLE DATA

```postgresql
DELETE
FROM table;
```

It will delete all data in a table.

# UPDATE

### UPDATE COLUMN

```postgresql
UPDATE table
SET {col1= value}, {col2= value}
WHERE {condition};
```

It will update the colum of a particular table base on the condition.

### ALTER STRUCTURE OF TABLE

#### UPDATE

```postgresql
ALTER TABLE {tablename} CHANGE {oldcolname} {newcolname} {datatype and constraints};
```

It will alter the structure of the table. Change column name,data type.

#### ADD

```postgresql
ALTER TABLE
    {tablename} ADD {newcolname} {datatype and constraints}};
```

By using this u can add new columns in the table.

```postgresql
ALTER TABLE table
    ADD age varchar(10) default ("230");
```

# GROUPBY AND HAVING

```postgresql
SELECT name, count(name)
FROM table
GROUP BY area
HAVING pincode > 211016;
```

This will group the table and make a diff table.

# JOINS

### INNER JOIN (default)

```postgresql
SELECT name, age
FROM table1
         INNER JOIN table2 ON {condition};
```

It will show the common data between the two tables.

* Means it will take only things that are matched base on the condition
  and rest is ignored. (only columns from both table that match the condition)

### OUTER JOIN

```postgresql
SELECT name, age
FROM table1
         FULL OUTER JOIN table2 ON table1.fr = table2.user_id
```

It will show all the data that is between the two tables.

* Means it will show data of both tables and missing data will be replaced by NULL.

### LEFT JOIN

```postgresql
SELECT name, id
FROM table1
         LEFT JOIN table2 ON table.id == table.fr
```

Everything will be included from table that is on the left(table1) and only matching from right table. Missing data will be replaced by NULL

### RIGHT JOIN

```postgresql
SELECT name, id
FROM table1
         RIGHT JOIN table2 ON table.id == table.fr
```

Everything will be included from table that is on the right(table2) and only matching from left table. Missing data will be replaced by NULL