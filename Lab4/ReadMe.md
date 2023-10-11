### Oct 11, 2023

## TCL Commands

- COMMIT
- ROLLBACK
- SAVEPOINT

```
// Initial table
SELECT * FROM Employee;
+-----+--------+
| id  | name   |
+-----+--------+
| 110 | Oliver |
| 111 | Mark   |
| 112 | Blair  |
| 113 | Rose   |
| 114 | Prince |
| 115 | Smith  |
+-----+--------+
```

```
MariaDB [21CSB08]> start transaction;
Query OK, 0 rows affected (0.000 sec)

MariaDB [21CSB08]> INSERT INTO Employee VALUES(116, 'Privk');
Query OK, 1 row affected (0.000 sec)

MariaDB [21CSB08]> savepoint A;
Query OK, 0 rows affected (0.000 sec)

MariaDB [21CSB08]> INSERT INTO Employee VALUES(117, 'PC');
Query OK, 1 row affected (0.000 sec)

MariaDB [21CSB08]> savepoint B;
Query OK, 0 rows affected (0.000 sec)

MariaDB [21CSB08]> select * from Employee;
+-----+--------+
| id  | name   |
+-----+--------+
| 110 | Oliver |
| 111 | Mark   |
| 112 | Blair  |
| 113 | Rose   |
| 114 | Prince |
| 115 | Smith  |
| 116 | Privk  |
| 117 | PC     |
+-----+--------+
8 rows in set (0.000 sec)

MariaDB [21CSB08]> rollback to A;
Query OK, 0 rows affected (0.000 sec)
```
```
select * from Employee;
+-----+--------+
| id  | name   |
+-----+--------+
| 110 | Oliver |
| 111 | Mark   |
| 112 | Blair  |
| 113 | Rose   |
| 114 | Prince |
| 115 | Smith  |
| 116 | Privk  |
+-----+--------+
```
