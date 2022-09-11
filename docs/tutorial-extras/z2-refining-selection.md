---
sidebar_position: 5
---
# Refining Selection

## Using Distinct

```sql title="Distinct"

SELECT DISTINCT columnname from tablename;

```

```sql title="Example"
SELECT DISTINCT gender FROM customers;

+--------+
| gender |
+--------+
| Male   |
| Female |
+--------+
```

## Order by
```sql title="Order by"
SELECT column_name FROM table_name ORDER BY column_name ASC;
SELECT column_name FROM table_name ORDER BY column_name DESC;

```

```sql title="Example"
SELECT bus_off FROM customers ORDER BY bus_off;

+----------------------------------------+
| bus_off                                |
+----------------------------------------+
| Abdifatah Matan Abdullahi HRG-MN       |
| Abdihamiid Ali Mohamoud Ahmed  MOG-BKR |
| Abdinasir Mohamed Adan BRM             |
| Abdirahman Ali Osman HRG- IDA          |
| Aydarous Mohamed Muse HRG- IDA         |
| Cilmi Shire Faarax BWY                 |
| Cilmi Shire Faarax BWY                 |
| Cilmi Shire Faarax BWY                 |
| Hasan Baydiye Sh. Abdi KIS- MN         |
| Hasan Baydiye Sh. Abdi KIS- MN         |
| Hasan Baydiye Sh. Abdi KIS- MN         |
| Majid Mohamed Saed BRM                 |
| Majid Mohamed Saed BRM                 |
| Mohamed Abukar Mohamed MOG-BAKR        |
| Saed Abdi Mohamed KIS-MN               |
| Saed Abdi Mohamed KIS-MN               |
| Saed Abdi Mohamed KIS-MN               |
| Saed Abdi Mohamed KIS-MN               |
| Sahro Mohamed Idiris MOG- BKR          |
| Sahro Mohamed Idiris MOG- BKR          |
| Yasin Abdisalaan Huseein LAS           |
| Yasin Abdisalaan Huseein LAS           |
| Yousuf Mohamed Ali Matan MOG-BKR       |
+----------------------------------------+
```
Order by can also be applied in numbers

```sql title="Order by index number"
SELECT column_name FROM table_name ORDER BY indexnumber;
```

```sql title="Examble"
SELECT cus_ID, first_nam,second_name ,last_name FROM cutomers ORDER BY 3;
+--------+------------+-------------+----------------+
| cus_ID | first_name | second_name | last_name      |
+--------+------------+-------------+----------------+
|      2 | Axmed      | Cali        | Cumar          |
|      8 | ayan       | cabdi       | guled          |
|     18 | C/qaadir   | Axmed       | Cali           |
|      6 | Cabdlah    | Mustaf      | Xasan          |
|      4 | Cali       | Bayow       | Maxamed        |
|      1 | Caydid     | Cabdi       | Xirsi          |
|     15 | hanan      |  cabdilaahi | cawaale        |
|      9 | hodan      |  cali       |  bare          |
|     14 | Hodan      | Kayse       | Warmahaye      |
|      5 | Ibrahim    | Maxamed     | Adan           |
|     13 | iido       | faarax      | jaamac bulaale |
|     21 | ilyaas     |  siyad      | muxumed        |
|     16 | Maxamed    | Cabdullahi  | Aadan          |
|     22 | Maxamuud   | Axmed       | Maxamuud       |
|     23 | muuse      | bulaale     | aadan          |
|      7 | Muxiyadin  | Yusuf       | Axmed          |
|     10 | nura       |  Gayre      | jamac          |
|      3 | Raxmo      | Aadan       | xuseen         |
|     19 | sacada     | maxmud      | jamac          |
|     11 | Sacdiyo    | Bashir      | Sacid          |
|     12 | Saney      | Maxamed     | Adan           |
|     17 | Shuute     | Maxamed     | Dhagaxow       |
|     20 | xasan      | shucayb     |  yuusuf        |
+--------+------------+-------------+----------------+
```

## Limit rows

```sql title="Limit"
SELECT column_name FROM table_name LIMIT 3;
SELECT column_name FROM table_name LIMIT 0, 5;

```
```sql title="Limit Examble"
SELECT first_name, second_name, last_name From customers LIMIT 3;

+------------+-------------+-----------+
| first_name | second_name | last_name |
+------------+-------------+-----------+
| Caydid     | Cabdi       | Xirsi     |
| Axmed      | Cali        | Cumar     |
| Raxmo      | Aadan       | xuseen    |
+------------+-------------+-----------+
```

## Like Search
```sql title="Like '%data%'"
SELECT * FROM customes WHERE column_name LIKE  "%data%";
SELECT * FROM customes WHERE column_name LIKE  "%\%data%";

```

```sql title="Examble Like '%data%'"
SELECT * FROM customers WHERE first_name like"%ca%";
+--------+------------+-------------+-----------+--------+-----------+-------------+----------------------------------------+
| cus_ID | first_name | second_name | last_name | gender | mobile_no | branch      | bus_off                                |
+--------+------------+-------------+-----------+--------+-----------+-------------+----------------------------------------+
|      1 | Caydid     | Cabdi       | Xirsi     | Male   | 618007818 | Mogadishu   | Sahro Mohamed Idiris MOG- BKR          |
|      4 | Cali       | Bayow       | Maxamed   | Male   | 615688558 | Kismayo     | Hasan Baydiye Sh. Abdi KIS- MN         |
|      6 | Cabdlah    | Mustaf      | Xasan     | Male   | 615865898 | Mogadishu   | Abdihamiid Ali Mohamoud Ahmed  MOG-BKR |
|     19 | sacada     | maxmud      | jamac     | Female | 634637377 | HQ/Hargeisa | Abdinasir Mohamed Adan BRM             |
+--------+------------+-------------+-----------+--------+-----------+-------------+----------------------------------------+
```

```sql title="Like '__' "
SELECT * FROM customes WHERE column_name LIKE  '---';
SELECT * FROM customes WHERE column_name LIKE  '-\--';

```

```sql title="Examble like '__' "
SELECT first_name, gender, mobile_no From customers
 WHERE first_name like '____';

+------------+--------+-----------+
| first_name | gender | mobile_no |
+------------+--------+-----------+
| ayan       | Male   |  61555273 |
| nura       | Female | 613878689 |
| iido       | Female | 634794565 |
+------------+--------+-----------+
```