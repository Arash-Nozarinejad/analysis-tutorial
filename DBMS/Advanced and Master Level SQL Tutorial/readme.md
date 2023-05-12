# SQL Advanced and Master Level tutorial

In this tutorial we will learn everything you need to know to master SQL.

- [SQL Advanced and Master Level tutorial](#sql-advanced-and-master-level-tutorial)
  - [Advanced](#advanced)
    - [VIEW](#view)
      - [CREATE VIEW Statement](#create-view-statement)
        - [VIEW Deep Dive](#view-deep-dive)
      - [UPDATE and DELETE with views](#update-and-delete-with-views)
    - [Stored Procedure](#stored-procedure)
      - [CREATE PROCEDURE Statement](#create-procedure-statement)
      - [Variables and parameters](#variables-and-parameters)
      - [Stored Procecdure Deep Dive](#stored-procecdure-deep-dive)
      - [Conditional Satements and Loops](#conditional-satements-and-loops)
      - [Cursors](#cursors)
    - [Transaction and Concurrency Control](#transaction-and-concurrency-control)
      - [ACID Properties](#acid-properties)
      - [Transaction Control Statements](#transaction-control-statements)
      - [Error Handling and Rollbacks](#error-handling-and-rollbacks)
      - [Transaction Isolation Levels](#transaction-isolation-levels)
    - [Locks and deadlocks](#locks-and-deadlocks)
      - [SQL Locks](#sql-locks)
      - [Preventing Deadlocks](#preventing-deadlocks)
      - [Deadlock Detection and Resolution](#deadlock-detection-and-resolution)
      - [Locking Levels and Granularity:](#locking-levels-and-granularity)
    - [Triggers and Events](#triggers-and-events)
      - [Triggers](#triggers)
        - [CREATE TRIGGER Statement](#create-trigger-statement)
          - [Trigger Types (BEFORE, AFTER, INSERT, UPDATE, DELETE)](#trigger-types-before-after-insert-update-delete)
      - [Events](#events)
        - [CREATE EVENT Statement](#create-event-statement)
        - [Managing Triggers](#managing-triggers)
        - [Event scheduling](#event-scheduling)
        - [Event management](#event-management)
    - [User Management and Security](#user-management-and-security)
      - [User accounts and privileges](#user-accounts-and-privileges)
      - [CREATE USER Statement](#create-user-statement)
      - [ALTER USER Statement](#alter-user-statement)
      - [DROP USER Statement](#drop-user-statement)
      - [Granting and revoking privileges](#granting-and-revoking-privileges)
      - [Types of Privileges](#types-of-privileges)
      - [Grant Statements](#grant-statements)
      - [Revoke Statements](#revoke-statements)
      - [View Privileges](#view-privileges)
      - [GRANT OPTION](#grant-option)
  - [Mastery](#mastery)
    - [SQL Optimization and Performance Tuning](#sql-optimization-and-performance-tuning)
      - [Query Optimization techniques](#query-optimization-techniques)
      - [Index Optimization](#index-optimization)
      - [Execution Plan Analysis](#execution-plan-analysis)
      - [Database Configuration and Tuning](#database-configuration-and-tuning)
    - [Advanced SQL Functions and Features](#advanced-sql-functions-and-features)
      - [Window Functions](#window-functions)
        - [Syntax of Window Functions](#syntax-of-window-functions)
        - [Common Window Functions](#common-window-functions)
        - [Example Usage of Window Functions](#example-usage-of-window-functions)
          - [Example 1: Calculating the cumulative sum of total\_amount for each customer within their orders](#example-1-calculating-the-cumulative-sum-of-total_amount-for-each-customer-within-their-orders)
          - [Example 2: Assigning a rank to each customer based on their total\_amount within their orders](#example-2-assigning-a-rank-to-each-customer-based-on-their-total_amount-within-their-orders)
          - [Example 3: Calculating the difference in total\_amount between the current order and the previous order for each customer](#example-3-calculating-the-difference-in-total_amount-between-the-current-order-and-the-previous-order-for-each-customer)
        - [Window Functions with Frame Specification](#window-functions-with-frame-specification)
      - [Common Table Expressions (CTEs) and Recusive CTEs](#common-table-expressions-ctes-and-recusive-ctes)
        - [Common Table Expressions (CTEs)](#common-table-expressions-ctes)
        - [Recursive CTEs](#recursive-ctes)
        - [Benefits of CTEs and Recursive CTEs](#benefits-of-ctes-and-recursive-ctes)
        - [Limitations and considerations](#limitations-and-considerations)
      - [Pivoting and Unpivoting Data](#pivoting-and-unpivoting-data)
      - [SQL/XML and SQL/JSON](#sqlxml-and-sqljson)
    - [SQL and NoSQL Databases](#sql-and-nosql-databases)
      - [SQL Support in NoSQL databases](#sql-support-in-nosql-databases)
      - [Comparing SQL and NoSQL Databases for Different Use Cases](#comparing-sql-and-nosql-databases-for-different-use-cases)
    - [SQL and Data Warehousing](#sql-and-data-warehousing)
      - [Data Warehouse Concepts](#data-warehouse-concepts)
      - [ETL Processes](#etl-processes)
      - [Start and Snoflake Schemas](#start-and-snoflake-schemas)
      - [OLAP anad Analytical Queries](#olap-anad-analytical-queries)
    - [SQL and Big Data](#sql-and-big-data)
      - [Big data Concepts and platforms (Hadoop, Spark)](#big-data-concepts-and-platforms-hadoop-spark)
      - [SQL On Big Data (Hive, Impala, Presto, etc)](#sql-on-big-data-hive-impala-presto-etc)
      - [Analyzing Big Data with SQL](#analyzing-big-data-with-sql)
  - [END](#end)
  - [Farewell](#farewell)

## Advanced

### VIEW

#### CREATE VIEW Statement

The __CREATE VIEW__ statement is used to create a virtual table based on the results of a _SELECT_ statement. Views allows you to simplify complex queries and provide an abstraction layer for data retrieval.

``` sql
CREATE VIEW view_name AS
SELECT column1, column
FROM table_name
WHERE condition;
```

##### VIEW Deep Dive

To better understand VIEWs, here's a more detailed example:

``` sql
CREATE VIEW customer_view AS
SELECT customer_id, customer_name, email
FROM customers
WHERE status = 'active';
```

- The CREATE VIEW statement is used to create a view named customer_view.
- The view is defined as a select statement that retrieves specific columns (customer_id, customer_name, and email) from the customers table.
- The FROM clause specifies the table we want to query, which is customers in this example.
- The WHERE clause filters the rows based on the specified condition (status = 'active').
- As a result, the view will contain the selected columns from the customers table that meet the given condition.

Now, let's query the view and see the results:

``` sql
SELECT * FROM customer_view;
```

Assuming we have the following data in the _customers_ tables:

``` sql
Table: customers
+-------------+---------------+----------------------+
| customer_id | customer_name |        email         |
+-------------+---------------+----------------------+
|      1      |   John Doe    | johndoe@example.com  |
|      2      |   Jane Smith  | janesmith@example.com|
|      3      |   Adam Brown  | adambrown@example.com|
+-------------+---------------+----------------------+
```

Result:

``` sql
+-------------+---------------+----------------------+
| customer_id | customer_name |        email         |
+-------------+---------------+----------------------+
|      1      |   John Doe    | johndoe@example.com  |
|      2      |   Jane Smith  | janesmith@example.com|
|      3      |   Adam Brown  | adambrown@example.com|
+-------------+---------------+----------------------+

```

The result shows the selected columns (customer_id, customer_name, and email) from the customers table, filtered by the condition status = 'active'. In this example, all rows that have a status of 'active' are included in the view.

#### UPDATE and DELETE with views

Views can also be used for performing __UPDATE__ and __DELETE__ operations on underlying tables. however, there are cerain limitation and consideration to keep in mind.

``` sql
UPDATE view_name
SET column1 = Value
WHERE condition;

DELETE FROM view_name
WHERE condition;
```

### Stored Procedure

__Stored Procedures__ are a collection of SQL statements that are stored in the database and can be executed as a single unit. They provide reusability, security and performance benefits.

#### CREATE PROCEDURE Statement

The __CREATE PROCEDURE__ satement is used to create a stored procedure in the database. It defines the procedure name, aprameters, and the SQL statemetns to be executed.

``` sql
CREATE PROCEDURE procedure_name (parameter1 datatype, parameter2 datatype)
BEGIN
    -- SQL statements
END;
```

#### Variables and parameters

__Stored Procedures__ can use variables to store and manipulate data during their execution. Parameters allow you to pass values into stored procedures when they are called.

``` sql
CREATE PROCEDURE procedure_name (IN parameter1 datatype, OUT parameter2 datatype)
BEGIN
  DECLARE variable datatype;
  SET variable = value;
  -- SQL statements
END;

```

#### Stored Procecdure Deep Dive

Here's a more detailed explanation of __stored Procedures__:

``` sql
CREATE PROCEDURE calculate_sum(IN num1 INT, IN num2 INT, OUT result INT)
BEGIN
    DECLARE sum INT;
    SET sum = num1 + num2;
    SET result = sum;
END;
```

- The CREATE PROCEDURE statement is used to create a stored procedure named calculate_sum.
- Inside the parentheses, we define the input parameters num1 and num2 with their respective data types, and the output parameter result with its data type.
- The BEGIN and END keywords enclose the body of the stored procedure.
- Within the procedure, we declare a local variable named sum with the same data type as the parameters.
- The SET statement assigns the sum of num1 and num2 to the sum variable.
- Finally, we assign the value of sum to the result output parameter.

Now, let's execute the procedure and see the results:

``` sql
-- Declare variables to hold the input and output values
DECLARE @input1 INT;
DECLARE @input2 INT;
DECLARE @output INT;

-- Set the input values
SET @input1 = 5;
SET @input2 = 3;

-- Execute the stored procedure
EXECUTE calculate_sum @input1, @input2, @output OUTPUT;

-- Display the result
SELECT @output AS result;
```

Result:

``` sql
+--------+
| result |
+--------+
|   8    |
+--------+
```

The result shows the output value of the stored procedure calculate_sum, which is the sum of the input parameters num1 and num2. In this example, when we pass 5 as num1 and 3 as num2, the procedure calculates the sum as 8, which is returned as the result.

Note: The data types used in the example are arbitrary, and you can replace them with the appropriate data types based on your requirements.

#### Conditional Satements and Loops

__Conditional Statements__ such as __IF-ELSE__ and __CASE__ can be used within stored procedures to control the flow of execution based on certain conditions. Loops like __WHILE__ and __FOR__ can be used for iterative processing.

``` sql
IF condition THEN
    -- sql statements
ELSE
    -- sql statements
END IF;

CASE
    WHEN condition1 THEN
        -- sql statements
    WHEN condition2 THEN
        -- sql statements
    ELSE
        -- sql statements
END CASE;

WHILE condition DO
    -- sql statements
END WHILE

FOR variable IN range DO
    -- sql statements
END FOR;
```

#### Cursors

__Cursors__ are used to retrieve and process rows from a result set within a stored procedure. They provide a way to iterate over query results and perform actions on each row.

``` sql
DECLARE cursor_name CURSOR FOR SELECT column1, column2 FROM table_name;

OPEN cursor_name;

FETCH NEXT FROM cursor_name INTO variable1, variable2;

WHILE @FETCH_STATUS = 0 DO
    -- SQL statements
    FETCH NEXT FROM cursor_name INTO variable1, variable2;
END WHILE;

CLOSE cursor_name;
```

### Transaction and Concurrency Control

Transaction management is a cruicial aspect of working with databases. In SQL, a transaction is a sequence of one or more database operations that must be executed as a single unit.

#### ACID Properties

__ACID__ (__Atomicity__, __consistency__, __Isolation__, __Durability__) properties are they key principles that ensure reliability and consistency in database transactions.

- Atomicity: A transaction is atomic, meaning it is treated as a single, indivisible unit of work. Either all the changes made in the transaction are committed, or none of them are.
- Consistency: A transaction brings the database from one consistent state to another. It ensures that all data modifications follow defined rules and constraints.
- Isolation: Transactions operate independently of each other, even if they are executed concurrently. Each transaction should be isolated from the effects of other transactions until it is committed.
- Durability: Once a transaction is committed, its changes are permanent and survive system failures. The changes are stored in non-volatile memory, such as disk storage.

#### Transaction Control Statements

SQL provides statements to control transactions.

- __BEGIN TRANSACTION__ (or __BEGIN WORK__): Starts a new transaction.
- __COMMIT__: Saves the changes made in the transaction to the database and ends the transaction.
- __ROLLBACK__: Undoes the changes made in teh transaction and ends the transaction.
- __SAVEPOINT__: Sets a savepoint within a transaction, allowing you to roll back to a specific point without cancelling the entire transaction.

Example:

```sql
BEGIN TRANSACTION;

UPDATE accounts SET balance = balance + 100 WHERE account_id = 1;
UPDATE accounts SET balance = balance - 100 WHERE account_id = 2;

COMMIT;
```

#### Error Handling and Rollbacks

Error handling is essential in transaction management to ensure data integrity. If an error occurs during a transaction, you can roll back the changes made so far to maintain a consistent state.

``` sql
BEGIN TRANSACTION;

BEGIN TRY
    -- Perform database operations here

    COMMIT;
END TRY

BEGIN CATCH
    ROLLBACK;
    `` Handle the error here
END CATCH;
```

the TRY-CATCH block allows you to catch any error that occurs during the transaction. If an error is caught, the changes are rolled back, and you can handle the error appropriately.

#### Transaction Isolation Levels

SQL databases provide different isolation levels to control how transactions interact with each other:

- __READ UNCOMMITED__: Allows dirty reads, meaning a transaction can see uncommited changes made by other transactions.
- __READ COMMITED__: Prevents dirty reads but allows non-repeatable reads, where a transaction may see different values for the same row during the course of transaction.
- __REAPEATABLE READ__: Prevents dirty reads and non-repeatable reads but allows phantom reads, where new rows are added or removed by other transactions.
- __SERIALIZABLE__: Provides the highest level of isolation, preventing dirty reads, non-repeatable reads, and phantom reads.

The isolation level can be set at the session level for individual transactions, depending on the database system.

### Locks and deadlocks

__LOCKS__ are mechanisms used to manage concurrent access to database resources. They ensure that multiple transactions don't interfere with each other. __DAEDlocks__ occur when two or more transactions are waiting for each other to release resources, resulting in a deadlock situation.

#### SQL Locks

- Shared Lock (Read Lock): Allows multiple transactions to read a resource simultaneously but prevents write operations on the same resource until the lock is released.
- Exclusive Lock (Write Lock): Prevents other transactions from reading or writing to a resource until the lock is released.
- Intent Lock: Indicates the intention of a transaction to acquire shared or exclusive locks on a resource.

#### Preventing Deadlocks

Preventing deadlocks involves adopting strategies to minimize the chances of circular dependencies between transactions. Here are some common prevention techniques:

- Acquire locks in a consistent order: Ensure that transactions always request locks on resources in the same order to avoid circular dependencies.
- Keep transactions short and focused: Minimize the time spent holding locks to reduce the chances of conflicts with other transactions.
- Use lock timeouts: Set a timeout for lock requests to prevent transactions from waiting indefinitely, aborting them if necessary.

#### Deadlock Detection and Resolution

If deadlocks cannot be entirely prevented, detection and resolution mechanisms become crucial. Most databases employ a deadlock detection algorithm that periodically scans for deadlocks and takes action to resolve them. Resolution strategies include:

- Deadlock detection algorithms: Databases use various algorithms, such as wait-for graph, to detect circular dependencies and identify the transactions involved in a deadlock.
- Deadlock victim selection: Once a deadlock is detected, the database must choose a victim transaction to abort and release its locks. Different strategies can be employed, such as selecting the transaction with the fewest resources or the lowest priority.
- Rollback and retry: After aborting a transaction, the affected queries can be retried to complete the processing successfully.

#### Locking Levels and Granularity:

Different levels of locking and granularity can be utilized in SQL databases, depending on the specific requirements and workload patterns. Common locking levels include table-level locks, page-level locks, row-level locks, and even column-level locks. Selecting an appropriate locking level can minimize the chances of conflicts and deadlocks.

### Triggers and Events

Triggers and events are powerful features in SQL databases that allows you to automate actions based on specific events or conditions. Triggers are database objects associated with tables, while events are time-based actions triggered by the database server.

#### Triggers

__Triggers__ are stored procedures (database objects) that are automatically executed in response to specific events, such as INSERT, UPDATE, or DELETE operations on a table. They allow you to enforece business rules or perform additional actions.

##### CREATE TRIGGER Statement

The __CREATE TRIGGER__ statement is used to create a new trigger in the databae. It specifies the trigger name, the table it is associated with, and the event that triggers its execution.

``` sql
CREATE TRIGGER trigger_name
BEFORE/AFTER INSERT/UPDATE/DELETE ON table_name
FOR EACH ROW
BEGIN
    -- SQL Statements
END;
```

For example:

``` sql
CREATE TRIGGER after_insert_employee
AFTER INSERT ON employees
FOR EACH ROW
BEGIN
    INSERT INTO audit_log (event_type, event_date) VALUES ('Employee Insert' , NOW())
END;
```

###### Trigger Types (BEFORE, AFTER, INSERT, UPDATE, DELETE)

Triggers can be classified based on the timing of their execution (BEFORE or AFTER) and the event that triggers them (INSERT, UPDATE, DELETE).

Trigger conditions and actions

Triggers can have conditions specified using IF statements to control their execution. They can perform various actions, such as modifying data, logging, or raising errors.

#### Events

__Events__ are scheduled tasks that execute at specified times or intervals. They are used to automate certain database actions, such as data backups or data synchronization. They are useful for automating tasks, generating reports, or performing periodic maintenance operations.

##### CREATE EVENT Statement

``` sql
CREATE EVENT event_name
ON SCHEDULE schedule
DO
    -- Event action here
```

For example:

``` SQL
CREATE EVENT daily_report
ON SCHEDULE EVERY 1 DAY
DO
    CALL generate_daily_report();
```

##### Managing Triggers

- You can query the databas's system catalog to view existing triggers associated with a table.
- Triggers can be altered using the __ALTER TRIGGER__ statement to change their behaviour or actions
- Use the __DROP TRIGGER__ statement to remvoe a trigger from a table.

##### Event scheduling

Event scheduling allows you to define when and how often an event should be executed. You can schedule events to run at specific dates and times or on a recurring basis.

##### Event management

Events can be managed using statements like ALTER, EVENT, DROP EVENT, and SHOW EVENTS. These statements allow you to modify, delete, or view the events in the database.

### User Management and Security

#### User accounts and privileges

User accounts are used to control access to the database. Privileges define what actions a user can perform on the database objects.

#### CREATE USER Statement

The __CREATE USER__ statement is used to create a new user account in the database. It specifies the usernmae and password for the user.

``` sql
CREATE USER username IDENTIFIED BY 'password';
```

#### ALTER USER Statement

The __ALTER USER__ statement is used to modify the properties of an existing user account, such as changing the password or account privileges.

``` sql
ALTER USER username IDENTIFIED BY `new_password`;
```

#### DROP USER Statement

The __DROP USER__ statement is used to delete an existing user account from the databse.

``` sql
DROP USER username;
```

#### Granting and revoking privileges

Privileges are granted to users to allow them specific permisssions on the database objects.

#### Types of Privileges

- __Object-level privileges__: These privileges are granted on specific database objects, such as table, views, procedures, or functions. Examples include: SELECT, INSERT, UPDATE, DELETE, EXECUTE, etc.
- __System-level privileges__: These privileges control administrative actions and access to system resources. Examples include: CREATE USER, ALTER DATABASE, DROP TABLESPACE, etc.
- __Grantable privileges__: Some privileges can be granted by users who posses the same privilege. This allows users to further delegate permissions to other users.

#### Grant Statements

The __GRANT__ statement is used to grant privileges to users. Privileges can be granted at different levels, such as database level, table leve, or column lege.

``` sql
GRANT privilege1, privilege2 ON table_name TO username;
```

Example:

``` sql
GRANT SELECT, INSERT ON employees
TO john;
```

In this example, the SELECT and INSERT privileges are granted on the "employees" table to the user "john."

Or:

``` sql
GRANT CREATE USER, ALTER DATABASE 
TO administrator;
```

In this example, the CREATE USER and ALTER DATABASE system-level privileges are granted to the "administrator" user.

#### Revoke Statements

The __REVOKE__ statement is used to revoke previously granted privileges from users. It removes the granted permissions, restricting users' access to certain actions or objects.

``` sql
REVOKE privilege1, privilege2 ON table_name FROM user_name;
```

Example:

``` sql
REVOKE INSERT, UPDATE ON employees
FROM john;
```

#### View Privileges

You can query the database's system catalog or use specific SQL statements (e.g. SHOW GRANTS) to view the privileges granted to users or roles.

#### GRANT OPTION

Some privileges can be granted with the GRANT OPTION, allowing users to further grant those privileges to others.

``` sql
GRANT SELECT, INSERT ON employees
TO john WITH GRANT OPTION;
```

In this example, the SELECT and INSERT privileges are granted to the user "john" with the ability to grant those privileges to other users.

## Mastery

### SQL Optimization and Performance Tuning

#### Query Optimization techniques

Query optimization involves improving the performance of SQL queries by optimizing their execution plans. Techniques include __indexing__, __query rewriting__, and __analyzing query statistics__.

#### Index Optimization

Indexes improve the speed of data retrieval by creating efficient data structures. Optimizing indexes involve selecting appropriate columns for indexing, removing redundant indexes, and regularly monitoring index usage.

#### Execution Plan Analysis

The exeution plan represents the sequence of steps used by the database engine to execute a query. Analyzing the execution plan helps identify potential bottlenecks and optimize query performance.

#### Database Configuration and Tuning

Database configuration involves adjusting various settings to optimize performance. This includes memory allocation, buffer sizes, and parallel processing settings. Regular monitoring and fine-tuning are essential for optimal performance.

### Advanced SQL Functions and Features

#### Window Functions

SQL __window function__ provide a powerful way to perform calculations and aggregations over a specific set of rows in a result set. Window functiosn opeate on a "_window"_ of rows defined by a partition and an optional ordering.

##### Syntax of Window Functions

The basic syntax for using window functions in SQL is as follows:

``` sql
SELECT column1, column2, ..., windowfunction() OVER (PARTITION BY partition_expression ORDER BY ordering_expression)
FROM table_name;
```

- __window_function()__: The specific window function to be applied.
- __PARTITION BY__: Defines the partitioning of rows within the result set. The window function operates independently of each partition.
- __ORDER BY__: Specifies the ordering of rows within each partition. It defines the sequence in which the winow function is applied.

##### Common Window Functions

Here are some commonly used window functions in SQL

- __ROW_NUMBER()__: Assigns a unique number to each row within a partition.
- __RANK()__: Assigns a rank to each row within a partition, with the same rank for ties.
- __DENSE_RANK()__: Assigns a rank to each row within a partition, with no gaps in ranking for ties.
- __NTILE(n)__: Divided the partition into "n" equal groups and assigns a group number to each row.
- __SUM()__, __AVG()__, __MIN()__, __MAX()__: Calculate the sum, average, minimum, or maximum value within a partition.
- __LEAD()__ and __LAG()__: Accesses the value of a column from a previous or subsequent row within a partition.

##### Example Usage of Window Functions

Let's consider a scneario where we have a "sales" table with columns: customer_id, order_date, and total_amount. Here are some examples of using window functions:

###### Example 1: Calculating the cumulative sum of total_amount for each customer within their orders

``` sql
SELECT customer_id, order_date, total_amount,
    SUM(total_amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS cumulative_sum
FROM sales;
```

###### Example 2: Assigning a rank to each customer based on their total_amount within their orders

``` sql
SELECT customer_id, pder_date, total_amount,
    RANK() OVER (PARTITION BY customer_id ORDER BY total_amount) AS customer_rank
FROM sales;
```

###### Example 3: Calculating the difference in total_amount between the current order and the previous order for each customer

``` sql
SELECT customer_id, order_date, total_amount.
    total_amount - LAG (total_amount) OVER (PARTITION BY customer_id ORDER BY order_date) AS amount_difference
FROM sales
```

##### Window Functions with Frame Specification

Window functions can be futher enhanced by specifying a frame, which defines the subset of rows within the partition that the function should operate on. Frame specification options include __ROWS BETWEEN__, __RANGE BETWEEN__, and __GROUPS BETWEEN__.

For example:

``` sql
SELECT customer_id, order_date, total_amount,
    SUM(total_amount) OVER (PARTITION BY customer_id ORDER BY order_date ROWS BETWEEN UNBOUND PRECEDING AND CURRENT ROW) AS cumulative_sum
FROM sales
```

In this example, the window function __SUM()__ calculates the cumulative sum of total_amount for each customer, including all rows from the start of the partition to the current row.

#### Common Table Expressions (CTEs) and Recusive CTEs

Common Table Expressions (CTEs) are temporary named result sets that can be referenced within a SQL query. They provide a way to simplify complex queries, improve query readability, and break down complex logic into manageable parts. Recursive CTEs take CTEs a step further by enabling recursive queries, useful for hadnling hierarchical data structures.

##### Common Table Expressions (CTEs)

CTEs allow you to define a temporary result set that can be referenced multiple times within a query. The syntax for creating a CTE is as follows:

``` sql
WITH cte_name (column1, column2, ...) AS (
    SELECT ...
    FROM ...
    WHERE ...
)

SELECT ...
FROM cte_name
JOIN ...
WHERE ...
```

- __WITH__: Begins the definition of a CTE
- __cte_nane__: The name assigned to the CTE
- __(column1, column2, ...)__: optional column list defining the columns returned by the CTE.
- __AS__: Separates the CTE definition from the SELECT statement that follows.

Example:

``` sql
WITH sales_summary (product_id, total_sales) AS (
    SELECT product_id, SUM(quantity * price)
    FROM sales
    GROUP BY product_id
)

SELECT p.product_names, s.total_values
FROM products p
JOIN sales_summary s ON p.product_id = s.product_id;
```

In this example, a CTE named _sales_summary_ calculates the total sales for each product in the _sales_ table. The CTE is then joined with the products table to retrieve the product names and total sales.

##### Recursive CTEs

Recrusive CTEs are a specialized form of CTEs used to handle hierarchical data structures where a table references itself. They allow you to traverse and query such hierarchical relationships. Recursive CTEs consist of two parts. The __anchor__ member and the __recursive__ member.

The syntax of Recursive CTEs is as follows:

``` sql
WITH RECURSIVE cte_name (column1, column2, ...) AS (
    -- Anchor member
    SELECT ...
    FROM ...
    WHERE ...

    UNION ALL

    -- Recursive member
    SELECT ...
    FROM ...
    JOIN ce_name ON ...
    WHERE ...
)

SELECT ...
FROM cte_name
WHERE ...
```

- __WITH RECURSIVE__: Begins the definition of a recursive CTE.
- __UNION ALL__: Combines the results of the anchor member and the recursive member.
- __JOIN cte_name__: Specifies the self-join to the CTE within the recursive member.

Example:

``` sql
WITH RECURSIVE employee_hierarchy (employee_id, employee_name, manager_id, level) AS (
    -- Anchor member
    SELECT employee_id, employee_name, manager_id, 0
    FROM employees
    WHERE manager_id IS NULL

    UNION ALL

    -- Recursive member
    SELECT e.employee_id, e.employee_name, e.manager_id, eh.level + 1
    FROM employees e
    JOIN employee_hierarchy eh ON e.manager_id = eh.employee_id
)

SELECT employee_id, employee_name, level
FROM employee_hierarchy.
```

In this example, a recurisve CTE named _employee_hierarchy_ is used to traverse and retrieve the employee hierarchy. The anchor member selects the top-level managers (those with a NULL manager_id) and the recursive member joins employees with their respective managers.

##### Benefits of CTEs and Recursive CTEs

- Simplify complex queries: CTEs break down complex logic into more manageable parts, improving query readability.
- Reusability: CTEs can be referenced multiple times within a query, reducing code duplication and improving maintainability.
- Recursive querying: Recursive CTEs enable the querying of hierarchical data structures, such as organizational charts or family trees.
- Modularization: CTEs allow you to separate different parts of a query, making it easier to understand and troubleshoot.

##### Limitations and considerations

- Performance impact: CTEs may introduce additional overhead compared to regular queries, especially when dealing with large datasets or complex recursive operations.
- Optimization: The database optimizer may not always optimize CTEs as efficiently as regular queries. Understanding query plans and performance profiling is crucial.
- Recursion depth: Recursive CTEs should be designed carefully to avoid infinite loops. Most databases impose a limit on recursion depth.

#### Pivoting and Unpivoting Data

Pivoting conerts rows into columns, while unpivoting converts columns into rows. These operations are useful for transforming data for reporting or analysis purposes.

``` sql
-- Pivoting
SELECT category,
    SUM(CASE WHEN month = 'Jan' THEN revenue END) AS jan_revenue,
    SUM(CASE WHEN month = 'feb' THEN revenue END) AS feb_revenue,
    ...
FROM sales_table
GROUP BY category;

-- Unpivoting
SELECT cateogyr, month, revenue
FROM (
    SELECT category,
    jan_revenue,
    feb_revenue,
    ...
    FROM pivoted_table
) AS subquery
UNPIVOT (revenue FRO month IN (jan_revenue, feb_revenue, ...)) AS unpivoted_table;
```

#### SQL/XML and SQL/JSON

SQL/XML and SQL/JSON are extensions to SQL that allow querying and manipulating XML and JSON data stored in the database.

### SQL and NoSQL Databases

#### SQL Support in NoSQL databases

NoSQL databases are non-relational databases designed for scalibility and high-performance. They use different data models than traditional SQL databases, such as key-value, document, columnar, or graph.

#### Comparing SQL and NoSQL Databases for Different Use Cases

SQL databases are well-suited for structured data and complex queries, while NoSQL databses excel at handling large amounts of unstructured or semi-structured data and scaling horizontally.

### SQL and Data Warehousing

#### Data Warehouse Concepts

Data warehousing involves collecting, organizing, and analyzing data from multiple sources to support business intelligence and reporting. It typically uses a separate database optimized for analytical queries.

#### ETL Processes

ETR (Extract, Transform, Load) processes involve extracting data from various sources, transforming it to fit the data warehouse schema, and loading it into the data warehouse. ETL processes ensures that data is cleansed, standardized, and transformed appropriately before being loaded into the data warehouse.

#### Start and Snoflake Schemas

Start and Snowflake schemas are common data modeling techniques used in data warehousing. In a Start schema, a central fact table is surrounded by dimension tables. A Snoflake schema expands on the Star schema by further normalizing the dimension tables.

#### OLAP anad Analytical Queries

Online Analytical Processing (OLAP) is a technology used for multidimensional analysis of data in a data wareohouse. OLAP queries involve aggregating and summarizing data across multiple dimensions to provide insights and support decision-making.

### SQL and Big Data

#### Big data Concepts and platforms (Hadoop, Spark)

Big data refers to large and complex data sets that are difficult to process using traditional database systems. Hadoop and Spark are popular big data platforms that support distributed processing and sotrage of large-sclae data.

#### SQL On Big Data (Hive, Impala, Presto, etc)

To work with big data, SQL-like query languages and tools have been developed to provide a familiar interface. Hive, Impala, and Presto are examples of SQL engines that enable querying and analysis of big data stored in Hadoop or other distributed systems.

#### Analyzing Big Data with SQL

SQL can be used to perform various analytical tasks on big data, such as aggregations, filtering, joining, and machine learning algorithms. SQL's flexibility and expressie power make it a valuable tool for analyzing large and diverse data sets.

## END

Finally, we have convered all the topics necessary to learn SQL at an advanced level and touched all the important mastery level concepts.

## Farewell

Thank you for reading this Github article on Advanced Python Concepts. Creating this tutorial project was very fun and I hope you enjoyed reading it as much as I enjoyed creating it.

You can visit our website for more tutorials, guides, case studies, and more by [clicking here](https://www.analysistutorial.com/).

Farewell.
