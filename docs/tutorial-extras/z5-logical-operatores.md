---
sidebar_position: 8
---
# Logical Operators

- Not Equal  ( **!=** )
- Like
- Not Like  
- Greater Than  ( **>** )
- Less Than  ( **<** )
- Logic AND  ( **&&** )
- Logic OR  ( **||** )
- Between  
- In and Not 
- Case Statement 



## NOT EQUAL


```sql title="Table before logical operator"
+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  1 | Abdullahi Hassan Farah  |    90 |
|  2 | Mohamed Hussein Abdi    |    75 |
|  3 | Ali Omer Jama           |    60 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  5 | Saynab Abdirahman Jamac |    65 |
|  6 | Abdi Mire Xuen          |    90 |
|  7 | Jele Mire Farah         |    75 |
|  8 | Fadumo Xasan Odawa      |    60 |
+----+-------------------------+-------+
```

```sql title="Not Equal"
Select * from students where Marks != 90;

+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  2 | Mohamed Hussein Abdi    |    75 |
|  3 | Ali Omer Jama           |    60 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  5 | Saynab Abdirahman Jamac |    65 |
|  7 | Jele Mire Farah         |    75 |
|  8 | Fadumo Xasan Odawa      |    60 |
+----+-------------------------+-------+

```

## LIKE


```sql title="Like"
Select *from students where StudentName LIKE '%Farah%';
+----+------------------------+-------+
| ID | StudentName            | Marks |
+----+------------------------+-------+
|  1 | Abdullahi Hassan Farah |    90 |
|  7 | Jele Mire Farah        |    75 |
+----+------------------------+-------+

```


## NOT LIKE 


```sql title="Not Like"
Select *from students where StudentName NOT LIKE '%Abdi%';

+----+------------------------+-------+
| ID | StudentName            | Marks |
+----+------------------------+-------+
|  1 | Abdullahi Hassan Farah |    90 |
|  3 | Ali Omer Jama          |    60 |
|  7 | Jele Mire Farah        |    75 |
|  8 | Fadumo Xasan Odawa     |    60 |
+----+------------------------+-------+
```


## GREATER THAN

```sql title="Greater Than"
Select * from students where Marks > 70;
+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  1 | Abdullahi Hassan Farah  |    90 |
|  2 | Mohamed Hussein Abdi    |    75 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  6 | Abdi Mire Xuen          |    90 |
|  7 | Jele Mire Farah         |    75 |
+----+-------------------------+-------+
```


```sql title="Greater Than"
Select * from students where Marks < 70;
+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  1 | Abdullahi Hassan Farah  |    90 |
|  2 | Mohamed Hussein Abdi    |    75 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  6 | Abdi Mire Xuen          |    90 |
|  7 | Jele Mire Farah         |    75 |
+----+-------------------------+-------+
```

## LOGIC AND

```sql title="LOGIC AND &&"
Select * from students where Marks = 60 && ID > 1;
+----+--------------------+-------+
| ID | StudentName        | Marks |
+----+--------------------+-------+
|  3 | Ali Omer Jama      |    60 |
|  8 | Fadumo Xasan Odawa |    60 |

```

## LOGIC OR


```sql title="Logic Or ||"
Select * from students where Marks = 61 || Marks > 75;
+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  1 | Abdullahi Hassan Farah  |    90 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  6 | Abdi Mire Xuen          |    90 |
+----+-------------------------+-------+
```

## BETWEEN

```sql title="Between"
Select * from students where Marks >= 70 && Marks <=90;
+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  1 | Abdullahi Hassan Farah  |    90 |
|  2 | Mohamed Hussein Abdi    |    75 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  6 | Abdi Mire Xuen          |    90 |
|  7 | Jele Mire Farah         |    75 |
+----+-------------------------+-------+

```

## IN and NOT

```sql title="IN and Not"
Select *from students where StudentName
IN('Abdi Mire Xuen','Mohamed Hussein Abdi','Jele Mire Farah');
+----+----------------------+-------+
| ID | StudentName          | Marks |
+----+----------------------+-------+
|  2 | Mohamed Hussein Abdi |    75 |
|  6 | Abdi Mire Xuen       |    90 |
|  7 | Jele Mire Farah      |    75 |
+----+----------------------+-------+
```

## CASE STATEMENT

```sql title="Case statements"
SELECT ID, StudentName, Marks,
CASE
WHEN Marks >= 65 THEN 'Passed very well'
ELSE 'Normal Passed'
END AS Remarks
FROM students;

+----+-------------------------+-------+------------------+
| ID | StudentName             | Marks | Remarks          |
+----+-------------------------+-------+------------------+
|  1 | Abdullahi Hassan Farah  |    90 | Passed very well |
|  2 | Mohamed Hussein Abdi    |    75 | Passed very well |
|  3 | Ali Omer Jama           |    60 | Normal Passed    |
|  4 | Abdirisakh Diriye Yusuf |    78 | Passed very well |
|  5 | Saynab Abdirahman Jamac |    65 | Passed very well |
|  6 | Abdi Mire Xuen          |    90 | Passed very well |
|  7 | Jele Mire Farah         |    75 | Passed very well |
|  8 | Fadumo Xasan Odawa      |    60 | Normal Passed    |
+----+-------------------------+-------+------------------+
```