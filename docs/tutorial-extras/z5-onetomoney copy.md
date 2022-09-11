---
sidebar_position: 10
---
# SQL Joins

## LAP PREPARATION
USERS TABLE
<details>
<summary> <code>Users table</code> </summary>

|ID|User.Name|
|---|---|
1|	Patrik|
2|	Albert|
3|	Maria|
4|	Darwin|
5|	Elizabeth|
</details>

LIKES TABLE
<details>
<summary> <code>Likes table</code> </summary>

|ID|Likes.Name|Likes.User_ID|
|---|---|---|
2|	1|	Climbing|
3|	1|	Code|
4|	6|	Rugby|
5|	4|	Apples|
1|	3|	Stars|
</details>


## INNER JOIN
The SQL INNER JOIN joins two tables based on a common column, and selects records that have matching values in these columns.

```sql title='Inner Join'
 SELECT
	USERS.ID,
	users.name,
	USER_ID,
	likes.NAME
FROM
	users
JOIN likes ON
	users.id = likes.user_id;
```
<details>
<summary>Output for <code>Inner Join</code> </summary>

|ID|User.Name|Likes.UserID|Likes.Name|
|---|---|---|---|
1|	Patrik|	1|	Climbing|
1|	Patrik|	1|	Code|
4|	Darwin|	4|	Apples|
3|	Maria|	3|	Stars|		
</details>


## LEFT JOIN
The LEFT JOIN command returns all rows from the left table, and the matching rows from the right table. The result is NULL from the right side, if there is no match.

```sql title="Left Join"
SELECT
	USERS.ID,
	users.name,
	USER_ID,
	likes.NAME
FROM
	users
LEFT JOIN likes ON
	users.id = likes.user_id;
```
<details>
<summary>Output for <code>Left Join</code> </summary>

|ID|User.Name|Likes.UserID|Likes.Name|
|---|---|---|---|
1|	Patrik|	1|	Climbing
1|	Patrik|	1|	Code
4|	Darwin|	4|	Apples
3|	Maria|	3|	Stars
2|	Albert|NULL|NULL|	
5|	Elizabeth|NULL|NULL|		
</details>

## RIGHT JOIN
The RIGHT JOIN command returns all rows from the right table, and the matching records from the left table. The result is NULL from the left side, when there is no match.

```sql title='Right Join'
SELECT
	USERS.ID,
	users.name,
	USER_ID,
	likes.NAME
FROM
	users
RIGHT JOIN likes ON
	users.id = likes.user_id;
```
<details>
<summary>Output for <code>Right Join</code> </summary>

|ID|User.Name|Likes.UserID|Likes.Name|
|---|---|---|---|
1|	Patrik|	1|	Climbing|
1|	Patrik|	1|	Code|
3|	Maria|	3|	Stars|
4|	Darwin|	4|	Apples|
NULL|NULL|6|Rugby|
</details>


## FULL OUTER JOIN
 FULL OUTER JOIN combines the results of both left and right outer joins and returns all (matched or unmatched) rows from the tables on both sides of the join clause.
```sql title='Outer Join'
SELECT
    USERS.ID,
    users.name,
    USER_ID,
    likes.NAME
FROM
    users
FULL OUTER JOIN likes ON
    users.id = likes.user_id;
```
<details>
 <summary>Output for <code>Outer Join</code> </summary>

|ID|User.Name|Likes.UserID|Likes.Name|
|---|---|---|---|
|1|	Patrik|	1|	Climbing|
|1|	Patrik|	1|	Code|
|NULL|NULL|	6|	Rugby|
|4|	Darwin|	4|	Apples|
|3|	Maria|	3|	Stars|
|2|	Albert|NULL|NULL|	
|5|	Elizabeth|NULL|NULL|		
</details>