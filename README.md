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

![Alt text](https://bookdown.org/paranedagarcia/database/images/sql-mapa.jpg "a title")

## Why SQL?

As, the people are becoming more and more dependent on internet for their day to day activity, a huge data trail is being created and to use that for any useful purpose, SQL is the perfect tool as it is extremely powerful query language and easy to learn.

Many proprietary and open source relational database management systems built around SQL are available for use by organizations. Some of them are:

- Microsoft SQL Server

- MySQL (now owned by Oracle)

- IBM DB2

- SAP HANA

- SAP Adaptive Server

- PostgreSQL

So, SQL is a widely used for database management all across the industry and SQL developers are paid well.

## Applications Of SQL

Alongside software development and computer programming other professions can also be benefited from SQL, such as:

- Research

- Data Science

- Business Analytics

- Database Administration

- Accontants

- Researchers

- Statisticians

- Business Strategists

- Health Care Professionals

## Phases Of Query Evaluation

![Alt text](https://media.geeksforgeeks.org/wp-content/uploads/20220211155243/PhasesofQueryEvaluation.png "a title")

- Parser/Translator: Parser checks the syntax and verifies the query. Translator converts command written in high-level language to low-level language.

- Optimizer: We have many relational algebra expressions for the given query. Optimizer selects the query which is having a low cost.

- Execution Plan: In this phase, the database decides the order of execution of given query instructions. For example, consider the following query:

```
Select * From emp_table
Where experience>5;

```

Here database will first execute From statement then Where and finally Select statement.

- Query Execution Engine: The query execution engine will take a query evaluation plan then executes that plan and return the answers to the query. It acts as a dispatcher for all commands in the execution plan. And it interacts with the storage engine to retrieve and update data from tables and indexes.

### Reference and Resources

- https://bookdown.org/paranedagarcia/database/sql.html

  (for image used in introduction)

- https://www.geeksforgeeks.org/query-execution-engine-in-sql
  (phases of query evaluation)
