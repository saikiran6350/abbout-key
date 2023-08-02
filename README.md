# abbout-key

MariaDB [(none)]> create database company;
Query OK, 1 row affected (0.003 sec)

MariaDB [(none)]> create table info;
ERROR 1046 (3D000): No database selected
MariaDB [(none)]> use company;
Database changed
MariaDB [company]> create table info(customerid int(10),customername varchar(20),orderid int(10),location varchar(10));
Query OK, 0 rows affected (0.051 sec)

MariaDB [company]> desc info;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| customerid   | int(10)     | YES  |     | NULL    |       |
| customername | varchar(20) | YES  |     | NULL    |       |
| orderid      | int(10)     | YES  |     | NULL    |       |
| location     | varchar(10) | YES  |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
4 rows in set (0.023 sec)

MariaDB [company]> create table info(customerid int(10) not null primary ker,customername varchar(20) not null,orderid int(10),location varchar(10));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'ker,customername varchar(20) not null,orderid int(10),location varchar(10))' at line 1
MariaDB [company]> CREATE TABLE information(Cust_Id int Not Null, Name varchar(20) Not Null,   Country varchar(20) Not Null,     City varchar(20));
Query OK, 0 rows affected (0.282 sec)

MariaDB [company]> desc information;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| Cust_Id | int(11)     | NO   |     | NULL    |       |
| Name    | varchar(20) | NO   |     | NULL    |       |
| Country | varchar(20) | NO   |     | NULL    |       |
| City    | varchar(20) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
4 rows in set (0.080 sec)

MariaDB [company]> CREATE TABLE information (Cust_id int Not Null UNIQUE, Name varchar(20) Not Null, Country varchar(20) Not Null, City varchar(20));
ERROR 1050 (42S01): Table 'information' already exists
MariaDB [company]> CREATE TABLE data (Cust_id int Not Null UNIQUE, Name varchar(20) Not Null, Country varchar(20) Not Null, City varchar(20));
Query OK, 0 rows affected (0.061 sec)

MariaDB [company]> desc data;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| Cust_id | int(11)     | NO   | PRI | NULL    |       |
| Name    | varchar(20) | NO   |     | NULL    |       |
| Country | varchar(20) | NO   |     | NULL    |       |
| City    | varchar(20) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
4 rows in set (0.028 sec)

MariaDB [company]> CREATE TABLE personal_info (Cust_id int Not Null,  Name varchar(20) Not Null,  Country varchar(20) Not Null,  City varchar(20), PRIMARY KEY (Cust_id));
Query OK, 0 rows affected (0.057 sec)

MariaDB [company]> desc personal info;
ERROR 1146 (42S02): Table 'company.personal' doesn't exist
MariaDB [company]> desc personal_info;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| Cust_id | int(11)     | NO   | PRI | NULL    |       |
| Name    | varchar(20) | NO   |     | NULL    |       |
| Country | varchar(20) | NO   |     | NULL    |       |
| City    | varchar(20) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
4 rows in set (0.025 sec)

MariaDB [company]> CREATE TABLE order_info (Order_id int NOT NULL, Order_num int NOT NULL, Cust_id int, PRIMARY KEY (Order_id),    FOREIGN KEY (Cust_id) REFERENCES personal_info(Cust_id) );
Query OK, 0 rows affected (0.056 sec)

MariaDB [company]> desc order_info;
+-----------+---------+------+-----+---------+-------+
| Field     | Type    | Null | Key | Default | Extra |
+-----------+---------+------+-----+---------+-------+
| Order_id  | int(11) | NO   | PRI | NULL    |       |
| Order_num | int(11) | NO   |     | NULL    |       |
| Cust_id   | int(11) | YES  | MUL | NULL    |       |
+-----------+---------+------+-----+---------+-------+
3 rows in set (0.024 sec)
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| aaaa               |
| collage            |
| company            |
| info               |
| information_schema |
| mysql              |
| pavan              |
| performance_schema |
| phpmyadmin         |
| student            |
| studentinfo        |
| test               |
| vishnu             |
+--------------------+
13 rows in set (0.085 sec)

MariaDB [(none)]> use collage;
Database changed
MariaDB [collage]> create table data(id int primary key,name varchar(20),age int);
Query OK, 0 rows affected (0.054 sec)

MariaDB [collage]> desc data;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | NO   | PRI | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
| age   | int(11)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.025 sec)

MariaDB [collage]> insert into data(id,name,age)values(1001,'sai',18);
Query OK, 1 row affected (0.087 sec)

MariaDB [collage]> insert into data(id,name,age)values(1092,'ram',21);
Query OK, 1 row affected (0.006 sec)

MariaDB [collage]> insert into data(id,name,age)values(1023,'hari',19);
Query OK, 1 row affected (0.004 sec)

MariaDB [collage]> insert into data(id,name,age)values(1011,'vani'19);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '19)' at line 1
MariaDB [collage]> insert into data(id,name,age)values(1011,'vani,'19);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '19)' at line 1
MariaDB [collage]> insert into data(id,name,age)values(1011,'vani',19);
Query OK, 1 row affected (0.005 sec)

MariaDB [collage]> desc data;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | NO   | PRI | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
| age   | int(11)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.011 sec)

MariaDB [collage]> select*from data;
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1001 | sai  |   18 |
| 1011 | vani |   19 |
| 1023 | hari |   19 |
| 1092 | ram  |   21 |
+------+------+------+
4 rows in set (0.007 sec)

MariaDB [collage]> select*from data where name like '%hello%';
Empty set (0.011 sec)

MariaDB [collage]> select*from data where name like '%sai%';
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1001 | sai  |   18 |
+------+------+------+
1 row in set (0.000 sec)

MariaDB [collage]> select*from data where age in (15,16);
Empty set (0.003 sec)

MariaDB [collage]> select*from data where age in (age>17);
Empty set (0.004 sec)

MariaDB [collage]> select*from data where age in (age>18);
Empty set (0.000 sec)

MariaDB [collage]> select*from data where age in (18,20);
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1001 | sai  |   18 |
+------+------+------+
1 row in set (0.002 sec)

MariaDB [collage]>
MariaDB [collage]> select*from data where age=19;
+------+------+------+
| id   | name | age  |
+------+------+------+
| 1011 | vani |   19 |
| 1023 | hari |   19 |
+------+------+------+
2 rows in set (0.003 sec)

MariaDB [collage]>


