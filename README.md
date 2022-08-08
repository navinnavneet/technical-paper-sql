<!-- ![Alt text](https://assets.digitalocean.com/articles/alligator/boo.svg "a title") -->

# SQL

#### ( Structured Query Language )

## Introduction

SQL, which stands for Structured Query Language, is a query based language used by computer programmers to communicate with databases ( RDMS). SQL was developed by IBM researchers Raymond Boyce and Donald Chamberlin, in 1970.

SQL provides an interface to a relational database and unifies tasks such as the following in one consistent language:

- Creating, replacing, altering, and dropping objects

- Inserting, updating, and deleting table rows

- Querying data

- Controlling access to the database and its objects

- Guaranteeing database consistency and integrity

![sql-map](https://bookdown.org/paranedagarcia/database/images/sql-mapa.jpg)

## Why SQL?

As, the people are becoming more and more dependent on internet for their day to day activities, a huge data trail is being created and to use that data for any useful purpose, SQL is the perfect tool as it is an extremely powerful query language and easy to learn.

Many proprietary and open source relational database management systems built around SQL are available for use by organizations. Some of them are:

- Microsoft SQL Server

- MySQL (now owned by Oracle)

- IBM DB2

- SAP HANA

- SAP Adaptive Server

- PostgreSQL

So, SQL is a widely used query language for database management all across the industry. And also, SQL developers are paid well.

## Professions emerging out of SQL

Alongside, software developers and computer programmers, other professionals can also benefit from SQL, such as:

- Researchers

- Data Scientists

- Business Analysts

- Database Administrators

- Accountants

- Statisticians

- Business Strategists

- Health Care Professionals

## Phases Of Query Evaluation

![PhasesofQueryEvaluation](https://media.geeksforgeeks.org/wp-content/uploads/20220211155243/PhasesofQueryEvaluation.png)

- Parser/Translator: Parser checks the syntax and verifies the query. Translator converts command written in high-level language to low-level language.

- Optimizer: Out of many relational algebra expressions for the given query, optimizer selects the one with the lowest cost.

- Execution Plan: In this phase, the database decides the order of execution of given query instructions. For example, consider the following query:

```
Select * From Patients
Where age > 50;
```

Here database will first execute From statement, then Where, and finally Select statement.

- Query Execution Engine: The query execution engine will take a query evaluation plan, executes that plan, and returns the answers to the query. It acts as a dispatcher for all commands in the execution plan. And it interacts with the storage engine to retrieve and update data from tables and indices.

## Types Of SQL Commands

There are five types of SQL commands.

![dbms-sql-command](https://static.javatpoint.com/dbms/images/dbms-sql-command.png)

### 1. Data Definition Language (DDL)

Data definition language statements define, structurally change, and drop schema objects. Such as, create, alter, delete etc. Some of the DDLstatements are:

#### 1.1 Create

This statement is used to create a table or a database.

- 1.1.1 Following code is for creating a DB with name Students.

```
CREATE DATABASE StudentsDB;
```

- 1.1.2 Following code is for creating a table inside above db with name Grades.

```
CREATE TABLE Grades (
student_id int,
student_name varchar(255),
grade int
);
```

#### 1.2 Drop

This statement is used to drop an existing table or a database.

- 1.2.1 Following code is for droping an existing db studentdsDB.

```
 DROP DATABASE studentsDB;
```

Entire data is lost after using this statement.

- 1.2.2 Following code is for droping an existing table.

```
DROP TABLE Grades;
```

#### 1.3 Alter

This command is used to delete, modify or add constraints or columns in an existing table. ALTER TABLE statement is used with ADD/DROP Column command according to the need.

```
 ALTER TABLE TableName
 ADD ColumnName Datatype;

 ALTER TABLE TableName
 DROP COLUMN ColumnName;
```

#### 1.4 Truncate

This command is used to delete the information present in the table but does not delete the table.

```
 TRUNCATE TABLE TableName;
```

### 2. Data Manipulation Language (DML)

Data manipulation language (DML) statements query or manipulate data in existing schema objects.

Whereas DDL statements change the structure of the database, DML statements query or change the contents. For example, ALTER TABLE changes the structure of a table, whereas INSERT adds one or more rows to the table.

Following are the DML Statements:

#### 2.1 Insert Into

This statement is used to insert new records into the table.

```
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

#### 2.2 Update

The UPDATE statement is used to update data in a table. For example, the code below would update the age of any customer named Bob in the customers table to 56.

```
UPDATE grades
SET grade = 85
WHERE name = 'Kiran';
```

#### 2.3 Delete

DELETE can remove all rows from a table (using ), or can be used as part of a WHERE clause to delete rows that meet a specific condition.

```
DELETE FROM grades
WHERE name = 'Kiran’;
```

### 3. Data Control Language (DCL)

The DCL commands such as grant and revoke are used for providing rights, permissions and other controls of the DB system.

Following are the DCL commands:

#### 3.1 Grant

This command is used to provide access or privileges on the database and its objects to the users.

```
GRANT PrivilegeName
ON ObjectName
TO {UserName |PUBLIC |RoleName}
[WITH GRANT OPTION];
```

#### 3.2 Revoke

This command is used to withdraw the user’s access privileges given by using the GRANT command.

```
REVOKE PrivilegeName
ON ObjectName
FROM {UserName |PUBLIC |RoleName};
```

####

### 4. Data Query Language (DQL)

DQL statements are used for performing queries on the data within schema objects. The purpose of the DQL Command is to get some schema relation based on the query passed to it.

#### 4.1 Select

SELECT is probably the most commonly-used SQL statement. You’ll use it pretty much every time you query data with SQL. It allows you to define what data you want your query to return.

```
SELECT name
FROM customers;

SELECT * FROM customers;
```

### 5. Transaction Control Language (TCL)

TCL commands such as commit, rollback and savepoint is used are used to manage transactions in the database. The commands are as follows:

#### 5.1 Commit

This command is used to save the transaction into the database.

```
COMMIT;
```

#### 5.2 Rollback

This command is used to restore the database to the last committed state.

```
ROLLBACK;
```

#### 5.3 Savepoint

This command is used to temporarily save a transaction. So if you wish to rollback to any point, then you can save that point as a ‘SAVEPOINT’.

```
SAVEPOINT SAVEPOINTNAME;
```

## SQL Joins

A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

### 1. INNER JOIN

INNER JOIN selects records that have matching values in both tables.

```
SELECT name
FROM customers
INNER JOIN orders
ON customers.customer_id = orders.customer_id;
```

### 2. LEFT JOIN

LEFT JOIN selects records from the left table that match records in the right table. In the below example the left table is customers.

```
SELECT name
FROM customers
LEFT JOIN orders
ON customers.customer_id = orders.customer_id;
```

### 3. RIGHT JOIN

RIGHT JOIN selects records from the right table that match records in the left table. In the below example the right table is orders.

```
SELECT name
FROM customers
RIGHT JOIN orders
ON customers.customer_id = orders.customer_id;
```

### 4. FULL JOIN

FULL JOIN selects records that have a match in the left or right table. Think of it as the “OR” JOIN compared with the “AND” JOIN (INNER JOIN).

```
SELECT name
FROM customers
FULL OUTER JOIN orders
ON customers.customer_id = orders.customer_id;
```

### 5. SQL SELF JOIN

A self join is a regular join, but the table is joined with itself.

```
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```

## SQL Aggregation

SQL aggregation is the task of collecting a set of values to return a single value. It is done with the help of aggregate functions, such as SUM, COUNT, and AVG. For example, in a database of products, you might want to calculate the average price of the whole inventory.

Aggregation in SQL is, typically, used in conjunction with grouping. The Group By clause is used to arrange rows into groups in SQL. Aggregation, together with grouping, is key to generating quick reports and insights from a database. For example, an ecommerce company might want to see its highest spending customers over a given time period.

### Aggregate Functions

An aggregate function in SQL performs a calculation on multiple values and returns a single value.

Following are the Aggregate functions:

#### 1. Min Function

The MIN function returns the smallest value of the selected column in a table.

```
SELECT MIN(ColumnName)
FROM TableName
WHERE Condition;
```

#### 2. Max Function

The MAX function returns the largest value of the selected column in a table.

```
SELECT MAX(ColumnName)
FROM TableName
WHERE Condition;
```

#### 3. Count Function

The COUNT function returns the number of rows which match the specified criteria.

```
SELECT COUNT(ColumnName)
FROM TableName
WHERE Condition;
```

#### 4. Sum Function

The SUM function returns the total sum of a numeric column that you choose.

```
SELECT SUM(ColumnName)
FROM TableName
WHERE Condition;
```

### 5. Avg Function

The AVG function returns the average value of a numeric column that you choose.

```
SELECT AVG(ColumnName)
FROM TableName
WHERE Condition;
```

### Reference and Resources

- https://docs.oracle.com/en/database/oracle/oracle-database/21/cncpt/sql.html#GUID-DA48618A-A6BB-421A-A10A-02859D8ED9AD

- https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/?ref=lbp

- https://bookdown.org/paranedagarcia/database/sql.html

- https://www.geeksforgeeks.org/query-execution-engine-in-sql

- https://www.javatpoint.com/dbms-sql-command
