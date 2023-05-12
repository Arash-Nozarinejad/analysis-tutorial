# SQL Basic and Intermediate Level Tutorial

In this tutorial we will learn all the basic and intermediate level topics needed to be learn to get you started with SQL.

- [SQL Basic and Intermediate Level Tutorial](#sql-basic-and-intermediate-level-tutorial)
  - [SQL Basic](#sql-basic)
    - [Introduction to databases and SQL](#introduction-to-databases-and-sql)
    - [SQL Syntax and Structure](#sql-syntax-and-structure)
    - [SQL Data Types](#sql-data-types)
    - [SQL Queries](#sql-queries)
      - [SELECT Statement](#select-statement)
      - [SELECT FROM](#select-from)
      - [WHERE Clause](#where-clause)
        - [AND, OR, and NOT Operators](#and-or-and-not-operators)
      - [ORDER BY clause](#order-by-clause)
      - [LIMIT Clause](#limit-clause)
      - [INSERT INTO Statement](#insert-into-statement)
      - [UPDATE Statement](#update-statement)
      - [DELETE Statement](#delete-statement)
    - [SQL Functions](#sql-functions)
      - [Agggregate Functions](#agggregate-functions)
      - [String Functions](#string-functions)
      - [Date and time Functions](#date-and-time-functions)
  - [SQL Intermediate](#sql-intermediate)
    - [Advanced SQL Queries](#advanced-sql-queries)
      - [DISTINCT Keyword](#distinct-keyword)
    - [ALIAS Syntax](#alias-syntax)
    - [JOIN Operatios](#join-operatios)
      - [INNER JOIN](#inner-join)
      - [LEFT JOIN](#left-join)
      - [RIGHT JOIN](#right-join)
      - [FULL JOIN](#full-join)
    - [GROUP BY Clause](#group-by-clause)
      - [GROUP BY Deep Dive](#group-by-deep-dive)
    - [Having Clause](#having-clause)
    - [UNION and UNION ALL Operators](#union-and-union-all-operators)
    - [Subqueries and nested queries](#subqueries-and-nested-queries)
    - [Database Design](#database-design)
      - [Normalization](#normalization)
      - [Primary Keys](#primary-keys)
      - [Foreign Keys](#foreign-keys)
      - [Indexing](#indexing)
      - [Referential Integrity](#referential-integrity)
    - [SQL Schema](#sql-schema)
      - [CREATE DATABASE Statement](#create-database-statement)
      - [CREATE TABLE statement](#create-table-statement)
      - [Column Constraints](#column-constraints)
      - [Table Constraints](#table-constraints)
      - [ALTER TABLE Statement](#alter-table-statement)
      - [DROP TABLE Statement](#drop-table-statement)
      - [TRUNCATE TABLE Satement](#truncate-table-satement)
  - [End](#end)
  - [Farewell](#farewell)

## SQL Basic

### Introduction to databases and SQL

SQL (Structured Query Language) is a programming language designed for managing and manipulating relational databases. It provides standardized way to interact with databases allowing users to create, retrieve, update, and delete data.

### SQL Syntax and Structure

SQL follows a specific syntax and structure for executing queries. A typical SQL query consists of one or more clausers, such as SELECT, FROM, WHERE, ORDER BY, and more. Here's an example of a simple SQL Query.

``` sql
SELECT column1, column2
FROM table_name
WHERE condition
ORDER BY column1;
```

### SQL Data Types

SQL supports various data types to represent different kinds of data. Common data types include integers, decimals, strings, dates, and booleans. Each database system may have its specific set of data types. Here are a few examples:

- Integer: INT, INTEGER, SMALINT, BIGINT
- Decimal: DECIMAL, NUMERIC, FLOAT, DOUBLE
- String: VARCHAR, CHAR, TEXT
- Date and time: DATE, TIME, DATETIME, TIMESTAMP
- Boolean: BOOLEAN, BIT

### SQL Queries

#### SELECT Statement

The __SELECT__ statement is used to retrieve data from one or more database tables. It allows you to specify the columns you want to retrieve and filter the rows based on certain conditions. Here's an example:

``` sql
SELECT column1, column2
FROM table_name;
```

#### SELECT FROM

The __FROM__ clause is used to specify the table(s) from which you want to retrieve data. It identifies the source of the data you want to query. Here's an example:

``` sql
SELECT column1, column2
FROM table1, table2
```

#### WHERE Clause

The __WHERE__ clause is used to filter rows based on specified conditions. It allows you to retrieve only the rows that certain criteria. Here's an example:

``` sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

##### AND, OR, and NOT Operators

The __AND__, __OR__, and __NOT__ operators are used to combine multiple conditions in the WHERE clause:

- __AND__: Returns rows that satisfy both the preceding and succeeding conditions
- __OR__: Returns rows that satisfy either the preceding or succeeding conditions
- __NOT__: Returns rows that don't satisfy the specified conditions

``` sql
SELECT column1, column2
FROM table_name
WHERE condition1 AND condition2;

SELECT column1, column2
FROM table_name
WHERE condition1 OR condition2;

SELECT column1, column2
FROM table_name
WHERE NOT condition;
```

#### ORDER BY clause

The __ORDER BY__ clause is used to sort the result set based on one or more columns. It can sort the data in ascending (default) or descending order. Here's an example:

``` sql
SELECT column1, column2
FROM table_name
ORDER BY column1 ASC;
```

#### LIMIT Clause

The __LIMIT__ clause is used to limit the number of rows returned in the result

``` sql
SELECT column1, column2
FROM table_name
LIMIT 10;
```

#### INSERT INTO Statement

The __INSERT INTO__ statement is used to insert new rows into a table. It allows you to specify the values for each column or insert data from another table. Here's an example:

``` sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2)
```

#### UPDATE Statement

The __UPADTE__ statement is used to modify existing data in a table. It allows you to update values in one or more columns based on specified conditions. Here's an example:

``` sql
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition
```

#### DELETE Statement

The __DELETE__ statement is used to delete existing rows from a table. It allows you to remove one or more rows based on specified conditions. Here's an example:

``` sql
DELETE FROM table_name
WHERE condition;
```

### SQL Functions

#### Agggregate Functions

__Aggregate functions__ perform calculations on a set of values and return a single result common aggregate functions include __COUNT__, __SUM__, __MIN__, __MAX__, and __AVG__.

``` sql
SELECT COUNT(column1) FROM table_name;
SELECT SUM(column1) FROM table_name;
SELECT MIN(column1) FROM table_name;
SELECT MAX(column1) FROM table_name;
SELECT AVG(column1) FROM table_name;
```

#### String Functions

__String functions__ manipulate string values and perform operations like converting case, extracting substrings, concatenating strings, etc. Some common string functions include __UPPER__, __LOWER__, __CONCAT__, __SUBSTRING__, and __REPLACE__.

``` sql
SELECT UPPER(column1) FROM table_name;
SELECT LOWER(column1) FROM table_name;
SELECT LENGTH(column1) FROM table_name
SELECT CONCAT(column1, '' column2) FROM table_name;
SELECT SUBSTRING(column1, 1, 5) FROM table_name;
SELECT REPLACE(column1, 'old', 'new') FROM table_name;
```

#### Date and time Functions

__Date and time functions__ perform operatios on date and time values. They allow you to extract specific parts of date or time, perform calculations, and format the val;ues. Examples of date and time functions include __NOW__, __DATE__, __TIME__, __DAY__, __MONTH__, __YEAR__ etc.

``` sql
SELECT NOW() FROM table_name;
SELECT DATE(column1) FROM table_name;
SELECT TIME(column1) FROM table_name;
SELECT DAY(column1) FROM table_name
SELECT MONTH(column1) FROM table_name;
SELECT YEAR(column1) FROM table_name;
```

## SQL Intermediate

### Advanced SQL Queries

#### DISTINCT Keyword

The __DISTINCT__ keyword is used to retrieve unique values from a column in the result set. It eliminates duplicate values. Here's an example:

``` sql
SELECT DISTINCT column1 FROM table_name;
```

### ALIAS Syntax

The __AS__ keyword is used to assign an alias (temporary name) to a table or column. Aliases are helpful for providing more meaningful or concise names in the result set or for joining tables. Here's an example:

``` sql
SELECT column1 AS alias1, column2 AS alias2
FROM table_name;
```

### JOIN Operatios

__JOIN__ operatios are used to combine rows from multiple tables based on a related column between them. They allow you retrieve data from multiple tables in a single query.

#### INNER JOIN

The __INNER JOIN__ returns only the matching rows between two tables based on a specified condition.

``` sql
SELECT column1, column2
FROM table1
INNER JOIN table2 ON table1.column = table2.column
```

#### LEFT JOIN

The __LEFT JOIN__ returns all rows from the _left_ table and the matching rows from the _right_ table.

``` sql
SELECT column1, column2
FROM table
LEFT JOIN table2 ON table1.column = table2.column
```

#### RIGHT JOIN

The __RIGHT JOIN__ returns all rows from the right table and the matching rows from the left table based on a specified condition. If there are no matching rows in the left table, NULL values are returned.

``` sql
SELECT column1, column2
FROM table1
RIGHT JOIN table2 ON table1.column = table2.column
```

#### FULL JOIN

The __FULL JOIN__ returns all rows from both the left and right tables. It combines the result of the _LEFT JOIN_ and _RIGHT JOIN_. If there are no matching rows, NULL values are returned.

``` sql
SELECT column1, column2
FROM table1
FULL JOIN table2 ON table1.column = table2.column
```

### GROUP BY Clause

The __GROUP BY__ clause is used to group rows based on one or more column. It is often used in combination with aggregate function to perform calculations on groups of data.

``` sql
SELECT column1, COUNT(column2)
FROM table_name
GROUP BY column1;
```

#### GROUP BY Deep Dive

Here's a deeper dive into the __GROUP BY__ Clause:

Assume we have a table called __orders__ with the following structure and data:

``` sql
Table: orders
+---------+----------+
| column1 | column2  |
+---------+----------+
|   A     |    10    |
|   A     |    20    |
|   B     |    30    |
|   B     |    40    |
|   B     |    50    |
|   C     |    60    |
+---------+----------+
```

Now let's execute the SQL code above.

``` sql
SELECT column1, COUNT(column2)
FROM orders
GROUP BY column1;
```

Explanation:

- The SELECT statement is used to specify the columns we want to retrieve from the orders table.
- In this case, we select column1 and the result of the COUNT(column2) expression.
- The COUNT(column2) expression counts the number of rows for each distinct value in column1.
- The FROM clause specifies the table we want to query, which is orders in this example.
The GROUP BY clause groups the rows based on the values in column1.
- As a result, we will get the distinct values in column1 and the count of occurrences of each value.

Result:

```sql
+---------+-----------------+
| column1 | COUNT(column2)  |
+---------+-----------------+
|   A     |        2        |
|   B     |        3        |
|   C     |        1        |
+---------+-----------------+

```

The result shows the distinct values in column1 (A, B, and C) and the count of occurrences for each value. In this example, the value 'A' appears twice, 'B' appears three times, and 'C' appears once.

Note: The column names and table name used in the example are arbitrary and may vary depending on your actual table structure and data.

### Having Clause

The __HAVING__ clause is used to filter the result set based on conditions applied to groups created by the __GROUP BY__ clause. It is similar to there __WHERE__ clause but operates on groups rather than individual rows.

``` sql
SELECT column1, COUNT(column2)
FROM table_name
GROUP BY column1
HAVING COUNT(column2) > 10;
```

### UNION and UNION ALL Operators

The __UNION__ operator is used to combine the result sets of two or more SELECT statements into a single result set. It eliminates duplicate rows. The __UNION ALL__ operator, on the other hand, includes all rows, including duplicates.

``` sql
SELECT column1 FROM table1
UNION
SELECT column1 FROM table2;

SELECT column1 FROM table1
UNION ALL
SELECT column1 FROM table2;
```

### Subqueries and nested queries

__Subqueries__, also known as nested queries, are queries placed inside another query. They allow you to retrieve data based on the result of an inner query. Subqueries can be used in various clauses, such as _SELECT_, _FROM_. _WHERE_, and more.

``` sql
SELECT column1
FROM table1
WHERE column2 IN (SELECT column2 FROM table2)
```

### Database Design

#### Normalization

__Normalization__ is the process of organizing data in a database to minimize redundancy and dependency issues. It involves dividing a database into multiple tables and establishing relationships between them.

#### Primary Keys

A __Primary Key__ is a unique identifier for each record in a table. It ensures that each row can be uniquely identified and helps establish relationships with other tables.

#### Foreign Keys

A __Foreign Key__ is a column in a table that establishes a link between two tables. It refers to the primary key in another table, creating relationship between them.

#### Indexing

__Indexing__ is a technique used to improve the performance of queries on large databases. It involves creating an index structure that allows for faster retrieval of data based on specific columns.

#### Referential Integrity

__Referential Integrity__ ensures that relationships between tables are maintained. It enforces the consistency and validity of data by defining rules for actions such as updates and deletetion in related tables

### SQL Schema

#### CREATE DATABASE Statement

The __CREATE DATABASE__ statement is used to create on a new database in the SQL system. It specifies the name of the database and any additional properties or options.

``` sql
CREATE DATABASE database_name;
```

#### CREATE TABLE statement

The __CREATE TABLE__ statement is used to create a new table in a database. It defines the structure of the table by specifying the column names, data types, constraints, and other properties.

``` sql
CREATE TABLE table_name (
  column1 data_type constraint,
  column data_type constraint,
  ...
)
```

#### Column Constraints

Column constraints define reules or conditions for individual columns. Common column constraints include __NOT NULL__ ( the column must have a value), __UNIQUE__ ( the column values must be unique), __DEFAULT__ (assign a default value if no value is specified), and __CHECK__ (specify a condition that values must meet).

``` sql
CREATE TABLE table_name (
  column1 data_type NOT NULL,
  column2 data_type UNIQUE,
  column3 data_type DEFAULT Value,
  column4 data_type CHECK (condition),
  ...
)
```

#### Table Constraints

Table constraints define rules or conditions that apply to the entire table. Common table constrains include __PRIMARY KEY__ (a unique identifier for the table), __FOREIGN KEY__ (establishing relationships with other tables), and __UNIQUE__ (ensuring unique values across multiple columns).

``` sql
CREATE TABLE table_name (
  column1 data_type,
  column2 data_type,
  ...
  CONSTRAINT constraint_name PRIMARY KEY (column1),
  CONSTRAINT constraint_name FOREIGN KEY (column2) REFERENCES other_table(column),
  CONSTRAINT constraint_name UNIQUE (column1, column2),
  ...
)
```

#### ALTER TABLE Statement

The __ALTER TABLE__ statement is used to modify the structure of an existing table. It allows you to _ADD__, or __MODIFY__ or __DROP__ columns, __CONSTRAINTS__, or other table properties.

``` sql
ALTER TABLE table_name
ADD column data_type;

ALTER TABLE table_name
MODIFY column new_data_type;

ALTER TABLE table_name
DROP COLUMN column_name;
```

#### DROP TABLE Statement

The __DROP TABLE__ Satement is used to delete an existing table from the database, along with all its data and associated objects.

``` sql
DROP TABLE table_name;
```

#### TRUNCATE TABLE Satement

The TRUNCATE TABLE__ satement is used to remove al lrows from an existing table, while keeping the table structure intact.

``` sql
TRUNCATE TABLE table_name;
```

## End

These were all SQL basic and intermediate level concepts. Learnign these simple topics will get you started working with SQL and will prepare you to learn advanced and master level concepts. Which I will cover in another tutorial

## Farewell

Thank you for reading this Github article on Advanced Python Concepts. Creating this tutorial project was very fun and I hope you enjoyed reading it as much as I enjoyed creating it.

You can visit our website for more tutorials, guides, case studies, and more by [clicking here](https://www.analysistutorial.com/).

Farewell.
