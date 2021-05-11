# convert-mysql-query-result-into-json-format
convert mysql query result into json format
_____________________________________________________________________________________________


mysql> select * from school_table;
+----+----------+-------+------------+
| id | name     | score | subject    |
+----+----------+-------+------------+
|  4 | Ankit    | 90.45 | Physics    |
|  3 | Lokesh   | 80.45 | Maths      |
|  5 | Anjali   | 84.45 | Arts       |
|  6 | Nagesh   | 90.56 | Maths      |
|  7 | Shubham  | 81.45 | Accounts   |
| 10 | Priyanka | 86.62 | Management |
| 11 | Lalit    | 70.62 | OP         |
| 13 | Arjun    | 70.62 | DBMS       |
| 14 | Abhinav  | 83.08 | Poetry     |
| 15 | Rupali   | 73.08 | coding     |
| 16 | Pallavi  | 63.08 | Apptitute  |
|  0 | SHIKHAR  | 89.45 | LOCAL      |
|  1 | SACHIN   | 56.45 | MISSION    |
|  2 | KIRAN    | 36.45 | JSON DATA  |
+----+----------+-------+------------+
14 rows in set (0.00 sec)

mysql> set @jsonlk=(select json_arrayagg(json_object("id",id,"name",name,"score",score,"subject",subject)) from school_table);
Query OK, 0 rows affected (0.00 sec)

mysql> select json_pretty(@jsonlk);
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| json_pretty(@jsonlk)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| [
  {
    "id": 4,
    "name": "Ankit",
    "score": 90.45,
    "subject": "Physics"
  },
  {
    "id": 3,
    "name": "Lokesh",
    "score": 80.45,
    "subject": "Maths"
  },
  {
    "id": 5,
    "name": "Anjali",
    "score": 84.45,
    "subject": "Arts"
  },
  {
    "id": 6,
    "name": "Nagesh",
    "score": 90.56,
    "subject": "Maths"
  },
  {
    "id": 7,
    "name": "Shubham",
    "score": 81.45,
    "subject": "Accounts"
  },
  {
    "id": 10,
    "name": "Priyanka",
    "score": 86.62,
    "subject": "Management"
  },
  {
    "id": 11,
    "name": "Lalit ",
    "score": 70.62,
    "subject": "OP"
  },
  {
    "id": 13,
    "name": "Arjun ",
    "score": 70.62,
    "subject": "DBMS"
  },
  {
    "id": 14,
    "name": "Abhinav",
    "score": 83.08,
    "subject": "Poetry"
  },
  {
    "id": 15,
    "name": "Rupali",
    "score": 73.08,
    "subject": "coding"
  },
  {
    "id": 16,
    "name": "Pallavi",
    "score": 63.08,
    "subject": "Apptitute"
  },
  {
    "id": 0,
    "name": "SHIKHAR",
    "score": 89.45,
    "subject": "LOCAL"
  },
  {
    "id": 1,
    "name": "SACHIN",
    "score": 56.45,
    "subject": "MISSION"
  },
  {
    "id": 2,
    "name": "KIRAN",
    "score": 36.45,
    "subject": "JSON DATA"
  }
] |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)

mysql> mysql>
