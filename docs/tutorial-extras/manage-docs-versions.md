---
sidebar_position: 1
---

# Create Databases and Tables

How to `create databases` and `tables` in SQL.

## Create database


```sql title="Create database command"
 CREATE DATABASE <databasename>;
 
 Create database learn_sql_db;


```
## Show database

```sql title="show database command"
SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| learn_sql          |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```
## Drop database
```sql title="Drop database command"
+--------------------+
| Database           |
+--------------------+
| information_schema |
| learn_sql          |
| learn_sql_drop     |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
 
drop database <databasename>;
drop database learn_sql_drop;

+--------------------+
| Database           |
+--------------------+
| information_schema |
| learn_sql          |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```

## Use database
```sql title="use database command"
USE <databasename>;
USE learn_sql;
```

## Display the current database
```sql title="Show current database"
SELECT database():
+------------+
| database() |
+------------+
| learn_sql  |
+------------+
```
## Datatypes
List of datatype in SQL
- String types; `Char, Varchar, Binary, Text , Tinytext , Longtext`
- Numeric types; `Numeric, Int, Intenger, Tinyint, Bigint, Decimal, Float, Double` 
- Date types; `Time, Timestamp, Datetime, Year`

## Create table
```sql title="Syntax for creating table"
CREATE TABLE tabalename
(
  Column_name data_type,
  column_name data_type
);

```
## Show table
```sql title="Show table command"
SHOW <tablename>;

```

## Show columns in the table
```sql title="Show table columns command"
SHOW columns FROM <tablename>;
+-----------+--------------+------+-----+---------+-------+
| Field     | Type         | Null | Key | Default | Extra |
+-----------+--------------+------+-----+---------+-------+
| Name      | varchar(255) | YES  |     | NULL    |       |
| Age       | int          | YES  |     | NULL    |       |
| Meangrade | varchar(255) | YES  |     | NULL    |       |
| Jobtitle  | varchar(255) | YES  |     | NULL    |       |
+-----------+--------------+------+-----+---------+-------+
```

## Drop table
```sql title="Dropping table"
  DROP TABLE <tablename>;
```
