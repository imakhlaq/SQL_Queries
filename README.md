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

    {
    colum
    name} {
    type} {
    constrants}

    id
    Integer
    primarykey,
    name
    varchar
(
    100
),
    address varchar
(
    250
)
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

    {
    colum
    name} {
    type} {
    constrants}
    __________________
    constraints
    id
    Integer
    primarykey
    NOT
    NULL,
    name
    varchar
(
    100
) UNIQUE NOT NULL,
    address varchar
(
    250
)
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

```postgresql
SELECT *
FROM table
WHERE age > 20
   OR status = "active"
   OR {condition 3};
```

You can use all the relational operators in where clause.

## NOT OPERATORS

```postgresql
SELECT *
FROM table
WHERE NOT gender = "others";
```

It will select all the data where gender is not others.