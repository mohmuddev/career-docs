---
sidebar_position: 4
---
# String Functions

SQL server string functions

- CONCAT
- CONCAT WITH +
- CHAR
- CHARINDEX

## CONCAT Function
```sql title="Cancat() function"
  SELECT CONCAT(column1, column2, column3) form tablename;
```


```sql title="Example"
select concat(first_name, ' ', second_name, ' ', last_name) as CustomerName, 
gender, mobile_no, branch, bus_off from customers where branch = 'Mogadishu';
 
+-----------------------+--------+-----------+-----------+----------------------------------------+
| CustomerName          | gender | mobile_no | branch    | bus_off                                |
+-----------------------+--------+-----------+-----------+----------------------------------------+
| Caydid Cabdi Xirsi    | Male   | 618007818 | Mogadishu | Sahro Mohamed Idiris MOG- BKR          |
| Axmed  Cali Cumar     | Male   | 615871001 | Mogadishu | Mohamed Abukar Mohamed MOG-BAKR        |
| Raxmo  Aadan xuseen   | Female | 619665577 | Mogadishu | Sahro Mohamed Idiris MOG- BKR          |
| Cabdlah Mustaf Xasan  | Male   | 615865898 | Mogadishu | Abdihamiid Ali Mohamoud Ahmed  MOG-BKR |
| Muxiyadin Yusuf Axmed | Female | 615703099 | Mogadishu | Yousuf Mohamed Ali Matan MOG-BKR       |
+-----------------------+--------+-----------+-----------+----------------------------------------+
```

## Substring Function


```sql title="Substrin function"
select substring(column_name,1,10)
select substring(column_name, -10)
```


```sql title="Example"
select substring(bus_off, -8) as Bussiness_Officer
from customers where branch="kismayo";

+-------------------+
| Bussiness_Officer |
+-------------------+
|  KIS- MN          |
|  KIS- MN          |
| d KIS-MN          |
| d KIS-MN          |
| d KIS-MN          |
| d KIS-MN          |
|  KIS- MN          |
+-------------------+
```

## Replace Function


```sql title="Replace function"
REPLACE('content', 'contain', 'replace to')

```


```sql title="Example"
select cus_ID,first_name, second_name,last_name, gender, 
replace(mobile_no, 061, +25261) as Mobile_no from customers
where gender='male';

+--------+------------+-------------+-----------+--------+--------------+
| cus_ID | first_name | second_name | last_name | gender | Mobile_no    |
+--------+------------+-------------+-----------+--------+--------------+
|      1 | Caydid     | Cabdi       | Xirsi     | Male   | 252618007818 |
|      2 | Axmed      | Cali        | Cumar     | Male   | 252615871001 |
|      4 | Cali       | Bayow       | Maxamed   | Male   | 252615688558 |
|      5 | Ibrahim    | Maxamed     | Adan      | Male   | 252615792699 |
|      6 | Cabdlah    | Mustaf      | Xasan     | Male   | 252615865898 |
|      8 | ayan       | cabdi       | guled     | Male   | 25261555273  |
|     12 | Saney      | Maxamed     | Adan      | Male   | 252616886421 |
+--------+------------+-------------+-----------+--------+--------------+

```

## Reverse Function

Reverse function changes text into mirror dispalay.


```sql title="Reverse Functin"
SELECT REVERSE(column_name) from table_name;

select reverse(gender) from customers;
+--------+
| Gender |
+--------+
| elameF |
| elameF |
| elameF |
| elameF |
| elameF |
+--------+
```

## Nest string funcitons


```sql title="Nest string function"

select substr( replace(first_name, 'li', 'bdi'), -6) asFirstName 
from customers where cus_ID=4;

+-----------+
| FirstName |
+-----------+
| Cabdi     |
+-----------+

```

## CHAR_LENGTH Function

```sql title="CHAR_LENGTH"
Select concat(first_name,' is ', char_length(first_name), ' 
characters long' ) as FirstName from customers;

+--------------------------------+
| FirstName                      |
+--------------------------------+
| Caydid is 6 characters long    |
| Axmed  is 6 characters long    |
| Raxmo  is 6 characters long    |
| Cali  is 5 characters long     |
| Ibrahim  is 8 characters long  |
| Cabdlah is 7 characters long   |
| Muxiyadin is 9 characters long |
| ayan is 4 characters long      |
| hodan is 5 characters long     |
| nura is 4 characters long      |
| Sacdiyo  is 8 characters long  |
| Saney  is 6 characters long    |
+--------------------------------+
```

## Change string's case

```sql title="Change case"
Select uppercase(first_name);
Select uppercase(first_name);

```


```sql title="Example change case"
select upper(first_name) as First_Name, bus_off  from 
customers where bus_off="Saed Abdi Mohamed KIS-MN";
+------------+--------------------------+
| First_Name | bus_off                  |
+------------+--------------------------+
| AYAN       | Saed Abdi Mohamed KIS-MN |
| HODAN      | Saed Abdi Mohamed KIS-MN |
| NURA       | Saed Abdi Mohamed KIS-MN |
| SACDIYO    | Saed Abdi Mohamed KIS-MN |
+------------+--------------------------+
```