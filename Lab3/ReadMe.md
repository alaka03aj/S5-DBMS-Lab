### Oct 4, 2023
## GROUP BY
```
select * from FOSS group by year;
```

### Output
```
+------------+------------------+-------------+-------+------+------------+------------+
| stud_id    | name             | role        | class | year | events_reg | phone      |
+------------+------------------+-------------+-------+------+------------+------------+
| MDL20CS052 | Jithin Jagadeesh | Chairperson | CSB   | 2024 |          6 | 1234567890 |
| MDL21CS022 | Annu Kuruvilla   | Design Head | CSB   | 2025 |          3 | 1234567894 |
+------------+------------------+-------------+-------+------+------------+------------+
2 rows in set (0.001 sec)
```

## ORDER BY

#### Ascending Order
```
select * from Clubs order by name;
```

### Output
```
+---------------+---------------+------------------+-----------------+------------+--------------+------------+---------------------+------------+
| club_id       | name          | lead_name        | faculty_advisor | founded_on | member_count | phone      | email               | lead_id    |
+---------------+---------------+------------------+-----------------+------------+--------------+------------+---------------------+------------+
| foss.mec      | FOSS MEC      | Jithin Jagadeesh | Sony P          |       2016 |          500 | 1234567890 | foss@mec.ac.in      | MDL20CS052 |
| gdsc.mec      | GDSC MEC      | Alaka A J        | Sreekumar K     |       2020 |          500 | 7306023848 | gdsc@mec.ac.in      | MDL21CS012 |
| iedc.mec      | IEDC MEC      | Ananya Daniel    | Sreekumar K     |       2021 |          500 | 1234567892 | iedc@mec.ac.in      | MDL20CS021 |
| macs.mec      | MACS MEC      | Binoy            | Aysha Fymin     |       2015 |          500 | 1234567891 | macs@mec.ac.in      | MDL20CS030 |
| tinkerhub.mec | Tinkerhub MEC | Anju Mohan       | Sreekumar K     |       2019 |          400 | 1234567893 | tinkerhub@mec.ac.in | MDL21EC018 |
| tle.mec       | TLE MEC       | Hanna Salam      | Sony P          |       2021 |          300 | 1234567894 | tle@mec.ac.in       | MDL20CS029 |
+---------------+---------------+------------------+-----------------+------------+--------------+------------+---------------------+------------+
6 rows in set (0.001 sec)
```

#### Descending Order

```
select * from Clubs order by name desc;
```

### Output 
```
+---------------+---------------+------------------+-----------------+------------+--------------+------------+---------------------+------------+
| club_id       | name          | lead_name        | faculty_advisor | founded_on | member_count | phone      | email               | lead_id    |
+---------------+---------------+------------------+-----------------+------------+--------------+------------+---------------------+------------+
| tle.mec       | TLE MEC       | Hanna Salam      | Sony P          |       2021 |          300 | 1234567894 | tle@mec.ac.in       | MDL20CS029 |
| tinkerhub.mec | Tinkerhub MEC | Anju Mohan       | Sreekumar K     |       2019 |          400 | 1234567893 | tinkerhub@mec.ac.in | MDL21EC018 |
| macs.mec      | MACS MEC      | Binoy            | Aysha Fymin     |       2015 |          500 | 1234567891 | macs@mec.ac.in      | MDL20CS030 |
| iedc.mec      | IEDC MEC      | Ananya Daniel    | Sreekumar K     |       2021 |          500 | 1234567892 | iedc@mec.ac.in      | MDL20CS021 |
| gdsc.mec      | GDSC MEC      | Alaka A J        | Sreekumar K     |       2020 |          500 | 7306023848 | gdsc@mec.ac.in      | MDL21CS012 |
| foss.mec      | FOSS MEC      | Jithin Jagadeesh | Sony P          |       2016 |          500 | 1234567890 | foss@mec.ac.in      | MDL20CS052 |
+---------------+---------------+------------------+-----------------+------------+--------------+------------+---------------------+------------+
6 rows in set (0.001 sec)
```
## GROUP BY - HAVING

```
select name, lead_name, founded_on from Clubs group by founded_on having founded_on > 2017;
```
### Output
```
+---------------+---------------+------------+
| name          | lead_name     | founded_on |
+---------------+---------------+------------+
| +Tinkerhub MEC | Anju Mohan    |       2019 |
| GDSC MEC      | Alaka A J     |       2020 |
| IEDC MEC      | Ananya Daniel |       2021 |
+---------------+---------------+------------+
3 rows in set (0.001 sec)
```

## UNION

```
select * from TLE union select * from FOSS;
```

### Output
```
+------------+------------------+------------------+-------+------+------------+------------+
| stud_id    | name             | role             | class | year | events_reg | phone      |
+------------+------------------+------------------+-------+------+------------+------------+
| MDL20CS021 | Arathy Sha       | Events Head      | CSA   | 2024 |          5 | 1234567892 |
| MDL20CS029 | Hanna Salam      | Chairperson      | CSB   | 2024 |          2 | 1234567890 |
| MDL20EC043 | Jeswin Thomas    | Vice Chairperson | ECA   | 2024 |          5 | 1234567891 |
| MDL21CS012 | Alaka A J        | Design Head      | CSB   | 2025 |          5 | 1234567894 |
| MDL21CS102 | Vignesh S Naik   | CP Head          | CSA   | 2025 |          5 | 1234567893 |
| MDL20CS052 | Jithin Jagadeesh | Chairperson      | CSB   | 2024 |          6 | 1234567890 |
| MDL20CS120 | Vishnu P         | Vice Chairperson | CSB   | 2024 |          2 | 1234567891 |
| MDL21CS022 | Annu Kuruvilla   | Design Head      | CSB   | 2025 |          3 | 1234567894 |
| MDL21CS055 | Karthik G Kumar  | Secretary        | CSA   | 2025 |          3 | 1234567893 |
| MDL21CS060 | Mekha L          | Marketing Head   | CSA   | 2025 |          3 | 1234567892 |
+------------+------------------+------------------+-------+------+------------+------------+
10 rows in set (0.001 sec)
```

