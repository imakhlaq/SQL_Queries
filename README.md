# SQL_Queries

# SHOW DATABASES

It will show all the available databases.

# USE {nameOfDatabase}

To select a particular database.

# SHOW TABLES

To show all the table.In a selected database.

# CREATE DATABASE {nameOfDatabase}

To create a database.

# CREATE TABLE {tableName}(

             {colum name} {type} {constrants}

               id      Integer primarykey,
               name    varchar(100),
              address  varchar(250)      );

It will create a table.

# DESC {table name}

It will show description of a table

# INSERT INTO TABLE {name} (id,name,address) VALUES(1,"Akhlaq Ahmad","kareli Ald")

Mapping will happen base on the column and value numbers. eg id=1

# SELECT name FROM {tableName};

It will select the name from the table and show it.

# SELECT * FROM {tableName}

It will select everything from the table.

# CREATE TABLE {tableName}(

             {colum name} {type} {constrants}
                               __________________ constrants
               id      Integer primarykey notnull,
               name    varchar(100) unique notnull,
              address  varchar(250)      );
