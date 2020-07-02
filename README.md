![picture](https://blog.plura.io/wp-content/uploads/2016/12/sql1.png)

# SQL-Injection
SQL injection is a code injection technique that might destroy your database.  SQL injection is one of the most common web hacking techniques.  SQL injection is the placement of malicious code in SQL statements, via web page input.

# Basic SQL

SQL is a standard language for storing, manipulating and retrieving data in databases.

1. Start mysql service and login. 

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture.png)

 2.  Create database name security. 

Syntax - create database Database_name;

Then use **show tables;** command to check tables exist in database.

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%201.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%201.png)

 3.  Now create table user and add column to it.

Syntax - Create table table_name(Column_name1 data_type, Column_name2 datatype, ....);   

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%202.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%202.png)

 4.  Insert values in table.

Syntax - Insert into table_name(Column_name1, Column_name2, ....) values (Value1, Value2, ....);

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%203.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%203.png)

 5.  To select all data in table user

command - Select * from user;

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%204.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%204.png)

 6.   To select database. use command - select database();

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%205.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%205.png)

 7.  To see all username present in table user. 

command - select username from user;

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%206.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%206.png)

 8.   Login query - **Select password from user where username = 'root';**

![Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%207.png](Basic%20SQL%20170077aa75f74023baa74a4c0a66d934/Capture%207.png)
