---
sidebar_position: 3
---

# CRUD Commands
**C**reate,  **R**ead,  **U**pdate and **D**elete

 ## Select expression
```sql title="SELECT entire table"
SELECT * FROM customers;

+----+-------------------------+--------+-----------+
| ID | CustomerName            | Sex    | Contact   |
+----+-------------------------+--------+-----------+
|  1 | Abdullahi Hussein Ali   | Female | 617878965 |
|  2 | Mukhar Hilowle Farax    | Male   | 618786978 |
|  3 | Deeqow Gure Abdi        | Male   | 618748596 |
|  4 | Anzal Abdiraxman Abdi   | Male   | 617968574 |
|  5 | Farxiyo Axmed Noor Abdi | Female | 615974869 |
+----+-------------------------+--------+-----------+


```
## Select specific column
```sql title="SELECT specific column"
SELECT columnName FROM tableName;

SELECT CustomerName FROM customers;
+-------------------------+
| CustomerName            |
+-------------------------+
| Abdullahi Hussein Ali   |
| Mukhar Hilowle Farax    |
| Deeqow Gure Abdi        |
| Anzal Abdiraxman Abdi   |
| Farxiyo Axmed Noor Abdi |
+-------------------------+

```

## Select Multiple columns
```sql title="Select multiple columns"
SELECT columnName1, Column2 FROM tableName

SELECT CustomerName, Contact From customers;
+-------------------------+-----------+
| CustomerName            | Contact   |
+-------------------------+-----------+
| Abdullahi Hussein Ali   | 617878965 |
| Mukhar Hilowle Farax    | 618786978 |
| Deeqow Gure Abdi        | 618748596 |
| Anzal Abdiraxman Abdi   | 617968574 |
| Farxiyo Axmed Noor Abdi | 615974869 |
+-------------------------+-----------+

```

## Where clouse

```sql title="SELECT WHERE"
SELECT * FROM customers WHERE Sex='Male';

+----+-----------------------+------+-----------+
| ID | CustomerName          | Sex  | Contact   |
+----+-----------------------+------+-----------+
|  2 | Mukhar Hilowle Farax  | Male | 618786978 |
|  3 | Deeqow Gure Abdi      | Male | 618748596 |
|  4 | Anzal Abdiraxman Abdi | Male | 617968574 |
+----+-----------------------+------+-----------+

```

## Introduction to Aliases


```sql title="Aliases"
SELECT CustomerName AS Name , Sex from customers;
+-------------------------+--------+
| Name                    | Sex    |
+-------------------------+--------+
| Abdullahi Hussein Ali   | Female |
| Mukhar Hilowle Farax    | Male   |
| Deeqow Gure Abdi        | Male   |
| Anzal Abdiraxman Abdi   | Male   |
| Farxiyo Axmed Noor Abdi | Female |
+-------------------------+--------+
```

## Update Commmand

```sql title="Update command"
UPDATE tabaleName SET  columnName='newData' WHERE columnName='oldData';

UPDATE customers SET CustomerName='Farax Timajilac Hassan'
WHERE CustomerName='Mukhar Hilowle Farax';
+----+-------------------------+--------+-----------+
| ID | CustomerName            | Sex    | Contact   |
+----+-------------------------+--------+-----------+
|  1 | Abdullahi Hussein Ali   | Female | 617878965 |
|  2 | Farax Timajilac Hassan  | Male   | 618786978 |
|  3 | Deeqow Gure Abdi        | Male   | 618748596 |
|  4 | Anzal Abdiraxman Abdi   | Male   | 617968574 |
|  5 | Farxiyo Axmed Noor Abdi | Female | 615974869 |
+----+-------------------------+--------+-----------+

```

```sql title="Update specific data"
UPDATE customers SET Contact=0617788999 WHERE CustomerName='Farxiyo Axmed Noor Abdi';
+----+-------------------------+--------+-----------+
| ID | CustomerName            | Sex    | Contact   |
+----+-------------------------+--------+-----------+
|  5 | Farxiyo Axmed Noor Abdi | Female | 617788999 |
+----+-------------------------+--------+-----------+

```

:::note Note
Try SELECTing data before UPDATE
:::

## Delete command

```sql title="Delete command"
DELETE FROM tabaleName Where columnName='data to be deleted';
DELETE FROM customers  where CustomerName='Deeqow Gure Abdi';
+----+-------------------------+--------+-----------+
| ID | CustomerName            | Sex    | Contact   |
+----+-------------------------+--------+-----------+
|  1 | Abdullahi Hussein Ali   | Female | 617878965 |
|  2 | Farax Timajilac Hassan  | Male   | 618786978 |
|  4 | Anzal Abdiraxman Abdi   | Male   | 617968574 |
|  5 | Farxiyo Axmed Noor Abdi | Female | 617788999 |
+----+-------------------------+--------+-----------+
```


