---
sidebar_position: 7
---
# Revisiting Data Types

## CHAR and VARCHAR

`VARCHAR` is variable length, while `CHAR` is fixed length

`CHAR` is a fixed length string data type, so any remaining space in the field is padded with blanks. `CHAR` takes up 1 byte per character. So, a `CHAR(100)` field (or variable) takes up 100 bytes on disk, regardless of the string it holds.


`VARCHAR` is a variable length string data type, so it holds only the characters you assign to it. `VARCHAR` takes up 1 byte per character, + 2 bytes to hold length information.  For example, if you set a `VARCHAR(100)` data type = ‘Jen’, then it would take up 3 bytes (for J, E, and N) plus 2 bytes, or 5 bytes in all.


```sql title="CHAR & VARCHAR"
+-----------+---------+---------+--+-----------+------------+---------+
| VALUE     | CHAR(4) | STORAGE |  | VALUE     | VARCHAR(4) | STORAGE |
+-----------+---------+---------+--+-----------+------------+---------+
| ''        | '    '  | 4 bytes |  | ''        | ''         | 1 bytes |
+-----------+---------+---------+--+-----------+------------+---------+
| 'ab'      | 'ab   ' | 4 bytes |  | 'ab'      | ''         | 3 bytes |
+-----------+---------+---------+--+-----------+------------+---------+
| 'abcd'    | 'abcd'  | 4 bytes |  | 'abcd'    | 'abcd'     | 5 bytes |
+-----------+---------+---------+--+-----------+------------+---------+
| 'abcdefg' | 'abcd'  | 4 bytes |  | 'abcdefg' | 'abcdefg'  | 5 bytes |
+-----------+---------+---------+--+-----------+------------+---------+
```

## NUMBERS

```sql title="Decimals"
create table dpts
(
 Name varchar(255),
 Price decimal(5,2)
);

insert into dpts(Name, Price)
values('Johne Doe', 100.01),
      ('Jocob adams', 100);

+-------------+--------+
| Name        | Price  |
+-------------+--------+
| John Doe    | 100.01 |
| Jocob adams | 100.00 |
+-------------+--------+
```

## DATE and Time

- Date `YYYY-MM-DD`
- Time `HH:MM:SS`
- DATETIME `YYYY-MM-DD HH:MM:SS`

**Create date data**

```sql title="Create date data"
create table people
(
 ID int not null auto_increment,
 Name varchar(255),
 DOB date,
 TOB time,
 DOBT datetime,
 primary key(ID)
);

insert into people( Name, DOB, TOB, DOBT)
values('Abdullahi Ali Farah', '1986-01-01', '07:30:35', '1986-01-01 12:30:35'),
      ('Mohamed Hassan Abdi', '1989-01-01', '01:30:35', '1989-01-01 01:30:35'),
	  ('Abdullahi Ali Farah', '1994-01-01', '08:30:35', '1994-01-01 08:30:35');

select * from people;

+----+---------------------+------------+----------+---------------------+
| ID | Name                | DOB        | TOB      | DOBT                |
+----+---------------------+------------+----------+---------------------+
|  1 | Abdullahi Ali Farah | 1986-01-01 | 07:30:35 | 1986-01-01 12:30:35 |
|  2 | Mohamed Hassan Abdi | 1989-01-01 | 01:30:35 | 1989-01-01 01:30:35 |
|  3 | Abdullahi Ali Farah | 1994-01-01 | 08:30:35 | 1994-01-01 08:30:35 |
+----+---------------------+------------+----------+---------------------+
```

## CURDATE, CURTIME and NOW

- CURDATE() - Current date
- CURTIME() - current time
- NOW()     - Current datetime


```sql title="Examble"
insert into people( Name, DOB, TOB, DOBT)
values('Abdihamiid Ali Abdi', curdate(), curtime(), now());

 +----+---------------------+------------+----------+---------------------+
| ID | Name                | DOB        | TOB      | DOBT                |
+----+---------------------+------------+----------+---------------------+
|  4 | Abdihamiid Ali Abdi | 2021-07-30 | 15:04:21 | 2021-07-30 15:04:21 |
+----+---------------------+------------+----------+---------------------+
```


## DATE FORMATING

**Date functions**
- DAY()
- DAYNAME()
- DAYOFWEEK()
- DAYOFYEAR()


**Date format function**

DATE_FORMAT()


```sql title="DATE_FORMAT()"
Select ID,Name,date_format(DOB, '%W %M %Y') AS DOB from people;

+----+---------------------+------------------------+
| ID | Name                | DOB                    |
+----+---------------------+------------------------+
|  1 | Abdullahi Ali Farah | Wednesday January 1986 |
|  2 | Mohamed Hassan Abdi | Sunday January 1989    |
|  3 | Abdullahi Ali Farah | Saturday January 1994  |
|  4 | Abdihamiid Ali Abdi | Friday July 2021       |
+----+---------------------+------------------------+

```

**Standard date format**


```sql title="Standar date format"
Select ID,Name,date_format(DOB, '%d/%m/%Y') AS DATE_OF_BIRTH from people;

+----+---------------------+---------------+
| ID | Name                | DATE_OF_BIRTH |
+----+---------------------+---------------+
|  1 | Abdullahi Ali Farah | 01/01/1986    |
|  2 | Mohamed Hassan Abdi | 01/01/1989    |
|  3 | Abdullahi Ali Farah | 01/01/1994    |
|  4 | Abdihamiid Ali Abdi | 30/07/2021    |
+----+---------------------+---------------+
```

## MATH DATE

**Date Calculation(Arithmetic)**
- DATEDIFF()
- DATE_ADD
- +/-


**DATEDIFF()**


```sql title="DIFFDATE()"
select ID, Name, datediff(curdate(), DOB) Days_ago FROM people;

+----+---------------------+----------+
| ID | Name                | Days_ago |
+----+---------------------+----------+
|  1 | Abdullahi Ali Farah |    12994 |
|  2 | Mohamed Hassan Abdi |    11898 |
|  3 | Abdullahi Ali Farah |    10072 |
|  4 | Abdihamiid Ali Abdi |        0 |
+----+---------------------+----------+
```


**DATE_ADD**


```sql title="DATE_ADD"
SELECT ID, Name, DATE_ADD(DOB, INTERVAL 1 MONTH) AS New_DOB FROM people;

+----+---------------------+------------+
| ID | Name                | New_DOB    |
+----+---------------------+------------+
|  1 | Abdullahi Ali Farah | 1986-02-01 |
|  2 | Mohamed Hassan Abdi | 1989-02-01 |
|  3 | Abdullahi Ali Farah | 1994-02-01 |
|  4 | Abdihamiid Ali Abdi | 2021-08-30 |
+----+---------------------+------------+
```

**+-**

```sql title="Addition"
SELECT ID, Name, DOB + INTERVAL 1 Month from people;
+----+---------------------+------------+
| ID | Name                | New_DOB    |
+----+---------------------+------------+
|  1 | Abdullahi Ali Farah | 1986-02-01 |
|  2 | Mohamed Hassan Abdi | 1989-02-01 |
|  3 | Abdullahi Ali Farah | 1994-02-01 |
|  4 | Abdihamiid Ali Abdi | 2021-08-30 |
+----+---------------------+------------+

``` 

```sql title="Substruction"
SELECT ID, Name, DOB - INTERVAL 1 Month from people;
+----+---------------------+------------+
| ID | Name                | New_DOB    |
+----+---------------------+------------+
|  1 | Abdullahi Ali Farah | 1985-12-01 |
|  2 | Mohamed Hassan Abdi | 1988-12-01 |
|  3 | Abdullahi Ali Farah | 1993-12-01 |
|  4 | Abdihamiid Ali Abdi | 2021-06-30 |
+----+---------------------+------------+
```

## TIMESTAMPS


```sql title="New timestamp"
Create table new_comments
(
ID int primary key auto_increment,
Comments varchar(255),
posted_at timestamp default now()
);

insert into new_comments(Comments)
values('The lesson was amazing'),
      ('The instructor was skillful'),
      ('I recommend everyone to this course');

+----+-------------------------------------+---------------------+
| ID | Comments                            | posted_at           |
+----+-------------------------------------+---------------------+
|  1 | The lesson was amazing              | 2021-08-06 15:32:48 |
|  2 | The instructor was skillful         | 2021-08-06 15:32:48 |
|  3 | I recommend everyone to this course | 2021-08-06 15:32:48 |
+----+-------------------------------------+---------------------+

```


```sql title="Update timestamp"
Create table update_comments
(
ID int primary key auto_increment,
Comments varchar(255),
updated_at timestamp default now() on update current_timestamp
);


insert into update_comments(Comments)
values('This is awesom, I love it'),
      ('The instructor was skillful'),
      ('I recommend everyone to this course');

+----+-------------------------------------+---------------------+
| ID | Comments                            | updated_at          |
+----+-------------------------------------+---------------------+
|  1 | This is awesom, I love it           | 2021-08-06 15:38:34 |
|  2 | The instructor was skillful         | 2021-08-06 15:38:34 |
|  3 | I recommend everyone to this course | 2021-08-06 15:38:34 |
+----+-------------------------------------+---------------------+

```