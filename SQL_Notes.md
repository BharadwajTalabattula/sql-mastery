# SQL- structured query language
* SQL is introduced by oracle  and currently SQL is under Oracle
* SQL is used to communitcate with database using queries;

# Database
* Database is storage location

# operations in SQL
* data insertation
* data update
* data delete
* data fetch

# database > folder
* folder system - data may be duplicated & multiple fles leading to redundancy and possible inconsistancy;
* database - uses normalization and constrains to minimize unnecesseryness & maintain data consistancy;


# data Security:
* Folder system: Limited access control (often just read/ write permissions)
vs
* Data base: provides user roles, authentication, and permissions ensuring that only authorized users can access or modify specific data;

# data Integrity
* Folder system: No built-in way to enforce rules like 'salary cannot be negative';
* data base: supports constrains(primary key, foreign key, check) to maintain data integrity;

# Efficient Querying
* folder system: Manual code to search, filter or sort
* Date base: use SQL to perform complex queries;

# concurrency: (multiple user access)
* folder system: hard to handle
* database: supports transaction management and concurrency control to allow safe multi user access;

# Backup & recovery
* folder system: Manual
* Data base: Built In recycle bin

# Data relationships
* Folder systems: hard to manage
* Data base: Built in support

-----------------------------------------------------------------------------------------------------------

# DBMS
* A DBMS is a software that allows users to store, retrive manipulate, and manage data in a structured way.
* it connects programmas with the database;

## Key Features
* Data storage: Stores data in tables(rows and columns)
* Querying: Use SQL to access and manipulate data;
* Data Security: Controls who can access what data
* concurrency: Multiple users can access data at the same time;
* Backup & Recovery: Protects against data loss;
* Data Integrity: Ensures occurancy and consisteucy;


# types of DBMS
* DBMS - database management system
* RDBMS - Relational database management system
* No SQL - Not only SQL (Non-relational databases)
* HDBMS - Hirarchial database management system
* NDBMS - Network database management system


#  ORDBMS VS RDBMS

# RDBMS :
* RDBMS stores the data in the table format
* it deals with rows and columns
* In case of RDMS relation defines parent-child table relation but its not mandatory to have that relation;

Ex: Oracle database, MySQL, ..etc

# ORDBMS - object-relational database managment systems
* It is used to store the data in a form of object inside tables;

-> Objects in tables

EX: PLSQL

``` sql
BEGIN
    INSERT INTO employees (employee_id, first_name, last_name, home_address, salary)
    VALUES (
        1,
        'John',
        'Doe',
        address_obj('123 Main St', 'Anytown', 12345), -- Use the constructor
        60000.00
    );

    INSERT INTO employees (employee_id, first_name, last_name, home_address, salary)
    VALUES (
        2,
        'Jane',
        'Smith',
        address_obj('456 Oak Ave', 'Otherville', 67890), -- Use the constructor
        75000.00
    );

    COMMIT;
END;
/

```

# No SQL
* store data as a collection of key-value pairs.
* document -> JSON for storing data
* deals keys & values
Ex: MongoDB

```JSON

student{
   id: 1,
   name: "Ram",
   age: 29
}
```
------------------------------------------------------------------------------------------------------------

# HDBMS
* It is store the data in three format
* In case of HDBMS data are not interconnected to each other
 
EX:

                  | -- Kashmire
       |-- hill --
       |          | -- Paharinath
Toip ---           
       |          | -- Puri
       | -- Sea --
                  | -- Goa

# NDBMS
* It is use to store that data in three format
* In case of NDBMS data are interconnected to each other

Ex:

         |--   shop  --|
         |             |
     shopkeeper     Customer
         |             |
         |-- Payment --|    




# SUB Languages of SQL

* DQL - Data Query Language
* DML - Data Manipulatation Language
* TCL - Transaction Control Language
* DDL - Data Defination Language
* DCL - Data Control Language


Note:
* All queries must be finished with semicolen;
* SQL is not complete case sensitive


# DQL
* DQL stands for data query language
* DQL is used for fetching the deatails by the help of queries 

* DQL have 3 clauses
1. SELECT
2. FROM
3. WHERE

# Select
* select clause is used for any specific column or all columns selection purpose;

# From
* from clause is used for decide the table name inside the DB;

# where
* Where clause is used for provide condition;


# SQL Queries
* SQL queries start execution with 'from' clause finish by 'select' clause


syntax:

``` SQL

> select colname, colname... 
 from table_name;
> select * from table_name;
> select * from all_users; -- to check all the user in oracle DB (In mysql 'Show' keyword is used)
> show users;
> select * from tab; -- to check all tables inside user;(show tables)
```
> conn userName;
password: ******* //To connect one user to another user

-------------------------------------------------------------------------------------------------------

# Employee table

+-------+--------+-----------+------+------------+----------+---------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL      | COMM    | DEPTNO |
+-------+--------+-----------+------+------------+----------+---------+--------+
|  1800 | VIKASH | HR        | NULL | 2024-11-13 | 12000.00 |    NULL |   NULL |
|  7369 | SMITH  | CLERK     | 7902 | 1980-11-17 |   800.00 |    NULL |     20 |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 |  1600.00 |  300.00 |     30 |
|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 |  1250.00 |  500.00 |     30 |
|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 |  2975.00 |    NULL |     20 |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 |  1250.00 | 1400.00 |     30 |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 |  2850.00 |    NULL |     30 |
|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 |  2450.00 |    NULL |     10 |
|  7788 | SCOTT  | ANALYST   | 7566 | 1987-04-19 |  3000.00 |    NULL |     20 |
|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 |  5000.00 |    NULL |     10 |
|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 |  1500.00 |    0.00 |     30 |
|  7876 | ADAMS  | CLERK     | 7788 | 1987-05-23 |  1100.00 |    NULL |     20 |
|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |   950.00 |    NULL |     30 |
|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 |  3000.00 |    NULL |     20 |
|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 |  1300.00 |    NULL |     10 |
+-------+--------+-----------+------+------------+----------+---------+--------+

# department table

+--------+------------+----------+
| DEPTNO | DNAME      | LOC      |
+--------+------------+----------+
|     10 | ACCOUNTING | NEW YORK |
|     20 | RESEARCH   | DALLAS   |
|     30 | SALES      | CHICAGO  |
|     40 | OPERATIONS | BOSTON   |
+--------+------------+----------+

# Examples

--> select * from dept; --display all details of department tables
--> select deptno, loc from dept; -- (display the deptno and the loc )
--> select dname from dept; -- display department names

# page setup

* set pages size lines size; -- for more column pages for more rows lines

# Examples

--> select * from emp; -- all details of emp tab
--> select ename, sal, deptno form emp; 
--> select empno, ename, job, comm from emp;
--> select deptno, dname from dept;
--> select ename, empno, mgr, from emp;
--> select ename, job, hiredate, sal from emp;


# Datatypes & literals:

* Oracel database has three datatypes;
* The values which are stored are known as literals;
* the type of literals are decided by data types;


SQL have three types datatype
--> number
--> varchar
--> date

# Number/ Decimal:

* Number datetypes are used to store number literals
* In case of number datatype size not mandatory;
* Number literals are not mandatory to provide inside single quote;


Example:

Nunber(size)      number(size, size)                                       number (w/o specific size)
  number(4)          number(6, 2) --> 6-2 = (4 digits before decimal)      19936    ✅ 
  1904  ✅            1993.35    ✅                                         10.33963 ✅ 
  99    ✅            100.50 --> 100.5 ✅                                   0.9999   ✅ 
  100   ✅             35.00 --> 35 ✅
  3     ✅             0.93 --> .93 ✅
  29063 ❌
  0     ✅



# Varchar:

* varchar datatypes are used to provide any type of character literals;
* In case of varchar datatype size is mandatory;
* varchar literals are mandatory to write inside single quote;
* varchar will accept size upto 2 bytes (VARCHAR2 for 4 bytes)

Example:

varchar(size)
 varchar(5)
 'ROHIT'   ✅       'A123'  ✅
 'Deep'    ✅       'AB-CD' ✅
 'Raj'     ✅       '@#!=>' ✅
 'a'       ✅       '3639'  ✅ 
 'de'      ✅
 'Monalisa'✅

 # Date:

 * Date datatype is used to store date literals by using 'DD-MON-YY' format;
 * Incase of date size is not required;
 * date literals are mandatory to write inside single quote; 

Example:

  date
I/P: '3-January-2015'           I/P: '31-NOV-2021' --> error❌ (31 is not present in nov) 
O/P: 03-JAN-15                 

I/P: '19-MAR-2000'             I/P: '29-Feb-2000'  
O/P: 19-MAR-00                  O/P: 29-FEB-00  

I/P : 19-11-2007 --> error ❌ (month number cannot be accepted)


EX:
date -- for oracle DB(dd-mm-yyyy) '19-JUL-15'
date -- for mysql(yyyy-mm--dd)    '15-06-19'


# desc- description
* it is used to check deatils of the table

EX: 
desc emp;
desc dept;


##  Operators
1. Arthimatic Operators(+ - * /)
2. Character Operators(||) -- used for concatination
3. Relational/Conditional Operators (=. !=. >, >=, <, <=)
4. Logical Operators (and, or, not)
5. Special Operators (as, in, between, like, is)
6. set operator (union, union all, intersect, minus)


# Dual
* Dual is a dummy table present in sql pluse soft internally
* Dual is used to work with our own literals

Ex: 
--> select 100 + 100 from dual;
--> select 'prattay' from dual;
--> Desc dual;


# Aliaising
* Aliaising means temporary renaming column val names or table names;
* Aliaising doesn't effect inside data base;
* To do aliaising special operator `as` we can use but its not mandatory for cloumn names;

Ex:
# col aliaising
--> select 'Ankita' as Name from Dual;
--> select (100+100) ADD VAALUE from Dual;
--> select hiredate date from emp;
--> select empno as id, sal as salary from emp;
--> select empno as 'emp  id' -- for printing with gap
--> select deptno did from dept;

# table aliaising
* for table name aliaising as keyword is not required;

Ex:
--> select * from emp e;
--> select * from emp as a; --Error

# Character operator
* character opeartor is used for concatination

Ex:
--> select 'ankita' || 'paul' as name from dual;
--> select 'good morning' || ename 'wishing' from dual;
--> select ename || 'working as a' || job || 'of department' || deptno || 'getting sal' || sal || '.' 'Employee Details' from emp;
select deptno||' '||dname as depdetails from dept;

o/p:

   DEPDETAILS
------------------
12 HR
10 ACCOUNTING
20 REASERCH
30 SALES
40 OPERATIONS

# Arthimatic Operators

Ex:

--> select ename, mgr, sal, sal +500 as 'increment sal' from emp;
--> select ename, hiredate, empno, sal-200, 'deduce sal' from emp;
--> select ename, job, comm 300 as 'deduce comm' from emp;
--> select ename, sal/31 as 'march sal', deptno from emp;
--> select ename, sal*12 'annual sal' from emp;
--> select hiredate, hiredate-10 from emp; -- work w/o error


# Relational Operator

Ex: 
--> select * from emp where ename = 'smith';
--> select ename, sal, deptno, hiredate from emp where deptno = 30;
--> select * from emp where job != 'clerk';
--> select * from emp where sal > 1500;
--> select * from dept where dname = 'SALES';
--> select *  from emp where hiredate < '13-DEC-81';
--> select ename, sal, sal(sal * 0.2) as hikesal from emp where comm <= 500;
--> select * from emp where sal >= 1500;


# Logical Operator
* In case of relational operator, we can satisfy only one condition at a time, to satisfy multiple conditions logical operators are introduced;

# AND
P	Q	P & Q
T	T	  T
T	F	  F
F	T	  F
F	F	  F
 
# OR
P	Q	P | Q
T	T	  T
T	F	  T
F	T	  T
F	F	  F

# NOT
P	!P
T	 F
F	 T


Syntax: 

Select colname, colname..from Tname
where con-1 logical op con-2 logical op con-3 logical op;


Ex:
--> select * from emp where Job = 'SALESMAN' AND sal > 1600;
--> select * from emp  where ename = 'SMITH' OR 
ename = 'MARTIN';
--> select * from emp where sal > 1500 AND sal < 4000;
--> select * from emp where Job = 'Analyst' AND (NOT Job = 'Manager');

# NOT op

syntax:

--> select * from emp where deptno != 30;
--> slect * from emp where not deptno = 30;

Ex:
--> select * from emp where (sal>1000 AND sal<1500) AND (COMM >300 AND COMM < 1500);

--> select * from emp where (job in ('manager', 'analyst')) AND (deptno in (20, 30)) AND sal > 2500;

--> select * from emp where not(deptno = 10 OR deptno = 20);

--> select * from emp where (job in ('Manager', 'Analyst')) AND (comm between 300 and 1000) AND (deptno not in (10, 20));


# Special Operator (IN / NOT IN);

* In is a special operator is used to fetch same column multiple deatils;

Syntax:

select colName, colName... from Tname
where colName in (data1, data2, data3..);

Ex:
--> select * from emp where ename in('smith', 'allen', 'martin', 'james', 'ward', 'miller');

--> select * from dept where dname in ('sales', 'accounting', 'research');

-->select * from emp where ename not in ('blake', 'martin', 'turnur');

--> select * from emp where (deptno in(20, 30)AND (Job not in ('manager', 'clear)));


# (Between / Not Between) Operator

* between is a special operator which is used to fetch the details in a range.

Syntax: 

select colName, colName... from Tname
where colName between range1 and range2;

Ex:

--> select * from emp where comm between 300 AND 900;

--> select ename, sal, job, deptno from emp where sal not between 2000 AND 3000;

--> select * from emp where (deptno in (10, 20, 30)) AND (hiredate between '1-JAN-82' AND '31-DEC-82');

--> select * from emp where (job not in ('clerk', 'manager', 'analyst')) AND (sal between 2000 and 4000);

# Like Operator

* Like is a special operator which is used to fetch data based on incomplete information;

* Like operator always accept data as characters

* There are two like operators

1. '_'
2. '%'

* % operator is used to fetch datas when user don't know length and missing position;

Ex:

1. %
2. 's%'
3. '%s%'
4. '%ll%'
5. '%l%l%'

*  - is used to fetch the details when know the length and missing position of data

Ex: 

1. 's__th'
2. '__ma'

Syntax:

select colName, colName... from Tname
where colName like 'pattern';


Ex:

--> select * from emp where ename like 's%';
--> select * from emp where ename like '%N';
--> select ename from emp where ename like '%A%';
--> select * from emp where ename like '%ll%';
--> select * from dept where like '%a%a%';
--> select * from emp where hiredate like '%-Dec-%';
--> select * from emp where hiredate like '%87';
--> select dname, from dept where dname like '_ _ _ ES';
--> select * from emp where ename NOT like '%M';
--> select * from emp where (mgr like ''7%) AND (mgr not like '%9');


# IS Operator 
* Is operator used to fetch the values based on null;

syntax:

select colName, colName.. from Tname
where colName is null;

--> select * from emp where mgr is null;
--> select ename, mgr, from emp where mgr is not null;

# DQL
* All commands are temporary 

# DML
* Data manipulation language

1. Insert  |
2. Update  | Temporary
3. Delete  |

# Insert

syntax

Insert into Tname
values (val1, val2, val3...); -- To insert all column data;

Insert into Tname(col1, col4, col5)
values (val1, val4, val5); -- To insert specific column data


Ex:

--> insert into emp values(100, 'smith', 'salesman', 160, '10-JAN-2014', 25000, 800, 30); 

* the data cannot be inserted when data violate constrain conditions

Ex:
```sql
* insert into emp values(100, 'smith', 'salesman', 160, '10-JAN-2014', 25000, 800, 30);  -- error unique constain
* insert into emp values(100, 'smith', 'salesman', 160, '10-JAN-2014', 25000, 800, 25);
--invalid Deptno
* insert into emp values(100, 'smith', 'salesman', 160, '10-JAN-2014', 250000, 800, 25); -- number is very large
* insert into emp values(100, 'smith', 'salesman', 160, '10-12-2014', 250000, 800, 25); -- not a valid month number is not recognies by oracle
* insert into emp values(100, 'smith', 'salesman', 160, '`31`-NOV-2014', 250000, 800, 25); -- Erro date format
* Insert into emp values (1900, 'Ankita', null, null, '5-Aug-2025', 1200, null null);
* Insert into emp (Empno, ename, deptno) values(1901, 'Elina', 19);
```

# Update

syntax

update Tname
set colName = value, colName = value,...
where condition;


Ex:

update emp
set job = 'Manager', sal = '5500.70', deptno = 20
where ename = 'MITA';

update emp
set sal = sal + (sal * 0.25)
where Job = 'Manager';


update emp 
set comm = 1000
where comm is null;

Note:

In case of update where condition is not mandatory if we don't use any where condition it will update all records for the column;

EX: 

update bonus set comm = 1900;

# Delete

syntax

delete from Tname
where condition;


Ex:
Delete from emp 
where empno = 100;

Note:
If two tables have parents child relation then it's child table data needs to delete then only parent table data will be deleted;

Ex:

# Emp is child table and dept is Parent table

Delete from emp 
where deptno = 19; -- 1 st

delete from dept
where deptno = 19; -- 2nd

Note:

In case of delete where condition is not mandatory to delete, if you use without 'where' all records will be deleted;


# TCL - transactions contol language
* Database operations are often grouped into transactions, which are a sequence of opeartions treated as  a single , indivisible unit of work;
EX:
  🅸 - insert
  🆄 - update
-- one transaction --
  🅸 - insert
  🅳 - delete 
  
-- 2nd transaction --

  when DMl commands executed within a transaction they are not perminantly saved into database.Insteared they held in temporary state awaiting a commit or rollbacl command;


* TCL is introduced to work with DML commands 
* TCL have 3 commands 

1. commit
2. savepoint
3. rollback

# Commit:

* commit is a TCL command which is used to save all DML operations permanantly in the database;

Syntax:

commit;

Ex: 
  🅸 - insert
  🆄 - update
  🅸 - insert
  🅳 - delete
commit; -- save the data permanantly in DB

# Rollback

* Rollback is a TCL command which is used to undo all the data operations temporarily;
* To make rollback permanent we have to use commit statement;
* when rollback is used without using savepoint, all uncommitted changes made since the beginning of the current transaction  are undone;

# Rollback has two syntax:

syntax

1. commit;            2. rollback;
   rollback;              commit;

Ex:

  🅸 - insert
  🆄 - update
  🅳 - delete
  🅸 - insert
Rollback; -- will undo temporaryily

# Savepoint

* It is a TCL command which is used to save all DML operations temporaryliy to make savepoint permanantly we have to use commit;
* undoing to savepoint: The savepoint command allows you to define a specific point within a transaction. * if rollback to savepoint_name; is used, only the changes made after the paticular savepoint  are undone;

Syntax:

Note: Savepoint cannot start with digit

**Rollback&commit(withSavepoint)**

-- start of transaction--

--step:1 initial operations
  🅸 - insert
  🆄 - update
  🅳 - delete

  savepoint a;

--step-2 more operations
  🅸 - insert
  🆄 - update
  🅸 - insert
  Savepoint b;

--step-3 Further operations
  🆄 - update
  🅳 - delete
  🅸 - insert
  savepoint c;
  Rollback to b; -- returns DB state to just after savepoint b was created; 

-- finalize the transaction
  commit;


--------------------------------
**Rollback&commit**

-- start of transaction--

  🅸 - insert
  🅳 - delete
  🅸 - insert

 rollback; -- suppose you realize something went wrong
 commit;

-----------------------------

# DDL - Data defination language(Permanent)

1. Create
2. Alter
    * alter add
    * alter rename
    * alter drop
    * alter modify
3. Turncate
4. Rename
5. Drop


# constrains

* Constrains are used to provide rules and regulations while creating a table;

* Constrains are not mandatory for table creation;

* they are 6 main constrains

1. NOT NULL
2. UNIQUE
3. CHECK
4. DEFAULT
5. PRIMARY KEY
6. FOREGIN KEY

+----+-----------------+-------------------+--------------------+----------------+--------------+
| id | constraint_name | allows_null_value | allows_multi_value | num_of_columns | applies_to   |
+----+-----------------+-------------------+--------------------+----------------+--------------+
|  1 | NOT NULL        |                 0 |                  1 |              1 | Column       |
|  2 | UNIQUE          |                 1 |                  0 |              1 | Column/Table |
|  3 | CHECK           |                 1 |                  1 |              1 | Column/Table |
|  4 | DEFAULT         |                 1 |                  1 |              1 | Column       |
|  5 | PRIMARY KEY     |                 0 |                  0 |              1 | Column/Table |
|  6 | FOREIGN KEY     |                 1 |                  1 |              2 | Table        |
+----+-----------------+-------------------+--------------------+----------------+--------------+


# NOT NULL

* If any columns declairs with not null constrains means that column cannot accept null values;

* Not Null allows duplicate values

* In a table their can be n number of columns decalred with Not Null;

# Unique

* In a tbale any ccolumns declair with unique means that column cannot accept any dupliacte or repeated values;

* Unique can allow null values;

* In a table n nuber of columns declare as unique

# Check

* In a table any column declared with check constraint means that column before inserting that data shall satisfy the condition;

* If the condition satisfied then only data inserted or updated otherwise not

* Check allows null and duplicate values;

* In a table n number of columns decalre as check;

# Default

* If user wants to provide by default same value multiple times for a column then that column in that table declared with default constraint;

* Default allows duplicate values, default allows null values alos but in explicit way;

* In a table n number of columns can be decalred as default;


# Primary key

* Primary key is a combination of unique and not null;

* Primary key doesn't allow any null and duplicate values;

* In a table only 1 column declair as primary key;

* If want to declare more than one column as primary key then have to use unique & Not Null constraints together;

# Foreign Key

* You define a foreign key in a "child" table by referencing the primary key of a "parent" table.

* foreign key is used to make parent child relation;

* foreign key can allow duplicate and null values;

* In a table n number of columns declared as foreign key;

Ex:

Customers - parent table

    CREATE TABLE Customers (
        customer_id INT PRIMARY KEY,
        name VARCHAR(50)
    );

Orders - child table

    CREATE TABLE Orders (
        order_id INT PRIMARY KEY,
        customer_id INT,
        order_date DATE,
        FOREIGN KEY (customer_id) REFERENCES Customers(customer_id)
    );

# Create

syntax

Create table Tname(
col1 datatype(size) constrain, 
col2 datatype(size) constrain, 
.
.
.
coln datatype(size) constrain);


Ex:

Create table ORDERS(
cust_name varchar(10),
ordate date,
amount number(6, 2));


create table seller(
 sname varchar(20) not null,
 pnum number unique, 
 loc varchar(30) );

--> Insert into seller values('Mohan', 4051928228, 'HSR'); -- row created

--> Insert into seller(pnum) values(909090909); -- Error due to Not null


**Foreign key**

create table product(
  pid number(4) primary key,
  pname varchar(10),
  price number(5, 2) default(100.5),
  exdate date check(exdate between('01-JAN-2026' and '01-JAN-2027'))
);

create table customer(
  cname varchar(15),
  payment_method varchar(15),
  pid number(4) reference product(pid)
);

* Foreigin key should be the primary key of the referenced/parent table;
* In the child table (e.g., the customer table), the foreign key column (e.g., pid) can and often does contain duplicate values and null values;


Ex:

CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(100)
);


CREATE TABLE OrderAssignments (
    AssignmentID INT PRIMARY KEY,
    OrderID INT,
    ProcessedByID INT, -- Role 1
    PackedByID INT,    -- Role 2

    -- This FK links 'ProcessedByID' to 'Employees.EmployeeID'
    FOREIGN KEY (ProcessedByID) REFERENCES Employees(EmployeeID),

    -- This FK links 'PackedByID' to 'Employees.EmployeeID'
    FOREIGN KEY (PackedByID) REFERENCES Employees(EmployeeID)
);


* We want an OrderAssignments table that tracks two things for a single order: who processed the order and who packed the order.

* In the OrderAssignments child table, both of these columns will link back to the same EmployeeID primary key in the parent Employees table.

* We are using two different column names (ProcessedByID and PackedByID) in the child table to fulfill different roles, even though both columns ultimately refer to the same primary key (EmployeeID) in the parent table (Employees).


# Alter Add

* alter add is used to add a new column at the last of the table permanently;

syntax

alter table Tname
add colName datatype(size) constaints;

Ex: alter table cour
add tname varchar(10);

Note: 
 To add a new column for existing tables with primary key and not null constrains the existing table must be empty;


# Alter rename

* It is used to change the column name for any table permenently;

syntax

alter table tname
rename column oldColName to newColName;


Ex:

alter table product
rename column exdate to date;



# Alter drop

* The drop column is used to delete a column permenently from a table;


syntax:

alter table Tname
drop column colName;

Ex:

alter table cour
drop column duration; --table altered

Note: 

when tables are having parent-child relation then first foreifn key of child table have to delete, then only primary key of parent table possible to delete;

book table is parent

alter table book
drop column bid; -- Erro cannot drop parent key

--fst

alter table author
drop column bid;

--then
alter table book
drop column bid; --table altered ✅

# Alter modify

* It is used to work with existing table column data type size & constrain permanently;

syntax:

Alter table tname
modify colname datatype(size) constrains;


Ex:
alter table order_details
modify cname number(15); -- Error alreday col has varchar data

alter table cour
modify tname number(10);

-----------------------------------------------------------------------------------------------------------
Date: 06-10-2025

# Rename
* It is used to change old table name to new table name permenantly;

syntax:

rename old Tname to new Tname;


Ex:

--> rename customer to cust;
--> rename product to prod;

# Truncate

* truncate is a DDL command which is used to delete all records in a table permenantly;

Syntax:

Truncate table Tname;

Ex:

--> truncate table order_details; --it delete all the records in table, not table
--> delete table book; -- it also delete table, but not permenent


# delete vs truncate

* truncate is a DDL command;
* truncate is used to delete all records present in a table permenantly;
* truncate does not require where condition;
* truncate need of any commit;
* truncate faster than delete;


* Delete is a DML command
* Delete is used to delete any specific record or all records temporaryly;
* To delete any specific records we required where condition;
* To make the delete permenent mandatorly have to commit;
* delete is slower than truncate;



# Drop

* drop is a DDL command which is used to delete the tables perminently from database;
* After deleting the tables, tables will store in side SQL recycle bin, If we want we can take it back to before condition;
* If two tables have parent child relation then we have to delete child table first then only able to delete parent table;

syntax:

drop table Tname;

Ex:

--> drop table order_details;
--> drop table payment;

## Parent child operation

Ex:
book table is parent

drop table book; -- Erro cannot drop parent key

--fst

drop table author;

--then
drop table book; --table dropped ✅

# recycle bin (for mysql their is not built in recyclebin)

* To check recyclebin;

syntax

show recyclebin;


* To return back a table from recycle bin to before stage

syntax

> Flashback table Tname to before drop;

* To delete any specific table from recyclebin

syntax

> Purge table Tname;

* To clean recyclebin

**syntax**
> purge recyclebin;


Ex:
```sql
> drop table seller;
> drop Dis_details;
> show recyclebin; -- it display seller,Dis_details tables with address and time deleted
> flashback table seller to befor drop; --it restores seller
> select * from tab;
> purge table Dis_details; -- Dis_details deleted from recyclebin
> purge recyclebin -- clearn full RB
```

**IMP**
# NOTE(parentchild relation after drop ):

* IF two tables have parent child relation and we delete the child table then that table is stored inside then recyclebin, and the parent child relation is break;
* If we return back child table from recyclebin to database then also relation will not exist;


Ex:

```sql
--cutomer is child and product is parent--
> insert into cust values('ram', 'f', 234, 3, 101) --> where 3 is the pid, where 3 doen't exist in product table so error;
> drop table cust;
> flashback table cust to brefore drop;
> insert into cust values('ram', 'f', 234, 3, 101) --> row inserted sinces their is not parent child relation b/w product and cust;
```

# recreate the child and parent relation

alter modify can also be used only when the primary key values in the child tables is not modiffiled;
drop, alter add ✅

-----------------------------------------------------------------------------------------------------------
# DCL (Data Control language)

* DCL all commands are permanent
* DCL have two commands grant and revoke

# connect one user to another

syntax

> conn userName;
> password:********;


# Grant
* Grant is the DCL command which is used to provide the permission to access their tables from one user to another user;
* user to user can grant insert, update, delete, select permissions;
* admin to user can grant inside update deleter select create permissions;

syntax:

> grant privilages on object to users;
> grant all on object to users;

Ex:
**senario-1**
```SQl
-- current user is scott--
> grant select, insert on stud to hr; -- select, insert permissions are provided to hr
> conn hr;
> Enter password:****;
> show user; -- user is HR
-- current user is hr--
> select * from scott.stud; --display table ✅
> insert into scott.stud values(4, 'rita', 23, 102, 1002 ); --row created ✅
> update scott.stud set sname='ram' where cid = 102; -- no permission ❌ 
```
**senario-2**
```SQl
-- current user is scott--
> grant all on cust to hr; -- all operation permession are grandted to hr
> conn hr;
> Enter password:****;
> show user; -- user is HR
-- current user is hr--
> select * from scott.cust; --display table ✅
> insert into scott.cust values(4, 'rita', 23, 102, 1002 ); --row created ✅
> update scott.cust set mailid = 900 where cid = 102; --row updated ✅
> delete scott.cust where cid = 101; --row deleted ✅
```

# Revoke
* revoke is a DCL command which is used to take back all granted permissions from user to another user to access their tables;

syntax

> revoke privilages on object from users;
> revoke all on object from users;


Ex:

```SQl
-- current user is scott--
> revoke select on dept from hr; 
> revoke select, insert on stud from hr; 
> revoke all on cust from hr; 
> conn hr;
> Enter password:****;
> show user; -- user is HR
-- current user is hr--
> select from dept; --  select operations doesn't work on dept table
> select , insert from stud-- select,insert operations doesn't work on stud table
> select, insert, update, delete from cust;-- all operations doesn't work on cust table
```

# create a newuser

syntax

> conn admin
> Enter password: ****;
> create user userName identified by password;
> grant connect to user;
> grant all privilages to user;

Ex:

```SQl

> select * from all_users; -- 27 users are present
> conn system;
> Enter Password:****;
> create user ankita identified by world; -- user created
> grand connect to ankita; -- it mandatory, if not, user cannot able to admin
> grand all privilages to ankita; -- if not given to user, user cannot to do inset,create, delete, or update..
> select * from all_users; -- new user add with name ankita (Now 28 users)
> conn ankita;
> Enter password: *****;
-- current user is ankita--
-- Now start creating tables under ankita user --
```

# deleting user(No recyclebin option)

syntax

> conn admin; --system is admin
> drop user userName cascade;

Ex:


```SQl

> select * from all_users; -- 28 users are present
> conn system;
> Enter Password:****;
--current user is system--
> drop user ankita cascade; --27 users, ankita is deleted,
-- when you delete a user all data inside it will be earised, No backoption is available--
```

-----------------------------------------------------------------------------------------------------------
Date: 12-Nov-2025

# Index:

* while we are writing multiple queries by using same column as condition at that time processer have to check each and every memory location for searching that column multiple times for multiple queries.

* so processer will get loacted and output will come in delay. to solve this problem `index` are introduced in SQL;

* AFter creating `index` processer don't search each and every memory beacuse processer well know about memory loaction. 

* the advantages of createing `index` are:

1. it will reduce the C.P.U cost 
2. it is helps to quick search



EX:

* when you write a condition like select * from emp where deptno = 10;

<!-- before index -->

                    EMP table
Cpu ----> empno, sal, ename, ...... deptno // everytime it check all the columns until it finds deptno

<!--  after index -->
                    EMP table
cpu ----> deptno; // cpu directly finds deptno



# Syntax for creating index:

* to check execution plan:
> set autotrace on explain;

* The syntax of creating index:
> create index indexName on Tname(col1, col2....);

* delete the index
> drop  index indexName;

* to set execution plan off:
> set autotrace off explain;


Ex:

```sql
> set autotace on explain;
> select * from emp where deptno =10; -- CPU takes more time to search
> create index did on emp(deptno); -- indexcreated
> select * from emp where deptno =10; -- CPU directly get the index
> create index did on emp(sal); -- error nameis already used by the existing obj
> create index salary on emp (deptno); -- such column list already indexed
> select ename from emp where sal>2000;
> create index salary on emp(sal);
> create index details on emp (ename, job);
> select * from emp where ename = 'SMITH' or job = 'CLERK'; -- it is not checked index
> select * from emp where ename = 'SMITH' AND job = 'CLERK'; -- it is checked index
> create index EMP_DETAILS ON EMP(ENAME, DEPTNO);
> drop index salary;
> drop index Did;
> drop index details;
> drop index emp_details;

```


* they are two  types of index:

1. cluster index
2. Non-cluster index

# Cluster index
1. in a table only one index is possible to create then that is known as cluster index;
2. cluster index requires less memeory;
3. data retrival is faster 
4 insert update delete operations are slower for cluster index;

# non-cluser index
1. If a table more than one indexes are possible to create then that is known as non-cluster index;
2. non-cluster index more memory
3. data retrival is slower 
4 insert update delete operations are faster for non-cluster index;

-----------------------------------------------------------------------------------------------------------
Date: 13-Nov-2025


# Functions:

* functions are set of statements which are introduced to do some specific task;
* SQL have two types of functions

1. Single row function
2. multirow function

# Single row function

* These functions are used to work with every rows in a column, and provide multiple multilpe outputs.
* these functions are used inside select, where, groupby, orderby cloues; 


# multirow functions(aggrgate functions)

* This functions are used to work with every rows in a column, and provide single output;
* These functions are used inside select, groupby, orderby, having cloues; but cannout use inside where cloues;


                                            Functions
                                                |
                              ------------------------------------
                              |                                  |
                 single row funciton                      Multi row funciton
                    |                                         |
                    |            |--> mod()                   |
                    |            |--> power()                 |-->max()  
                    |            |--> sqrt()                  |-->min() 
                    |            |--> abs()                   |-->sum()
                    |--> Number--|--> floor()                 |-->avg()  
                    |    func    |--> ceil()                  |-->count() 
                    |            |--> round()
                    |
                    |                
                    |               |-->upper()
                    |               |-->lower()
                    |               |-->trim()
                    |               |-->initcap()
                    |               |-->replace()
                    |--> Character--|-->concat()
                    |    func       |-->substr()
                    |               |-->instr()
                    |               |-->length()
                    |
                    |               |-->sysdate
                    |               |-->current_date
                    |               |-->current_timeStamp
                    |--> date ------|-->sessiontimezone
                    |    func       |-->Last_day()
                    |               |-->Months_between()
                    |
                    |
                    |                 |--> to_date()
                    |                 | 
                    |--> convertion --|
                    |    func         |  
                    |                 |--> to_char()
        

# MOD(value, divider)

Ex:
```sql
> select mod(1239, 10) from dual; -- 9
> select mod(1239, 11) modval from dual; --7
> select mod(348.34, 3) from dual; --.34
> select mod(-239, 10) from dual; -- 9
> select sal, mod(sal, 2) from emp; --14 rows created
> select hiredate, mod(hiredate, 2) from emp; --error expected number got date
```

# power(base, power value)

Ex:
```sql
> select power(-5, 5) from dual; -- -3125
> select power(12, 3) from dual; -- 1728
> select power(131, -2) from dual; -- 0.00058272
> select deptno, power(deptno, 3) from dept; -- row created
```

# sqrt(value) - not accept negative values

Ex:
```sql
> select sqrt(121) from dual;--11
> select sqrt(454.33) from dual; --21.315
> select sqrt(-144) from dual; -- error
```

# abs(value)

Ex:

```sql
> select abs(-12) from dual; -- 12
> select abs(-156.67) from dual; -- 156.67
> select abs(20) from dual; -- 20


```

# floor(arg)

Ex:

```sql
> select floor(5.1) from dual; -- 5
> select floor(5.4) from dual; -- 5
> select floor(5.9) from dual; -- 5
```

# ceil(arg)


Ex:

```sql
> select floor(5.1) from dual; -- 6
> select floor(5.4) from dual; -- 6
> select floor(5.9) from dual; -- 6
```

# round(arg)

Ex:

```sql
> select round(5.1) from dual; -- 5
> select round(5.4) from dual; -- 5
> select round(5.5) from dual; -- 6
> select round(5.9) from dual; -- 6
> select round(5.9999) from dual; -- 6
```
------------------------------------------------------------------------------------------------------------
Date: 14-Nov-2025 

# length(arg): 

* this function is used to calculate the length of input ;

Ex:

```sql
> select length(ename) L-N, length(ename)/2 H_L_N from ename;
-- WAQTD all emp name after converting lower case who's name consist more then 5 character

> select lower(ename) name from emp where length(ename) > 5;
```

# trim(arg):

* Function removes specified characters from the beginning, end, or both ends of a string. By default, if no character is specified, it removes leading and trailing spaces. 

Ex:
```sql
> select trim(' ravi ') from dual;
```


# initcap():

* it is a string manipulation function that converts the first letter of each word in a given string to uppercase and all other letters to lowercase.


Ex:
```sql
> select initcap('ravi kumar ekk') from dual; -- Ravi kumar ekk
```

# concat(arg1, arg2):
*  function in SQL is a string function used to combine two or more string values into a single string.

Ex
```sql
> select concat('Ravi', 'ekka') from dual;
> select concat('Ravi', concat('', 'ekka')) from dual;
```

# replace:

* this syntax is used for replacing the old character to new character with the given character;

syntax:

replace(arg1, arg2, arg3);
1. input character
2. old character
3. new character

Ex:

```sql
> select replace('Ravi', 'R', 'r') from dual;
> select replace(hiredate, 'DEC', 'JUN') from dual;
> select replace('good boy') from dual;
> select dname replace(dname, 's') from dual;
> select replace ('346796', '6') from dual;


-- WAQTD in a sentance 'have a good day' how many 'a' are present?
> select 'a', length('have a good day') length(replace('have a good day', 'a')) from dual;

```

# instr

* this function is used to provide index value of given input

syntax - 
 instr(arg1, arg2)
        i/p   char
instr(arg1, arg2, arg3, arg4);
       i/p  char index val occurence

------------------------------------------------------------------------------------------------------------
Date: 17-Nov-2025
# instr():

Syntax:
-8 -7 -6 -5 -4 -3 -2 -1
 g  o  o  d     b  o  y
 1  2  3  4  5  6  7  8


Ex: 

```sql
> select instr('good boy', 'o') from dual; --2
> select instr('good boy', 'a') from dual; --0
> select dname, instr(dname, 'A') from dept: --0, 1, 5, 2, 5
> select instr('goodboy', '0', 15) from dual; --0
> select instr('good boy', 'o', 2, 3) from dual; -- 7
> select instr('good boy', 'o', 1, 2) from dual; -- 3
> select instr('good boy', 'o', 2, 4) from dual; --0
> select instr('banana', 'an', 2, 2) from dual; --4


-- WAQTD the employee names whos name are consist minimum two 'AA' with out using like operator
> select ename from emp where instr(ename, 'A', 1, 2) != 0 ;

```

# substr():

* this function is used to fetch the group of characters;

Syntax:
-8 -7 -6 -5 -4 -3 -2 -1
 g  o  o  d     b  o  y
 1  2  3  4  5  6  7  8

 substr(arg1, arg2, arg3);-- arg3 is optional, this works only from left to right even when you give negavtive values  as index number;

 1. arg1 - input string
 2. ard2 - iindex value
 3. arg3 - No of characters

EX:

```sql
> select substr('good boy', 3, 6) from dual;-- OD BOY
> select substr('good boy', 10, 3) from dual; -- D BOY
> select substr('good boy', 3, 3) from dual; -- OD 
> select substr('good boy', 4, -2) from dual; --  
> select substr('good boy', -5, 4) from dual; -- GOOD
> select ename, substr('ename', -2) from emp; -- all enamelasr two letters in emp table
> select hiredate, substr(Hiredate, 4, 3) from emp; --all months in the date
-- WAQTD all employee names after removing first letter
> select substr('ename', 2) from emp; 
-- WAQTD every employee names after removing the last character
> select NOT substr('ename', -2) from emp; -- check if it is correct?
>  select substr('ename', 1, length(ename)-1) from emp;
-- waqtd every enmaes, and display the emp name after removing strating and ending letters;
> select ename, substr('ename', 2, lenght(ename -2)) from emp;

 --Assignment--

-- WAQTD all deatils of the dept when working loaction starting with 'D' and ending with 's'
> select * from dept where (instr(loc, 'D') = 1) AND (instr(loc, 's') = length(loc));
-- WAQTD last two letters of every working location
> select substr(loc, lenght(loc -1), 2) from dept;
-- WAQTD every department name and first three letters of every department name
> select substr(dname, 1, 3) from dept;
```
------------------------------------------------------------------------------------------------------------Date: 18-Nov-2025
                 
# Date functions

# sysdate
* this function is used to fetch todays current date based on oracle

Ex:
> select sysdate from dual;
 
sol:
 sysDate
 ---------
18-nov-2025


# current_date

* this function is used to fetch todays current date based on out P.C;

Ex:
select current_date from dual;

sol:
 Current_D
 ----------
18-nov-2025

# sessiontimezone:

* this function is used to fetch time zone ;

Ex:
select sessiontimezone from dual;


sol:
SESSIONTIMEZONE
 --------------
+05:30


# current_timestamp
* This function is used to fetch todays current date, time, timezone

Ex:
> select current_timestamp from dual;

sol:

CURRENT_TIMESTAMP
 ----------------
 18-Nov-2025 09.58.17.539000 AM +05:30


# Last_day(arg)
* this function is used to fetch last date of provided input month;


Ex:
> select last_day('12-mar-2024') from dual;

LAST_DAY
 --------
31-MAR-24

> select last_day(sysdate) from dual;

 Last_day
 ---------
 30_Nov-25

# months_between(arg1, arg2)

* This function is used to fetch months gap of provided inputs 

Ex:

```sql
> select months_between('01-jan-2025', '01-jan-2024') from dual; -- 12
> select months_between('01-jul-2025', '01-jan-2025') from dual; -- 6
> select months_between('11-jul-2025', '21-jan-2025') from dual; -- 5.677
> select months_between('14-mar-2025', '21-nov-2024') from dual; -- 3.774
> select months_between(sysdate, hiredate) from emp; -- 548.324 months

--WAQTD all employee names, sal, designation, years of experiance who are having more than 43 years of experiance
> select ename, sal, job, months_between(sysdate, hiredate)/12 YOE from emp where months_between(sysdate, hiredate) > 516;

```

# to_date(arg1, arg2)

* This function 

Ex:

```sql
> select to_date('11-10-1998', 'dd-mm-yyyy') from dual; -- 11-OCT-98
> select to_date('11-10-1998', 'mm-dd-yyyy') from dual; --10-nov-1998
> select to_date('21-03-19', 'yy-dd-mm') from dual; --Error not a valid month
> select to_date('21-03-19', 'yy-mm-dd') from dual; -- 19-MAR-21
> insert into emp(empno, ename, hiredate) values(100, 'mohit', '11-02-2025'); --error
> insert into emp(empno, ename, hiredate) values(100, 'mohit',  to_date('11-02-2025', 'dd-mm-yyyy'));
-- 1 row created 

```


# to_char(arg1, arg2)

* 

syntax:

to_char(arg1, arg2);
        date  format
        date   'yyyy' --> 2025
        date   'year' --> twenty twenty five
        date  'month' --> november
        date   'mm'  --> 11th month
        date   'day'  --> monday
        date     'd'  ---> 1 to 7, 1 for sun, 7 for saturday
        date 'hh:mi:ss' ---> current time

Ex:

```sql
> select to_char(sysdate, 'month') from dual; -- november
> select to_char(hiredate, 'MONTH') from dual; -- NOVEMBER
> select to_char(sysdate, 'MM') from dual; -- 11
> select to_char(hiredate, 'MONTH'), to_char(hiredate, 'mm') from emp; -- DECEMBER 12
> select to_char(hiredate, 'Day') from emp; -- wednesday
> select to_char(hiredate, 'day'), to_char(hiredate, 'd') from emp; -- wednesday 4
```
-----------------------------------------------------------------------------------------------------------
Date: 19-Nov-2025

``` sql
-- WAQTD all emp names, sal, day of joining who are joined in a company on saturday;

> select ename, sal, to_char(hiredate, 'DAY') DOFJOIN from emp where TRIM(to_char(HIREDATE, 'DAY')) = 'SATURDAY';

--WAQTD todays current time;

> select to_char(sysdate, 'hh:mi:ss') from dual;

```

# multi row functions

# MAX(arg):

* This function is work with every rows in a column and provide the maximum value of that column as output;
* This function is work with varchar, number, date, number literals

Ex:
```sql
> select max(800) from dual; --800
> select max(sal) from emp; -- 5000
> select max(mgr) from empl -- 7902
> select max(hiredate) from emp;  --23-may-87
> select max(ename) from emp; -- VARD
```

# MIN(arg):

* This function is work with every rows in a column and provide minimum value of that column as output;
* This function is work with number varchar date literals;

EX:
```sql
> select min(sal) from emp; -- 800
> select min(comm) from emp; --0
> select min(ename) from emp; -- ADAMS
> select min(hiredate) from emp; -- 17-DEC-80
```

# SUM(arg):

* This function is used to add all the values present in provided column, and provide output the addition value 
* This function is only work with number literals;

Ex:
```sql
> select sum(sal) from emp; -- 29025
> select sum(comm) from emp; -- 2200
> select sum(Deptno) from dept; -- 100
> select sum(ename) from emp; --error
> select sum(hiredate) from emp; --error

```
# AUG(arg):

* This function is used to provide average value of given column;
* This function only work with number literals;


Ex:
```sql
> select aug(sal) from emp; -- 2073.21429
> select aug(comm) from emp; -- 550
> select aug(deptno) from emp; -- 25
> select aug(ename) from emp; ---error
> select aug(hiredate) from emp; -- error
```

```sql
-- WAQTD the max sal among all sales man;
< select Max(sal) MAXSAL from emp where job = 'salesman';
-- WAQTD the min sal of dept '20';
> select MIN(sal) MINSAL from emp where deptno = 20;
-- WAQTD the total sal of the employees who are working under reporting mananger
> select SUM(sal) TSAL from emp where  mgr != 'null';
-- WAQTD the average comm  of the employees when emplyess are getting salary in between 1000 to 1500
> select AVG(comm) AVGCOMM from emp where sal between 1000 AND 1500 ;

```

# COUNT(arg):

* This function is used to count how many datas are present for that paticular column 
* this function is work with number, varchar, date, literals;

EX:
```sql
> select count(ename) from emp; --14
> select count(mgr) from emp; --13
> select count(COMM) from emp; --4
> select count(hiredate) from emp; --14
> select count(*) from emp; --14


--WAQTD how many employess are working as manager
> select count(job) NOOFEMP from emp where job = 'MANAGER';
> select count(*) NOOFEMP from emp where job = 'MANAGER';

-- WAQTD how many employess are getting odd salaries;
> select count(sal) from emp where (sal % 2)!= 0;

```
------------------------------------------------------------------------------------------------------------
Date: 20-Nov-2025

# SUB QUERY

syntax:

```sql
select colName, colName,...        |
from TName                         |---> outer query
where (subQuery);                  |
          |----------inner query


select colName,colName...
from (subquery) --> inner query
where condition;

```

```sql

-- WAQTD all details of the employee who is getting maximum salary 
> select * from emp where sal = (select max(sal) from emp); -- will not work if you use cond sal = max(sal)
                       |                 |---inner query
                       |-----outer query

-- WAQTD all details of employee who is getting minimum salary
> select * from emp where sal = (select min(sal) from emp);

-- WAQTD all details of the employee who are getting salary more than complete employee table average salary
> select * from emp where sal > (select avg(sal) from emp);

-- WAQTD all details of the employees who are getting salary below salesman's avg salary
> select * from emp where sal < (select avg(sal) from emp where job = 'salesman');

-- WAQTD all details of the employee who are getting salary below all salesmans average salary but salesman's details should not display;
> select * from emp where sal < (select avg(sal) from emp where job = 'salesman') AND job Not in ('salesman');

-- WAQTD all details of the managers who is getting maximum salary above all managers 
> select * from emp where job = 'manager' AND sal = (select max(sal) from emp where job = 'manager');

-- WAQTD all details of the analyst who are getting salary more than all salesman's average salary
> select * from emp where job = 'analyst' AND  sal > (select avg(sal) from emp where job = 'salesman');

-- WAQTD second higest salary of employee table 
> select max(sal) from emp where sal < (select max(sal) from emp); 

-- WAQTD all deatils of the employee who is getting second higest salary
> select * from emp where sal = (select max(sal) from emp where sal < (select max(sal) from emp));

-- 1.wartd 2nd minimum salary.
> select min(sal) from emp where sal != (select min(sal) from emp);
-- 2.waqtd all employees name, salary,job, hiredate who are getting 2nd minimum salary.
> select ename, sal, job, hiredate from emp where sal = (select min(sal) from emp where sal != (select min(sal) from emp));

-- 3.waqtd all details of employees whose annual salary is more than ward's annual salary.
> select * from emp where sal * 12 > (select sal * 12 from emp where ename = 'ward');


-- 4.waqtd all details of employees whose salary is more than clerk's avarage salary but they should not work in department 10 and 20.
> select * from emp where sal > (select Avg(sal) from emp where job = 'clerk') AND  deptno Not in (10, 20);


-- 5. waqtd the salesman name who is getting minimum salary among all salesman.
> select ename from emp where sal = (select min(sal) from emp where job = 'salesman') AND job = 'salesman';


-- 7.waqtd the most recently joined employee details.
> select * from emp where hiredate = (select max(hiredate) from emp);

```

------------------------------------------------------------------------------------------------------------
Date: 21-Nov-2025


```sql
-- WAQTD all details of the employee who is getting minimum and maximun salary
> select * from emp where sal = (select min(sal) from emp) OR sal = (select max(sal) from emp);
> select * from emp where sal in ((select min(sal) from emp), (select max(sal) from emp));

-- WAQTD all details of the employee who's department number is same as smith's number and job role is same as blake job role
> select * from emp where deptno = (select deptno from emp where ename = 'smith') AND job = (select job from emp where ename = 'blake');

-- WAQTD all details of the employee whos job role is same as allen's job role but they are getting salary  more than james salary and allen and james details should not display
> select * from emp where job = (select job from emp where ename = 'allen') AND sal > (select sal from emp where ename = 'james') AND ename NOT IN ('allen', 'james');

-- WAQTD all details of allen's manager 
> select * from emp where empno = (select mgr from emp where ename = 'ward');

-- WAQTD all details of the employees who are working under king 
> select * from emp where mgr = (select empno from emp where ename = 'king');

-- WAQTD all details of allen's manager's manager

select * from emp where empno = (select mgr from emp where empno = (select mgr from emp where ename = 'allen' ));

```
-----------------------------------------------------------------------------------------------------------
Date: 22-nov-2025

```sql
-- WAQTD all details of employee who are working in sales department;
> select * from emp where deptno = (select deptno from dept where dname = 'sales');

-- WAQTD all details of the sales man who are working in sales department
> select * from emp where deptno = (select deptno from dept where dname = 'sales') AND job = 'salesman';

--WAQTD the department details of smith allen martin  james

> select * from dept where deptno in (select deptno from emp where ename in ('smith', 'allen', 'martin', 'james'));

-- WAQTD the department name and working location of the employees when  employee names consistest in 
> select dname, loc from dept where deptno in (select deptno from emp where ename LIKE '%A%');

-- WAQTD all details of the employees who are getting salary more than 1000 less than 3000 and working in accounting department

-- WAQTD all details of the employee whos working location consists minimum two 'AA';

-- WAQTD all details of the department when employees are getting salary in between 1500 to 3000 AND working as manager 

-- WAQTD the department name of the employees who are not getting any commission

-- WAQTD to display the working location of all sales man and clerk 

```



```sql

--WAQTD the deptname of the employees who are getting even salaryies
> select dname from dept where deptno in (select deptno from emp where (sal%2 = 0));

-- WAQTD to display the department details of james's manager

> select * from dept where deptno = (select deptno from emp where empno = (select mgr from emp where ename = 'james'));

--WAQTD all details of the employee who's working location  is same as allen's working location

> select * from emp where deptno = (select deptno from dept where loc = (select loc from dept where deptno = (select deptno from emp where ename = 'allen')));

--WAQTD all details of the employees except allen who's working location is same as allen's working location 

-- WAQTD to display the department name of the employee who is getting second higest salary 
> select dname from dept where deptno in (select deptno from emp where sal = (select max(sal) from emp where sal != (select max(sal) from emp)));


```
------------------------------------------------------------------------------------------------------------
Date: 24-Nov-2025

# Distinct:

* It is a keyword which is used to fetch the unique data of the provided columns;

syntax:

Select distinct colname, colname...
from Tname
where condition;


Example:

```sql

> select distinct job from emp;
> select distinct deptno from emp;
> select distinct job from emp where sal > 2000;
> select distinct * from emp;
> select distinct comm from emp;

```

# order by:

* It is a clause in sql which is used to arrange the details either asending order or desending order;

syntax:

select col1, col2,....
from tname
where condition order by colname order;

Ex:

```sql

> select sal from emp order by sal desc;
> select job from emp where sal > 2000 order by job asc;
> select comm from emp order by comm;
> select mgr from emp order by comm;
> select * from emp order bu mgr desc;
> select ename, sal from emp order by sal asc, ename desc;
> select ename, sal from emp order by sal asc, ename asc;
> select distinct job from emp where sal > 1200 order by job;
```

# RowNum 

* Rownum puesdo column which is used to provide sequencial row numbers in a table;

* Rownum always start working from first row;


```sql

> select rownum from emp;
> select ename, sal, Rownum from emp;
> select * from emp where Rownum <= 5;
> select * from emp where rownum = 1;
> select * from emp order by rownum desc;
> select * from emp order by rownum desc;



-- WAQTD first 10 unique emp name after a range asc order
> select distinct, ename from emp where rownum <=10 order by ename asc;

-- WAQTD  how many unique job role are present in the emp table
> select distinct job from emp;
> select count(distinct job) from emp;

-- WAQTD are unique job role and its length
> select distinct job, length(job) from emp;

-- WAQTD first half of emp table all details;
> select * from emp where rownum <= floor(count(*)/2);
> select * from emp where rownum = (select round count(*)/2 from emp);

-- WAQTD last record of emp table
> select * from (select emp. rownum  from emp order by rownum desc) where rownum = 1;

-- WAQTD alternate records of emp table
> select * from (select emp, * rownum as rownum from emp) where mod(rownum, 2) != 0;

-- WAQTD forth higest sal
> select min(sal) from (select distinct sal from emp order by sal desc) where rownum <= 4;

> select sal from (select sal from (select distinct sal from emp w=order by sal desc ) where rownum <= 4 order by sal asc) where rownum = 1;


```
------------------------------------------------------------------------------------------------------------
Date: 26-Nov-2025

```sql
--WAQTD all details of the employee who is getting 4th higest salary
> select * from emp where sal = (select min(sal) from (select distinct sal from emp order by sal desc) where rownum <= 4);

> select * from emp where sal = (select sal from (select sal from (select distinct sal from emp order by sal desc) where rownum <= 4 order by sal) where rownum = 1);

--WAQTD  all details of employee where who are getting 4th higest salary
> select dname from dept where deptno in (select deptno from emp where sal = (select sal from (select sal from (select distinct sal from emp order by sal desc) where rownum <= 4 order by sal) where rownum=1));


--WAQTD the third min salary
> select min(sal) from emp where sal != (select min(sal) from emp where sal != (select min(sal) from emp)) AND sal != (select min(sal) from emp); 

> select sal from (select sal from (select distinct sal from emp order by sal) where rownum <= 3 order by sal desc) where rownum =1;

-- WAQTD all details of the employee who is getting 3rd min salary

> select * from emp where sal = (selec min(sal) from emp where sal != (select min(sal) from emp where sal != (select min(sal) from emp)) AND sal != (select min(sal) from emp) );

> select * from emp where sal = (select sal from (select sal from (select distinct sal from emp order by sal) where rownum <=3 order by sal desc) where rownum = 1);

-- WAQTD the working location of the employees of the employees who are getting thierd min(sal);

> select loc from dept where deptno in(select deptno from emp where sal =(select max(sal) from (select distinct sal from emp order by sal) where rownum <= 3));

> select loc from dept where deptno in( select deptno from emp where sal = (select sal from (select distinct sal from emp order by sal) where rownum <=3 order by sal desc where rownum = 1));






-- WAQTD all details of the employee who is getting 9th higest salary

> select * from (select  e.* rownum r from (select * from emp order by sal desc) e) where r = 9;



-- WAQTD the annual salary of the employee name of the employee who is getting 6th min salary

> select sal * 12, ename from (select e.* , rownum r from (select emp.* from emp order by sal) e) where r = 6;

-- WAQTD all details of the depart for the emp who are getting 9th min sal
> select * from dept where deptno = (select deptno from ((select e.*, rownum r from(select emp.* from emp order by sal) e) where r = 9 ));


-- WAQTD the depart name of the employees who are getting min and max sal
> SELECT dname
FROM dept
WHERE deptno IN (
    SELECT deptno
    FROM emp
    WHERE sal = (SELECT MIN(sal) FROM emp)
       OR sal = (SELECT MAX(sal) FROM emp)
);



-- WAQTD all details of the employee who's deptno is consist exact 5 letters in dname
> SELECT *
FROM emp
WHERE deptno IN (
    SELECT deptno
    FROM dept
    WHERE LENGTH(dname) = 5
);


-- WAQTD all details of the employees who are working in accounting department having more than 43 years of experience
> SELECT *
FROM emp
WHERE deptno = (
    SELECT deptno
    FROM dept
    WHERE dname = 'ACCOUNTING'
)
AND (MONTHS_BETWEEN(SYSDATE, hiredate) / 12) > 43;




-- WAQTD how many employees are working in dellas location
> SELECT COUNT(*)
FROM emp
WHERE deptno = (
    SELECT deptno
    FROM dept
    WHERE location = 'DALLAS'
);



```
------------------------------------------------------------------------------------------------------------

Date: 27-Nov-2025

# Join

* Joining more than two tables and get output any of the table data or all the table data is known as joints;

* Join is the combination of cross product and condition;

# Types of join:

* Cross Join
* Inner Join
* Equal Join
* self Join
* Right Join
* Left Join
* Full Outer Join

# Cross Join

* It is also known as condition Join
* Joining two or more than two tables based on cross product is known as cross Join for cross join condition is not madatory;
* without having parent child relation cross join will work for the tables;
* For cross Join tables names aliasing are not mandatory;

# Cross Join

Tab1  Tab2
1      A
2      B
3      C


syntax:

select tab1.cal, tab2.col....
from tab1, tab2
where condition;


Ex:

```sql

select tab1.col, tab2.col...
from tab1 cross join tab2
where condition;



-- WAQTD sname and cname to become a full stack developer  which courses they have to learn;
> select stud.sname, cour.cname from stud, cour;

-- WAQTD the stud name, age, and their course name, cours fee to become a full stack developer which courses they have to study to become Full stack developer
> select s.sname, s.age, c.cname, c.fee from stud s cross join cour c;

-- WAQTD the student name and all details of the course to become  a full stack developer mahesh have to study which courses;
> select s.sname, c.* from stud s cross join cour c where s.sname  = 'Mahesh';

-- WAQTD all details of the student  and course which student have to study java courses to become a full stack developer

> select s.*, c.* from stud s cross join cour c where c.cname = 'java';

```


# Equi join
* In case of equi join tables are joib based on common col equal details and provide output multiple tables data.

* In case of equi joib for compairing two columns mandatoryly have to use equal operator 

* For Equi join past-child relation is mandatory

* Table names aliasizing are not mandatory where condition is mandatory for equi join;


Tab1   Tab2   o/p
1        2     2
2        3     3
3        5     3
4        3


syntax:

select tab1 col, tab2 col....
from tab1, tab2
where tab1.comm col = tab2.comm col


```sql

-- WAQTD the student name and their current course names
> select s.sname, c.cname from stud s, course c where s.cid = c.cid;

-- WAQTD the employee name designation salary their department name and working location
> select c.ename, e.job, e.sal, d.dname, d.loc from emp e, dept d where e.deptno = d.deptno;

-- WAQTD  all details of the student alone with thier course name who cours name consist min two 'AA';
> select s.* from stud s, cour c where s.cid = c.cid AND c.cname like '%a%a%';

-- WAQTD the employee name, job, hiredate deptname, who are working as cleark of sales department;
> select e.ename, e.job, e.hiredate, d.dname from emp e, dept d where c.deptno = d.deptno AND d.dname = 'sales' AND e.job = 'clerk';


```


Assignement:

```sql

-- WAQTD all empid, reporting mgr, dname, loc, who are getting sal in between 1500 to 3000;
> select e.ename, e.empno, e.mgr, d.dname, d.loc from emp e, dept d where e.deptno = d.deptno AND e.sal between 1500 AND 3000;

-- WAQTD * from emp with loc who are working under mgr & dname consist 'e';
> select e.*, d.loc, from emp e, dept d where e.deptno = d.deptno AND e.mgr NOT NULL AND d.dname like '%e%';

-- WAQTD * from emp with dname who are working as salesman, manager, clerk, getting sal > 1500 AND loc not like '%A%';

> select e.*, d.dname from emp e, dept d where e.deptno = d.deptno AND e.job in ('salesman', 'manager', 'clerk') AND e.sal > 1500 AND d.loc Not like '%a%';

-- WAQTD ename, anul sal, d.* who are working as analyst and sal > 2000 & sal < 3000;
> select e.ename, e.sal * 12 'anual sal', d.* from emp e, dept d where e.deptno = d.deptno AND e.job = 'analyst' AND e.sal between 2000 AND 3000;

```

-----------------------------------------------------------------------------------------------------------
Date: 28-Nov-2025

# inner Join 

* In case of inner join two or more than two tables are join based on common column compairing by all relational operator;
* In case of inner join common columns are compair inside all clause so where clause is not mandatory
* Table names aliasing are not mandatory 
* For inner join parent child relation is mandatory


Dig:

  tab-1   tab-2
   1       2
   2       3
   3       5
   4       3

Output:

 =   !=  >   <
 2   1   3   1
 3   1   4   1
 3   1   4   1
     1   4   1
     2       1
     2       2
     2       2
     3       2
     3       3
     4       4
     4
     4
     4

Syntax:

select tabl1.col, tab2.col....
from tab1 inner join tab2
on tab1 comm col =, !=, <, >, <=, >= tab2 comm col
where condition;


select tab1 col, tab2 col....
from tab1 join tab2 
on tab1 comm col =, !=, <, >, <=, >=  tab2 comm col
where condition;


```sql

-- WAQTD all employee nameand their current department name ;
> select e.ename, d.dname, from emp e join dept d on e.deptno  = d.deptno;

-- WAQTD all employee name and the department names whihch department they left to work
> select e.ename, d.dname from emp e join dept d on e.deptno != d.deptno;

-- WAQTD the student name, age, along with course details which courses still now not studied by allin;

> select s.sname, s.age, c.* from stud s join cour c on s.cid  != c.cid where s.sname = 'elina'; 


-- WAQTD employee name, job, hiredate, deptname, of the employees when employees are getting even salary
> select e.ename, e.job, e.hiredate, d.dname from emp e inner join  dept d on e.deptno = d.deptno where e.sal%2 = 0;

-- WAQTD every employee name their year of experiance departmen name which department they left to work but having more than 44 years of experiance;

> select e.ename, (MONTHS_BETWEEN(SYSDATE, e.hiredate) / 12), d.dname from emp e inner join dept d on e.deptno != d.deptno  where (MONTHS_BETWEEN(SYSDATE, hiredate) / 12) > 43;



```

# Three table join syntax:

Synatx:

  select tab1 col, tab2 col, tab3 col, ...
 from tab1 join  tab2 on tab1 comm col = tab2 comm col
 join tab3 on tab2 comm col = tab3 comm col
 where condition;


 ```sql

-- WAQTD the course name along with corresponing student name and their exam name
> select c.cname, s.sname, e.ename, from cour c join stud  s on c.cid = s.cid join exam e on s.eid = e.eid;


-- Assignament


-- WAQTD every course name along with corrosponding student name age  their exam time who are have to write java mock

> select c.cname, s.sname, s.age, e.etime from cour c join stud s on c.cid = s.cid  join exam e on s.eid  = e.eid where e.ename = 'java mock';

-- WAQTD the employee name, job, sal, deptno, deptname, which department all salesmans are left to work 

> select e.ename, e.job, e.sal, d.deptno, d.dname from emp e join dept d on e.deptno != d.deptno where 
e.job = 'SALESMAN';

```

------------------------------------------------------------------------------------------------------------
Date: 01-Dec-2025


# Self join

* Self Join means a single one table join with itself;
* In case of self join single one table compair with that table commen col equal details and provide output
based on that;
* In case of self join table names aliaising are mandatory 
* In case of self join where clause is mandatory to compair common columns;

Syntax:

select T1 col, T2 col,...
from table t1, table t2
where t1 comm col = t2 comm col;


```sql

-- WAQTD the emp name and their reporting manager names 
> select e1.ename empname, e2.ename man_name from emp e1, emp e2 where e1.mgr = e2.empno;

-- WAQTD all reporting manager name their job alon with the employee name and employees job who are working under that reporting managers

> select e1.ename, e1.job, e2.ename, e2.job from emp e1, emp e2 where e1.empno = e2.mgr;

-- WAQTD allen and his manager all details 

> select * from emp e1. emp e2 where e1.mgr  = e1.empno AND (e1.ename = 'allen');


-- WAQTD the president name and all details of the employee who are workign under president

> select e1.ename, e2.* from emp e1, emp e2 where e1.empno = e2.mgr AND (e1.job = 'president')


-- WAQTD employee name salary their reporting manager name, reporting manager sal when employee salary are more than their reporting manager

> select e1.ename, e1.sal, e2.ename, e2.sal from emp e1 = emp e2 where e1.mgr = e2.empno AND (e1.sal > e2.sal);

```

# left join

* In case of left-join tables are join based on common col equal details and provide output
common details as well as left-side table all details

* In case of left-join table name alising are not mandatory 
* In case of left-join common col are compaired in, on clause so where condition is not  mandatory;


Left join   o/p
1    6       1
2    3       2
3    5       3 -comm num along with left table

common mathch elements along with left table ele;

Syntax:

select Tab1 col, tab2 col...
from tab1 left join tab2 
on tab1 comm col = tab2 comm col
where condition;


------------------------------------------------------------------------------------------------------------
Date: 02-Dec-2025

```sql

--WAQTD the student name and their corrosponding course names, if any student are not assigned for any course then also display the student name 

> select s.sname, c.cname from stud s left join cour c on s.cid = c.cid;

-- WAQTD the department name location corresponding employee name salary, if any department no employees are working then also display the department name

> select d.dname, d.loc, e.ename, e.sal from dept d left join emp e on d.deptno = e.deptno;

```

# Rigth join

* In case of right join tables are join based on commn column equal details and provide output common details and right side table all details;

* In case of right join common columns are compaired in side on clause, so where clause is not mandatory 
* Table name alising are not mandatory 


syntax:

select Tab1.col, Tab2.col...
from tab1 right join tab2
on tab1 comm col = tab2 comm col
where condition;


right join   o/p
1    6       3 -comm num along with right table
2    3       6
3    5       5 

common mathch elements along with right table ele;



```sql
-- WAQTD the student name their corrosponding course name, if any student not assigned for any course then also display the course name 

> select s.sname, c.cname from stud s right join cour c on s.cid = c.cid;

-- WAQTD the employee name job corrospoing department name, if any department no employees are then also display the department name;

> select e.ename, e.job, d.dname from emp e right join dept d on e.deptno = d.deptno;

```


# Full outer join 

* Tables are join based on comm col equal details and porvide output common details along with both table all details;
* Table name aliasing are not mandatory
* where condition is not mandatory;


syntax:

select tab1.col, tab2.col...
from tab1 full outer join tab2
on tab1 comm col = tab2 comm col
where condition;


FUll outer join  o/p
1    6       1 -comm num along with full table
2    3       2
3    5       3 
             6
             5
common mathch elements along with full table ele;

```sql

-- WAQTD the student name and their corrosponding course name, if any course not assigned for any student or any student still now not enrolled for any course then  both student name and course name need to display

> select s.sname, c.cname from study s full outer join  cour c on s.cid = c.cid;


```

output:
sname   cname
 rita      sql
 mahesh 
 elina    java
 mitali   java
          web



# set Operators

* set operators are introduced to work with multiple tables without having relation 

1. union [unique data asce order]
2. union all [all date any order]
3. intersect [comm data asc]
4. minus [uncommon data asec]


# Union

* Union is used to compair multiple table any specific columns and provide output unique datas of that columns in `asec` order 


syntax:

select colName form Tname
union
select colname from Tname;

Ex:

```sql
select sname from stud
union
select cname from cust;


-- o/p is elina, mahesh, mita, mitali, rita

```

# union all:

* union all is used to provide all datas of provided columns as output after compairing multiple tables specific column


syntax:

select colName from Tname
union all
select colName from Tname;


```sql

select sname from stud
union all
select cname from cust;


-- o/p is rita, mahesh, elina, mitali, mahesh, mita

```

# Intersect

* It is used to compair multiple tables specific column and provide output after compairing the columns the common datas in asec order;

syntax:

select colname from Tname
intersect 
select colname from Tname;


Ex:

``` sql
select sname from stud
intersect
select cname from cust;

-- mahesh

```

# minus

* it is used to compair multiple tables specific column and provide output uncommon data in asecinding order;

syntax:

select colName from Tname
minus
select colName from Tname;

```sql

select sname from stud
minus
select cname from cust; -- o/p is mita


select deptno from emp
minus
select deptno from dept; -- NO o/p empty rows


select deptno from dept;
minus
select deptno from emp; -- o/p is 40

```

------------------------------------------------------------------------------------------------------------

Date: 03-Dec-2025

# Normalizatoin

* Dividing a larger table into smaller tables by making relation between the tables are known as normalization;

1. Insertion anamaly
2. updating anamalye
3. deletion anamalye

are solved by the help of normalization.

* Normalization is used to reduce redundancy


sname  age  dgree   cname  fees   tname
Ram    24   B.Tech  Java   35000  Raveesh
sita   26   B.S.C  python  34000  -----
Ram    25   B.tech java    35000   Ramesh

this table is converted into two tables with parent child relation to solve normalization


     course                                             

| cid | cname | fees     | tname   |              
+-----+-------+----------+---------+
| 101 | java  | 32000.00 | raveesh |
| 102 | sql   | 15000.00 | NULL    |
| 103 | web   | 32000.00 | NULL    |


    stud

+-----+--------+------+------+------+
| sid | sname  | age  | cid  | eid  |
+-----+--------+------+------+------+
|   1 | mahesh |   22 |  102 | 1003 |
|   2 | elina  |   20 |  101 | 1001 |
|   3 | mitals |   22 |  101 | 1001 |
+-----+--------+------+------+------+


# To achive normalization we have to follow normalization form rules

1. First normalization form (1NF) rule

* In case of any table all attributes names must be unique[col names]
* the order of rows and columns does not matter



Ex: 

  stud

sid  sname cid1 cid2
10    Ram  101   102
1
21
22

2. Second normalization form (2NF) rule

* It will follow one 1NF all rules 
* It will follow no partial dependency for a table


EX:

  stud

sid  sname cid1 cid2 tname 
10    Ram  101   102
1                      ❌ -- partial dependency
21
22
                     No partial dependency


* No partially dependency means in a table all columns must be depend on primary key 
* Partially dependency means in a table any column is exist which is not depend on primary key of that table
* this is not accepted;


3. Third normalization form (3NF) rule

* It will follow one 2NF all rules 
* It will follow No transitive dependency 



EX:

  stud
           transitive 
           dependency
sid  sname ename etime tname 

                ❌    - no transitive dependency   



above table is divided into two part to avoid transitive dependency;

stud                                  exam


sid   sname   eid   age            eid   ename   etime
pk             pk


* No transitive dependency means two non-primary key column cannot depend on each other 
* Transitive means two non-primary key column depend on each other; this is not accepted;


------------------

# VIEW

* view is the virtual table
* view is the resultant set of stroed query;
* view read-only vs update;
* the advantages of view are 

1. view is providing data security, it restrict unecessery data access;
2. By using view we can write complex query simple way;


syntax:

```sql

> connt admin;
> password:

> grant create view to user;   
> Revoke create view from user

> conn user;
> password: 

> create view viewName
> as
> Query/Subquery/Joins

> drop view viewName;


```

Ex:

```sql
> conn system;
> password: ****

> grant create view to scott;

> conn scott;
> Enter password: ****

> create view empdetails
> as 
> select empno, ename from emp;

> select * from tab;
> select * from empdetails;

> create view employee
> as 
> select * from emp
> where deptno=(select deptno from dept where dname = 'SALES');

> select * from tab;


> select * from employee;

> create view v1
> as
> select s.sname, c.cname
> from stud s join cour c
> on s.cid = c.cid;


> select * from tab;


> select * from v1;

> drop view dempdetails;

> select * from tab;

> conn system;
> enter password: ****

> revoke create view from scott;

> conn scott;
> enter password: ****

> show user;

> create view v3
> as
> select ename, sal, from emp; -- error insufficiant privilages
```


# ER Diagram(entity relationship diagram)

* ER diagram stands for entity relationship diagram
* ER diagram is used to draw to establilsh the relation between one entity to another entity;


symbols to represent the entity:

Entity -->   🔲



attribiute  --> 🔘



relations --> 




# Schema diagram 

* It is used to draw to represent the relationship between attributes;







# Group by & having

* Group by is the clause which is used for grouping the data of provided column;
* Having is the clause which is used for work with multirow function related condition;
* Group by cluase is not debate on having but having clause is debate on group by;


syntax:

select col, col,...
from Tname
where condition
group by colName
having  condition
Order by colName order;


```sql
-- WAQTD the job role of employee table based on the grouping

-- WAQTD the group of job from emp table;
> select job from emp group by job;

-- WAQTD the job role and number of employees working in each job role
> select job, count(job) from emp group by job;

-- WAQTD the job role and number of employees working in each job role, in each job role minmum three employees must be working
> select job, count(job) from emp group by job having count(job) >= 3;

```

# CTE - Common Table Expression
* It is a temporary named result set that you can reference within a single SELECT, INSERT, UPDATE, or DELETE statement.
* It acts like a Virtual table that is created during query execution, used immediately, and destroyed when the query finishes.

EX:
```sql
WITH cte_name AS(
    SELECT col1, col2
    FROM table_name
    WHERE condition
)
SELECT *
FROM cte_name;
```

