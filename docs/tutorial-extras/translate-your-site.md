---
sidebar_position: 2
---

# Insert Data

## Insert data into table

How to `insert` data into table.

```sql title="Inserting data Command"
INSERT INTO tabalename(column1, column2)
VALUES ('value1', 2)

INSERT INTO students(Name, Meangrade)
VALUES ('Mohamud Ali Farah', 'C+'),
       ('Hashim Abdi wheliye', 'C');

```

## Dispaly data inserted data
```sql title="Show data in table command"
SELECT * FROM tablename;

SELECT * FROM students;
+----------------------+------+-----------+-----------------------+
| Name                 | Age  | Meangrade | Jobtitle              |
+----------------------+------+-----------+-----------------------+
| Mohamud Ali Farah    |   26 | C+        | database adminstrator |
| Hassan Abdi Hassan   |   29 | C-        | Finance Officer       |
| Hashim Abdi weheliye |   30 | C         | Head Teacher          |
| Hassan Adan Siraje   |   29 | C+        | Programm Manger       |
+----------------------+------+-----------+-----------------------+
```

## Show warnings
:::note important

`SQLwarnings` warn against conditions/excerptions resulting from execution of the most recent nondiagnostic statement in the current session.

:::

```SQL title="Command to display warnings"
SHOW WARNINGS;

```

## NULL and NOT NULL
By default, a column can hold `NULL` values. The `NOT NULL` constraint enforces a column to NOT accept `NULL` values. This enforces a field to always contain a value, which means that you cannot insert a new record, or update a record without adding a value to this field.
```sql title="NULL and NOT NULL"
INSERT INTO students(Name, Meangrade)
VALUES ( ),

The value of Name and menagrade will be NULL


CREATE TABLE persons
(
    name varchar(255) NOT NULL,
    age int NOT NULL

)

NOT NULL forces the values can not be NULL

```


## Default values
The `DEFAULT` constraint is used to set a default value for a column. The `default` value will be added to all new records, if no other value is specified.
```sql title="Default values"
CREATE TABLE tabalename
(
  Column_name data_type default 'Mohamud Ali Farah',
  column_name data_type
);

```

## Primary key
A `primary key` is a field in a table which uniquely identifies each row/record in a database table. Primary keys must contain unique values. A `primary key` column cannot have `NULL` values. A table can have only one `primary key`, which may consist of single or multiple fields.
```sql title="PRIMARY KEY"
CREATE TABLE persons
(
  person_id INT NOT NULL,
  name varchar(255),
  age INT,
  PRIMARY KEY (person_id)
);

```

## Auto generated IDs
```sql title="PRIMARY KEY  AUTO_INCREMENT"
CREATE TABLE persons
(
  person_id INT NOT NULL AUTO_INCREMENT,
  name varchar(255),
  age INT,
  PRIMARY KEY (person_id)
);

```

