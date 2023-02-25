# CTE Mastery: A complete beginner to advanced common table expressions Tutorial

Learn the power of Common Table Expressions (CTE) in SQL and take your skills to the next level. In this tutorial, you'll discover how CTE can simplify your queries, improve readability and boost performance. From basic to advanced, we'll cover everything you need to know about this essential tool for working with data in MySQL.

## Introduction

Hello and welcome to the complete beginner to advanced common table expressions tutorial. Whether it is your first time reading on common table expressions or you have used them before but want to unlock the complete potential common table expressions offer this tutorial is for you.

This tutorial is designed to first introduce to basic concept on common table expressions and gradually teach you more advanced concept along the way.

## 1) Common Table Expressions: Basic CTE Concepts

A common table expression (CTE) is a named temporary result set that exists within the scope of a single statement and that can be referenced to later within that statement, possibly multiple times.

In SQL, every statement or query produces a temporary result or relation. A CTE is used to name those temporary result sets that exist the execution scope of that particular statement, such as CREATE, INSERT, SELECT, UPDATE, DELETE, etc.
Similar to a derived table, a CTE is not stored as an object and lasts only during the execution of a query. But unlike a derived table, a CTE can be self-referencing -Also called a recursive CTE, but more on that later.

CTEs are usually used to replace complex subqueries in order to make them more readable.

## 2) Table of Content

* Common Table Expressions: CTE Syntax
* Common Table Expressions: Recursive CTEs
  * 4.1) Recursive CTEs: Widening result columns
  * 4.2) Recursive CTEs: Column Access
  * 4.3) Recursive CTEs: Limiting Recursions
  * 4.4) Recursive CTEs: Constrains
* Series Generation
* Data Series Generation

## 3) Common Table Expressions CTE Syntax

To specify common table expressions, use a WITH clause that has one or more comma-separated subclauses. Each subclause provides a subquery that produces a result set, and associates a name with the subquery.

```MySQL
WITH
    cte_name  [(col_name, col_name, ...)] AS (sub_query),
    cte_name  [(col_name, col_name, ...)] AS (sub_query),

```

Example:

```MySQL
WITH
    cte1 AS (SELECT a, b FROM table1),
    cte2 AS (SELECT c, d FROM table2)
SELECT b, d FROM cte1 JOIN cte2
WHERE cte1.a = cte2.c;

```

In this example, two CTEs, Cte1 and Cte2, are defined using SELECT statements that select columns from two different tables, table1 and table2.

The SELECT statement outside of the CTEs then uses JOIN to combine the results of the two CTEs, selecting the b column from Cte1 and the d column from Cte2. The WHERE clause specifies that the results should only include rows where the a column from Cte1 matches the c column from Cte2.

This example shows how CTEs can be used to break down complex SQL queries into smaller, more manageable pieces. The CTEs act as temporary tables that can be used to simplify the main query, making it easier to write and understand.

Key points:

* CTEs start by using the WITH clause
* The WITH clause allows can define one or more common table expressions, but each CTE name must be unique to the clause.
* If a parenthesized list of names follows the CTE name, those names are the column names.
  * The number of names in the list must be the same as the number of columns in the result set. Otherwise, the names come from the select list of first SELECT (within AS (subquery) part.
* Only one WITH clause is permitted at the same level. WITH followed by WITH at the same level is not permitted.
  * A statement can contain multiple WITH clauses if they occur at different levels
* A CTE name can be referenced in other CTEs, enabling CTEs to be defined based on other CTEs. But, CTEs can refer to other CTEs that are defined earlier in the same WITH clause, but not those defined later.
* A CTE in a query block can refer to CTEs defined in query blocks at a more outer level, but not CTEs defined in query blocks at more inner level.

And finally, a WITH clause is permitted in these contexts:
At the beginning of SELECT, UPDATE, and DELETE statements:

```MySQL
WITH ... SELECT ...
WITH ... UPDATE ...
WITH ... DELETE ...

# For example:
  # tbi_next_commit
```

At the beginning of subqueries (including derived table subqueries):

```MySQL
SELECT ... WHERE id IN (WITH ... SELECT ...) ...
SELECT * FROM (WITH ...SELECT ...) as dt ...

# For example:
  # tbi_next_commit
```

Immediately before SELECT. For statements that include SELECT statements:

```MySQL
INSERT ... WITH SELECT ...
REPLACE ... WITH ... SELECT ...
CREATE TABLE ... WITH ... SELECT ...
DECLARE VIEW ... WITH ... SELECT ...

# For Example
  # tbi_next_commit
```

## 4) Common Table Expressions: Recursive CTEs

A CTE can refer to itself to define a recursive CTE.

```MySQL
WITH RECURSIVE cte (n) AS {
  SELECT 1
  UNION ALL
  SELECT n + 1 From cte WHERE n < 5>
}
SELECT * FROM cte;
```

This is an example of a recursive CTE in SQL. It generates a sequence of numbers from 1 to 5.

The CTE is named "cte", and it is defined using the "WITH RECURSIVE" clause. The "cte" has one column, "n", which represents the current number in the sequence.

The CTE starts with a SELECT statement that returns the first number in the sequence, which is 1.
The recursive part of the CTE is defined using the UNION ALL operator. It consists of a SELECT statement that adds 1 to the current number in the sequence, and then joins the result back to the "cte" using the WHERE clause to stop the recursion when the number reaches 5.

Finally, the SELECT statement outside the CTE is used to return all the numbers generated by the CTE.
The output of this code will be a single column with values 1, 2, 3, 4, and 5.

Common applications of recursive CTEs include: Series generation, traversal of hierarchical data, and traversal of tree-structured data. We'll explain these use cases later in the article.

Let's break down the basics of recursive CTEs:

* The WITH clause must begin by a WITH RECURSIVE
  * Non-recursive CTEs can also use WITH RECURSIVE but the RECURSIVE part is ignored by the interpretor
* The recursive CTE subquery has two parts, separated by UNION ALL or UNION DISTINCT.
  * The first SELECT produces the initial row or rows for the CTE and does not refer to the CTE name.
  * The second SELECT produces additional rows and recurses by referring to the CTE name in its FROM clause.
* The types of the CTE columns are inferred from the column types of the non-recursive SELECT part only, and the columns are all nullable. For type determination, the recursive SELECT part is ignored.
* If the non-recursive and the recursive parts are separated by UNION DISTINCT, duplicate rows are eliminated.
  * This is useful for queries that perform transitive closures, to avoid infinite loops.
* Each iteration of the recursive part operates only on the rows produced by the previous iteration. If the recursive part has multiple query blocks, iterations of each query block are scheduled in unspecific order, and each query block operates on rows that have been produced either by its previous iteration or by other query blocks since that previous iteration's end.

### 4.1) Recursive CTEs: Widening result columns

Consider the following example:

```MySQL
WITH RECURSIVE cte AS (
  SELECT 1 AS n, 'abc' AS str
  UNION ALL
  SELECT n + 1, CONCAT(str, str) FROM cte WHERE n<3>
)
SELECT * FROM cte;
```

in nonstrict SQL mpde, the statement produces this output:

| n    | str  |
|:------:|:------:|
|    1 | abc  |
|    2 | abc  |
|    3 | abc  |

The str column values are all 'abc' because the nonrecursive SELECT determines the column widths. Consequently, the wider str values produced by the recursive SELECT are truncated.

In strict SQL mode, the statement produces an error:

```MySQL
ERROR 1406 (22001): Data too long for column 'str' at row 1
```

To address this issue, so that the statement does not produce truncation or errors, use CAST() in the non-recursive SELECT to make the str column wider:

```MySQL
WITH RECURSIVE cte AS (
  SELECT 1 AS n, CAST('abc' AS CHAR(20)) AS str
  UNION ALL
  SELECT n + 1, CONCAT(str, str) FROM cte WHERE n < 3
)
SELECT * FROM cte;
```

Now the statement produces this result, without truncation:

| n    | str          |
|:------:|--------------|
|    1 | abc          |
|    2 | abcabc       |
|    3 | abcabcabcabc |

### 4.2) Recursive CTEs: Column Access

Columns are accessed by name, not position, which means that columns in the recursive part can access columns in the non-recursive part that have a different position, as this CTE illustrates:

```MySQL
WITH RECURSIVE cte AS (
 SELECT 1 AS n, 1 AS p, -1 AS q
  UNION ALL
  SELECT n + 1, q * 2, p * 2 FROM cte WHERE n < 5
)
SELECT * FROM cte;
```

Because p in one row is derived from q in the previous row, and vice versa, the positive and negative values swap positions in each successive row of the output:

| n    | p    | q    |
|:------:|------:|------:|
|    1 |    1 |   -1 |
|    2 |   -2 |    2 |
|    3 |    4 |   -4 |
|    4 |   -8 |    8 |
|    5 |   16 |  -16 |

### 4.3) Recursive CTEs: Limiting recursions

It is important for recursive CTEs that the recursive SELECT part include a condition to terminate recursion. As a development technique to guard against a runaway recursive CTE, you can force termination by placing a limit on execution time:

* The **cte_max_recursion_depth** system variable enforces a limit on the number of recursion levels for CTEs. The server terminates execution of any CTE that recuses more lvel that the value of this variable.
* The **max_execution_time** system variable enforces an execution timeout for SELECT statements executed within the current session.
* The **MAX_EXECUTION_TIME** optimizer hint enforces a per-query execution timeout for the SELECT statement in which it appears.

Suppose that a recursive CTE is a mistakenly written with no recursion execution termination condition:

```MySQL
WITH RECURSIVE cte (n) AS (
  SELECT 1
  UNION ALL
  SELECT n + 1 FROM cte
)
SELECT * FROM cte;
```

By default, **cte_max_recursion_depth** has a value of 1000. Causing the CTE to terminate when it recurses past 1000 levels. Applications can change the session value to adjust for their requirements:

```MySQL
SET SESSION cte_max_recusion_depth = 10;  --permit only shallow recursion
SET SESSION cte_max_recursion_depth = 1000000; --permit deeper recursion
```

You can also set the global **cte_max_recursion_depth** value to affect all sessions that begin subsequently.
For queries that execute and thus recurse slowly or in context for which there is reason to set the cte_max_recursion_depth value very high, another way to guard against deep recursion is to set a per-session timeout. To do so, execute a statement this before executing the CTE statement:

```MySQL
SET max_execution_time = 1000;  --impose one second timeout
```

Alternatively, include an optimizer hint within the CTE statement itself:

```MySQL
WITH RECURSIVE cte (n) AS
(
  SELECT 1
  UNION ALL
  SELECT n + 1 FROM cte
)
SELECT /*+ SET_VAR(cte_max_recursion_depth = 1M) */ * FROM cte;

WITH RECURSIVE cte (n) AS
(
  SELECT 1
  UNION ALL
  SELECT n + 1 FROM cte
)
SELECT /*+ MAX_EXECUTION_TIME(1000) */ * FROM cte;
```

Beginning with MySQL 8.0.19 you can also use LIMIT within the recursive query to impose a maximum number of rows to be returned to the outermost SELECT, for example:

```MySQL
WITH RECURSIVE cte (n) AS
(
  SELECT 1
  UNION ALL
  SELECT n + 1 FROM cte LIMIT 10000
)
SELECT * FROM cte;
```

You can do this in addition to or instead of setting a time limit. Thus, the following CTE terminates after returning ten thousand rows or running for one second (1000 milliseconds), whichever occurs first:

```MySQL
WITH RECURSIVE cte (n) AS
(
  SELECT 1
  UNION ALL
  SELECT n + 1 FROM cte LIMIT 10000
)
SELECT /*+ MAX_EXECUTION_TIME(1000) */ * FROM cte;
```

If a recursive query without an execution time limit enters an infinite loop, you can terminate it from another session using KILL_QUERY. Within the session itself, the client program used to run the query might provide a way to kill query. For example, in MySQL, typing Control + C interrupts the current statement.

### 4.4) Recursive CTEs: Constrains

Some syntax constraints apply within recursive CTE subqueries. The recursive SELECT part must not contain these constructs:

* Aggregate functions such as SUM()
Window functions
* GROUP BY
* ORDER BY
* DISTINC
  * The prohibition on DISTINC applies only to UNION members; UNION DISTINC is permitted
* LIMIT

Since MySQL 9.0.19, the recursive part of CTE can use LIMIT along with an optional OFFSET clause. The effect on the result set is the same as when using LIMIT in the outermost SELECT, but is also more efficient, since using it with the recursive SELECT stops the generation of rows as soon as the requested number of them has produced. These constraints do not apply to the non-recursive SELECT part of a recursive CTE.

These constrains come from the SQL standard, other than the MySQL-specific exclusion of ORDER BY, LIMIT (in MySQL 8.0.10 and earlier), and DISTINCT.

Note that the above constraints do not apply to the non-recursive part.

Because a CTE cannot refer other CTEs defined after, mutually-recursive CTEs are ruled out, where cte1 references cte2 and cte2 references cte1. One of those references must be to a CTE defined later, which is not permitted. In addition, the recursive member can only reference the CTE name once and in its FROM clause, not in any subquery.

For recursive CTEs, EXPLAIN output rows for recursive SELECT parts display recursive in the extra column.

Cost estimates displayed by EXPLAIN represent cost per iteration, which might differ considerably from total cost, the optimizer cannot predict the number of iterations because it cannot predict at what point the WHERE clause becomes false.

CTE actual cost may also be affected by result set size. A CTE that produces many rows may require an internal temporary table large enough to be converted from in-memory to on-disk format and may suffer a performance penalty. If so, increasing the permitted in-memory temporary table size may improve performance

## 5) Series Generation

As mentioned previously, recursive common table expressions (CTEs) are frequently used for series generation.

A Fibonacci series begins with the two numbers 0 and 1 (or 1 and 1) and each number after that is the sum of the previous two numbers. A recursive common table expression can generate a Fibonacci series if each row produced by the recursive SELECT has access to the two previous numbers from the series. The following CTE generates a 10-number series using 0 and 1 as the first two numbers:

```MySQL
WITH RECURSIVE fibonacci (n, fib_n, next_fib_n) AS(
  SELECT 1, 0, 1
  UNION ALL
  SELECT n + 1, next_fib_n, fib_n + next_fib_n
    FROM fibonacci WHERE n < 10
)
SELECT * FROM fibonacci;
```

The CTE produces this result:

| n    | fib_n | next_fib_n |
|------|-------|------------|
|    1 |     0 |          1 |
|    2 |     1 |          1 |
|    3 |     1 |          2 |
|    4 |     2 |          3 |
|    5 |     3 |          5 |
|    6 |     5 |          8 |
|    7 |     8 |         13 |
|    8 |    13 |         21 |
|    9 |    21 |         34 |
|   10 |    34 |         55 |

How the CTE works:

n is a display column to indicate that the row contains the n-th Fibonacci number. For example, the 8th Fibonacci number is 13.
The fib_n column displays Fibonacci number n.
The next_fib_n column displays the next Fibonacci number after number n. This column provides the next series value to the next row, so that row can produce the sum of the two previous series values in its fib_n column.
Recursion ends when n reaches 10. This is an arbitrary choice, to limit the output to a small set of rows.

The preceding output shows the entire CTE result. To select just part of it, add an appropriate WHERE clause to the top-level SELECT. For example, to select the 8th Fibonacci number, do this:

```MySQL
WITH RECURSIVE fibonacci ...
...
SELECT fib_n FROM fibonacci WHERE n = 8;

+-------+
| fib_n |
+-------+
|    13 |
+-------+
```

## 6) Data Series Generation

A common table expression can generate a series of successive dates, which is useful for generation summaries that include a row for all dates in the series, including dates not represented in the summarized data.
Suppose that a table of sales numbers contains these rows:

```MySQL
SELECT * FROM sales ORDER BY date, price;
+------------+--------+
| date       | price  |
+------------+--------+
| 2017-01-03 | 100.00 |
| 2017-01-03 | 200.00 |
| 2017-01-06 |  50.00 |
| 2017-01-08 |  10.00 |
| 2017-01-08 |  20.00 |
| 2017-01-08 | 150.00 |
| 2017-01-10 |   5.00 |
+------------+--------+
```

This query summarizes the sales per day:

```MySQL
SELECT date, SUM(price) AS sum_price
       FROM sales
       GROUP BY date
       ORDER BY date;
+------------+-----------+
| date       | sum_price |
+------------+-----------+
| 2017-01-03 |    300.00 |
| 2017-01-06 |     50.00 |
| 2017-01-08 |    180.00 |
| 2017-01-10 |      5.00 |
+------------+-----------+
```

However, that result contains "holes" for dates not represented in the range of dates spanned by the table. A result that represents all dates in the range can be produced using a recursive CTE to generate that set of dates, joined with a LEFT JOIN to the sales data.
Here is the CTE to generate the date range series:

```MySQL
WITH RECURSIVE dates (date) AS (
  SELECT MIN(date) FROM sales
  UNION ALL
  SELECT date + INTERVAL 1 DAY FROM dates
  WHERE date + INTERVAL 1 DAY <= (SELECT MAX(date) FROM sales)
)
SELECT * FROM dates;
```

The CTE produces this result:

| date       |
|------------|
| 2017-01-03 |
| 2017-01-04 |
| 2017-01-05 |
| 2017-01-06 |
| 2017-01-07 |
| 2017-01-08 |
| 2017-01-09 |
| 2017-01-10 |

How the CTE works:

The nonrecursive SELECT produces the lowest date in the date range spanned by the sales table.

Each row produced by the recursive SELECT adds one day to the date produced by the previous row.

Recursion ends after the dates reach the highest date in the date range spanned by the sales table.

Joining the CTE with a LEFT JOIN against the sales table produces the sales summary with a row for each date in the range:

```MySQL
WITH RECURSIVE dates (date) AS (
  SELECT MIN(date) FROM sales
  UNION ALL
  SELECT date + INTERVAL 1 DAY FROM dates
  WHERE date + INTERVAL 1 DAY <= (SELECT MAX(date) FROM sales)
)
SELECT dates.date, COALESCE(SUM(price), 0) AS sum_price
FROM dates LEFT JOIN sales ON dates.date = sales.date
GROUP BY dates.date
ORDER BY dates.date;
```

The output looks like this:

| date       | sum_price |
|------------|-----------|
| 2017-01-03 |    300.00 |
| 2017-01-04 |      0.00 |
| 2017-01-05 |      0.00 |
| 2017-01-06 |     50.00 |
| 2017-01-07 |      0.00 |
| 2017-01-08 |    180.00 |
| 2017-01-09 |      0.00 |
| 2017-01-10 |      5.00 |

Some points to note:

* Are the queries inefficient, particularly the one with the MAX() subquery executed for each row in the recursive SELECT? EXPLAIN shows that the subquery containing MAX() is evaluated only once and the result is cached.
* The use of COALESCE() avoids displaying NULL in the sum_price column on days for which no sales data occur in the sales table.

## 7) Hierarchical Data Traversal

Recursive common table expressions are useful for traversing data that forms hierarchy.

Consider these statements that create a small data set that shows, for each employee in a company, the employee name and ID number, and the ID of the employee's manager. The top-level employee (the CEO), has a manager ID of NULL (no manager).

```MySQL
CREATE TABLE employees (
  id         INT PRIMARY KEY NOT NULL,
  name       VARCHAR(100) NOT NULL,
  manager_id INT NULL,
  INDEX (manager_id),
FOREIGN KEY (manager_id) REFERENCES employees (id)
);
INSERT INTO employees VALUES
(333, "Yasmina", NULL),  # Yasmina is the CEO (manager_id is NULL)
(198, "John", 333),      # John has ID 198 and reports to 333 (Yasmina)
(692, "Tarek", 333),
(29, "Pedro", 198),
(4610, "Sarah", 29),
(72, "Pierre", 29),
(123, "Adil", 692);
The resulting data set looks like this:
SELECT * FROM employees ORDER BY id;
```

| id   | name    | manager_id |
|------|---------|------------|
|   29 | Pedro   |        198 |
|   72 | Pierre  |         29 |
|  123 | Adil    |        692 |
|  198 | John    |        333 |
|  333 | Yasmina |       NULL |
|  692 | Tarek   |        333 |
| 4610 | Sarah   |         29 |

To produce the organizational chart with the management chain for each employee (that is, the path from CEO to employee), use a recursive CTE:

```MySQL
WITH RECURSIVE employee_paths (id, name, path) AS (
  SELECT id, name, CAST(id AS CHAR(200))
    FROM employees
    WHERE manager_id IS NULL
  UNION ALL
  SELECT e.id, e.name, CONCAT(ep.path, ',', e.id)
    FROM employee_paths AS ep JOIN employees AS e
      ON ep.id = e.manager_id
)
SELECT * FROM employee_paths ORDER BY path;
```

The CTE produces this output:

| id   | name    | path            |
|------|---------|-----------------|
|  333 | Yasmina | 333             |
|  198 | John    | 333,198         |
|   29 | Pedro   | 333,198,29      |
| 4610 | Sarah   | 333,198,29,4610 |
|   72 | Pierre  | 333,198,29,72   |
|  692 | Tarek   | 333,692         |
|  123 | Adil    | 333,692,123     |

How the CTE works:

The nonrecursive SELECT produces the row for the CEO (the row with a NULL manager ID).
The path column is widened to CHAR(200) to ensure that there is room for the longer path values produced by the recursive SELECT.
Each row produced by the recursive SELECT finds all employees who report directly to an employee produced by a previous row. For each such employee, the row includes the employee ID and name, and the employee management chain. The chain is the manager's chain, with the employee ID added to the end.

Recursion ends when employees have no others who report to them.

To find the path for a specific employee or employees, add a WHERE clause to the top-level SELECT. For example, to display the results for Tarek and Sarah, modify that SELECT like this:

```MySQL
WITH RECURSIVE ...
       ...
SELECT * FROM employees_extended
  WHERE id IN (692, 4610)
  ORDER BY path;
+------+-------+-----------------+
| id   | name  | path            |
+------+-------+-----------------+
| 4610 | Sarah | 333,198,29,4610 |
|  692 | Tarek | 333,692         |
+------+-------+-----------------+
```

## 8) common Table Expressions Compared to Similar Constructs

Common Table expressions (CTEs) are similar to derived tables in some ways:

* Both constructs are named.
* Both constructs exist for the scope of a single statement

Because of these similarities, CTEs and derived tables often can be used interchangeably. As a trivial example, these statements are equivalent:

```MySQL
WITH cte AS (SELECT 1) SELECT * FROM cte;
SELECT * FROM (SELECT 1) as dt;
```

However, CTEs have some advantages over derived tables:

* A derived table can be referenced only a single time within a query. A CTE can be referenced multiple times. To use multiple instances of a derived table result, you must derive the result multiple times.
* A CTE can be self-referencing (recursive).
*One CTE can refer to another.
* A CTE may be easier to read when its definitions appear at the beginning of the statement rather than embedded within it.

CTEs are similar to tables created with CREATE "TEMPORARY" TABLE but need not be defined or dropped explicitly. For a CTE, you need no privileges to create tables.
