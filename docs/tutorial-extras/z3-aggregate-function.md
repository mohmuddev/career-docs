---
sidebar_position: 6
---
# Aggregate Function

## The count function


```sql title="COUNT"
SELECT  count(*) FROM table_name;
```

```sql title="COUNT"
select count(*) from students;
+----------+
| count(*) |
+----------+
|        5 |
+----------+
```

## Group By

```sql title="Group By"
 Select column_name FROM table_name GROUP BY coumn_name;

```

```sql title="Examble"
Select cus_ID, first_name,second_name, last_name , branch, COUNT(*) 
FROM customers GROUP BY branch;
+--------+------------+-------------+----------------+-------------+----------+
| cus_ID | first_name | second_name | last_name      | branch      | COUNT(*) |
+--------+------------+-------------+----------------+-------------+----------+
|      1 | Caydid     | Cabdi       | Xirsi          | Mogadishu   |        5 |
|      4 | Cali       | Bayow       | Maxamed        | Kismayo     |        7 |
|     13 | iido       | faarax      | jaamac bulaale | HQ/Hargeisa |        4 |
|     16 | Maxamed    | Cabdullahi  | Aadan          | Beletweine  |        3 |
|     20 | xasan      | shucayb     |  yuusuf        | Borama      |        4 |
+--------+------------+-------------+----------------+-------------+----------+
```

```sql title="Example2"
  
SELECT cus_ID, bus_off, branch, count(*) AS No_customers FROM customers  
GROUP BY bus_off;
+----+----------------------------------------+-------------+--------------+
| ID | Account_Manger                         | Branch      | No_customers |
+----+----------------------------------------+-------------+--------------+
|  1 | Sahro Mohamed Idiris MOG- BKR          | Mogadishu   |            2 |
|  2 | Mohamed Abukar Mohamed MOG-BAKR        | Mogadishu   |            1 |
|  4 | Hasan Baydiye Sh. Abdi KIS- MN         | Kismayo     |            3 |
|  6 | Abdihamiid Ali Mohamoud Ahmed  MOG-BKR | Mogadishu   |            1 |
|  7 | Yousuf Mohamed Ali Matan MOG-BKR       | Mogadishu   |            1 |
|  8 | Saed Abdi Mohamed KIS-MN               | Kismayo     |            4 |
| 13 | Aydarous Mohamed Muse HRG- IDA         | HQ/Hargeisa |            1 |
| 14 | Abdirahman Ali Osman HRG- IDA          | HQ/Hargeisa |            1 |
| 15 | Abdifatah Matan Abdullahi HRG-MN       | HQ/Hargeisa |            1 |
| 16 | Cilmi Shire Faarax BWY                 | Beletweine  |            3 |
| 19 | Abdinasir Mohamed Adan BRM             | HQ/Hargeisa |            1 |
| 20 | Majid Mohamed Saed BRM                 | Borama      |            2 |
| 22 | Yasin Abdisalaan Huseein LAS           | Borama      |            2 |
+----+----------------------------------------+-------------+--------------+
```


## MAX and MIN 

```sql title="Exam Result Table"
+----+-------------------------+-------+
| ID | StudentName             | Marks |
+----+-------------------------+-------+
|  1 | Abdullahi Hassan Farah  |    90 |
|  2 | Mohamed Hussein Abdi    |    75 |
|  3 | Ali Omer Jama           |    60 |
|  4 | Abdirisakh Diriye Yusuf |    78 |
|  5 | Saynab Abdirahman Jamac |    65 |
+----+-------------------------+-------+
```

```sql title="Max and Min"
SELECT max(cloumn) FROM table_name;
SELECT min(cloumn) FROM table_name;

```

```sql title="MAX"
SELECT StudentName, MAX(Marks) AS Max_value,FROM students;
+------------------------+-----------+
| StudentName            | Max_value |
+------------------------+-----------+
| Abdullahi Hassan Farah |        90 |
+------------------------+-----------+
```

```sql title="MIN"
SELECT StudentName, MIN(Marks) AS Max_value,FROM students;
+------------------------+-----------+
| StudentName            | Min_value |
+------------------------+-----------+
| Abdullahi Hassan Farah |        60 |
+------------------------+-----------+
```

:::note NOTE 

 The Max and Min function does not select thier correct respective values.
:::

## Solve Max and Min issue

```sql title="Subqueries"
SElECT column_name from table_name WHERE Column_name=(SELECT MAX(cloumn) 
FROM table_name);

SElECT column_name from table_name WHERE Column_name=(SELECT MIN(cloumn) 
FROM table_name);
```

```sql title="Examble"
SELECT StudentName, Marks FROM students WHERE 
Marks=( MIN(Marks) FROM students);

+---------------+-------+
| StudentName   | Marks |
+---------------+-------+
| Ali Omer Jama |    60 |
+---------------+-------+

```

## Min and Max with Group By

```sql title="Min and Max with group by"
SELECT cus_ID,bus_off, min(mobile_no) as Mobile_no FROM customers 
GROUP BY bus_off;
+--------+----------------------------------------+-----------+
| cus_ID | bus_off                                | Mobile_no |
+--------+----------------------------------------+-----------+
|      1 | Sahro Mohamed Idiris MOG- BKR          | 618007818 |
|      2 | Mohamed Abukar Mohamed MOG-BAKR        | 615871001 |
|      4 | Hasan Baydiye Sh. Abdi KIS- MN         | 615688558 |
|      6 | Abdihamiid Ali Mohamoud Ahmed  MOG-BKR | 615865898 |
|      7 | Yousuf Mohamed Ali Matan MOG-BKR       | 615703099 |
|      8 | Saed Abdi Mohamed KIS-MN               |  61555273 |
|     13 | Aydarous Mohamed Muse HRG- IDA         | 634794565 |
|     14 | Abdirahman Ali Osman HRG- IDA          | 634732204 |
|     15 | Abdifatah Matan Abdullahi HRG-MN       | 634715826 |
|     16 | Cilmi Shire Faarax BWY                 | 615519427 |
|     19 | Abdinasir Mohamed Adan BRM             | 634637377 |
|     20 | Majid Mohamed Saed BRM                 | 614526996 |
|     22 | Yasin Abdisalaan Huseein LAS           | 634495171 |
+--------+----------------------------------------+-----------+
```

## SUM Function

```sql title="SUM"
SELECT Sum(column_name) FROM table_name
```

```sql title="SUM Examble"
SELECT sum(Marks) as Total_Marks from students;
+-------------+
| Total_Marks |
+-------------+
|         593 |
+-------------+
```


## AVG Funtion

```sql title="Average Function"
SELECT AVG(column_name) FROM table_name
+---------+
| Average |
+---------+
| 74.1250 |
+---------+
```