# Topics

Here are the categorized topics:

### SQL: Postgres
- Forks
- Client/server model
- Data types Unique to Postgres
  - interval
  - point
  - bigserial
  - etc…
- Database cluster

### Theory
- SQL vs NoSQL (Relational vs non-relational)
- Web-scaled
- When to use SQL and NoSQL
- Expression, Statement, Operators

### Data Types SQL
- null, bit
- int, real / float
- char, varchar, text
- boolean
- date, datetime, timestamp
- xml/json
  - char vs varchar vs text
  - datetime vs timestamp
  - JSON vs JSONB

### Operators
- Arithmetic, Logical, Comparison, Bitwise

### Primitives
- Integer, Numeric, String, Boolean

### Structured
- Date/Time, Array, Range / Multirange, UUID

### Document
- JSON/JSONB, XML, Key-value (Hstore)

### Geometry
- Point, Line, Circle, Polygon

### Customizations
- Composite, Custom Types

### Constraints
- UNIQUE
- NOT NULL
- PRIMARY KEY as UUID
- FOREIGN KEY
- CHECK (<condition>)
- Adding & removing constraints after creating table

### Commands
- List db
- Connect
- List tables
- Move to super
- List specific table
- List current table
- Creating
  - Database
  - Table
  - Drop
  - Drop DB
  - Drop Table
  - Drop constraints
- Database migration
  - Add, Delete, Migration
  - Up migration
  - Down migration

### Functions
- SELECT
- LIMIT
- FETCH
- OFFSET
- AS
- DISTINCT
- GROUP BY
- HAVING
- GROUPING SETS
- ROLLUP
- CUBE
- Having vs Where
- Limit vs Fetch
- FROM
- WHERE
- AND, OR
- LIKE, ILIKE
- BETWEEN
- IN
- IS NULL, IS NOT NULL
- ORDER BY
- DESC, ASC
- DELETE
- DELETING FOREIGN KEY
- CASCADE
- UPDATE
- SET
- RENAME COLUMN
- JOIN
  - INNER JOIN
  - ON 
  - LEFT JOIN
  - RIGHT JOIN
  - FULL JOIN (FULL OUTER JOIN)
  - SELF JOIN
  - CROSS JOIN
  - NATURAL JOIN

### Views
- Pros and Cons
- CREATE VIEW
- Materialized View

### Write Amplification
- UNION
- COALESCE
- NULLIF

### Index
- Multi index
- AUTO_INCREMENT
- ON CONFLICT
  - DO NOTHING
  - Upserting
    - DO UPDATE
  - EXCLUDED

### Date Functions
- INTERVAL vs AGE

### Aggregate Functions
- AVG, MIN, MAX, SUM, ROUND, COUNT, CONCAT

### Scalar Functions
- LCASE, CASE, LEN, MID, ROUND, NOW, FORMAT
- INITCAP, LEFT, RIGHT, CONCAT, ABS, CEIL, FLOOR
- UPPER AND LOWER in psql.

### Aggregate vs Scalar

### Window Function
- OVER
  - PARTITION BY, RANK, LEAD, LAG

### CASE

### SQL Commands
- DDL
  - CREATE, ALTER, DROP, TRUNCATE
  - DROP vs TRUNCATE
- DML
  - INSERT, SELECT, UPDATE, DELETE
- DCL
  - GRANT, REVOKE
- TCL
  - COMMIT
  - ROLLBACK
  - SAVE POINT
- DQL
  - SELECT

### 3-Schema Architecture
- Internal level
- Conceptual level
- External level

### BIGINT VS BIGSERIAL

### Combining Queries
- UNION, UNION ALL
- INTERSECT, INTERSECT ALL
- EXCEPT, EXCEPT ALL

### Normalization
- Levels
  - 1NF, 2NF, 3NF etc..
  - BCNF
- Anomalies
  - Insertion anomalies
  - Deletion anomalies
  - Updation anomalies
- Data redundancy
- Missing data
- Losing data
- Inconsistency
- Updating values on so many records unnecessarily

### Relationship
- One to one
- One to many
- Many to many

### Transaction & ACID
- Transaction
  - COMMIT
  - ROLLBACK
  - SAVE POINT
  - RELEASE SAVEPOINT
  - LOCK
    - Exclusive Locks (X-Locks)
    - Shared Locks (S-Locks)
    - Update Locks (U-Locks)
    - Intent Locks
    - Read and Write Locks
- ACID
  - Atomicity 
  - Consistency
    - Consistency in data
    - Consistency in reads
  - Isolation
    - Read phenomena
      - Dirty reads
      - Non-repeatable reads
      - Phantom reads
    - Serializations
      - (Lost updates)
    - Isolation level
      - Read uncommitted
      - Read committed
      - Repeatable Reads
      - Transactions are Serialized
  - Durability
- How to implement ACID properties
- EXPLAIN
  - Heap Scan
  - Parallel Scan
- Planner

### Other Theory and Functions
- COPY
- OLTP
- MUCC
- Pendings
- Delete vs truncate
- Candidate key vs super key
- Stored procedure
- ER diagram.
- Practice nested queries.

---


# Databases Overview

## Introduction

Databases are like big electronic filing cabinets that hold lots of information. They help us keep everything neat and tidy, making it super easy to find, add, or change stuff whenever we need to. Imagine you're using a website to shop, chat with friends, or look up books in a library—databases are the magic behind the scenes that make all these things work smoothly. In this video I'll be giving you a simple rundown of what databases are, why they matter so much in today's digital world, and how they help us every day.

## What is a Database?

A database is an organized collection of data, generally stored and accessed electronically from a computer system. The data can be anything from a simple list of names to complex data like detailed information about users' activities on a website. Databases are managed by Database Management Systems (DBMS), which provide tools for creating, retrieving, updating, and deleting data.

## Types of Databases

Databases come in various types, each suited to different needs:

1. **Relational Databases**: These are the most common type, where data is stored in tables. Tables are organized into rows and columns. Each row is a record, and each column is a field. SQL (Structured Query Language) is typically used to manage and query relational databases.
   
2. **NoSQL Databases**: These are designed to handle large volumes of data that might not fit neatly into tables. They are used for big data and real-time web applications. Examples include MongoDB and Cassandra.

3. **In-Memory Databases**: These store data in the main memory (RAM) of a computer, allowing for fast access. They are often used in applications where speed is critical.

4. **Cloud Databases**: These are databases that run on cloud computing platforms, like Amazon Web Services (AWS) or Google Cloud. They offer flexibility, scalability, and are often easier to manage.

5. **Graph Databases**: These are used to store data in graph structures, with nodes, edges, and properties. They are particularly useful for applications like social networks, where relationships between data points are complex.

## Key Concepts in Databases

### Tables, Rows, and Columns

In a relational database, data is organized into tables. Each table has rows and columns. Columns define the type of data, and rows contain the actual data. For example, in a table of students, columns might include StudentID, Name, and Age, while each row would contain the data for one student.

### Primary Key and Foreign Key

A **primary key** is a unique identifier for each record in a table. For example, a StudentID can be a primary key in a students table. A **foreign key** is a field in one table that uniquely identifies a row of another table. Foreign keys are used to establish and enforce a link between the data in the two tables.

### ACID Properties

ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties ensure reliable processing of database transactions:

- **Atomicity**: Ensures that each transaction is all or nothing.
  - Think of it like buying movie tickets online. Either you get all the tickets you want, or none at all. If something goes wrong during the purchase, you won't end up paying without getting any tickets. That's atomicity—everything happens as a whole, or nothing happens at all.
- **Consistency**: Ensures that a transaction brings the database from one valid state to another.
  -  Imagine playing a video game where you save your progress. After saving, you expect to come back to exactly where you left off, with all your items and levels intact. Consistency means that after any operation, like saving your game, the game world stays in a state that makes sense according to its rules.
- **Isolation**: Ensures that transactions do not interfere with each other.
  - Picture yourself shopping at a busy grocery store. Even though everyone is grabbing items at the same time, you don't worry about someone else taking the last item you wanted just as you reach for it. In the digital world, isolation means that even when many people are accessing the same data, each person's actions don't mess up others' experiences.
- **Durability**: Ensures that once a transaction is committed, it remains so even in the event of a system failure.
  - Consider writing a letter and mailing it. Once it's sent, you know it will eventually reach its destination unless something really unusual happens. Durability in databases works similarly. Once data is saved, it stays saved. Even if the computer crashes or loses power, the data doesn't disappear—it's still there when everything comes back online.

### Normalization

Normalization is a process in database design used to reduce data redundancy and improve data integrity. It involves organizing the fields and tables of a database to minimize duplication. The main stages of normalization are:

1. **First Normal Form (1NF)**: Ensures that each table column contains atomic values, and each column contains only a single value.
2. **Second Normal Form (2NF)**: Ensures that all non-key attributes are fully functional dependent on the primary key.
3. **Third Normal Form (3NF)**: Ensures that all the attributes are not only dependent on the primary key but are also non-transitively dependent.

## SQL: The Language of Databases

SQL, or Structured Query Language, is the standard language for interacting with relational databases. It allows users to create, read, update, and delete data.

### Basic SQL Commands

- **SELECT**: Retrieves data from a database.
  ```sql
  SELECT * FROM students;
  ```
- **INSERT**: Adds new data to a database.
  ```sql
  INSERT INTO students (StudentID, Name, Age) VALUES (1, 'John Doe', 20);
  ```
- **UPDATE**: Modifies existing data in a database.
  ```sql
  UPDATE students SET Age = 21 WHERE StudentID = 1;
  ```
- **DELETE**: Removes data from a database.
  ```sql
  DELETE FROM students WHERE StudentID = 1;
  ```

### Joins

SQL allows you to combine rows from two or more tables based on a related column. This is done using JOIN operations:

- **INNER JOIN**: Returns records that have matching values in both tables.
  ```sql
  SELECT students.Name, courses.CourseName
  FROM students
  INNER JOIN enrollments ON students.StudentID = enrollments.StudentID
  INNER JOIN courses ON enrollments.CourseID = courses.CourseID;
  ```

- **LEFT JOIN**: Returns all records from the left table, and the matched records from the right table.
  ```sql
  SELECT students.Name, enrollments.CourseID
  FROM students
  LEFT JOIN enrollments ON students.StudentID = enrollments.StudentID;
  ```

## Indexing

Indexing is a technique to optimize the performance of a database. An index is a data structure that improves the speed of data retrieval operations on a table at the cost of additional writes and storage space. Think of it like an index in a book, which helps you find information quickly without having to read through every page.

## Transactions

A transaction is a sequence of one or more SQL operations treated as a single unit. Transactions ensure that all operations within the unit are completed successfully before the data is committed to the database. If any operation within the transaction fails, the entire transaction is rolled back.

### Example

```sql
BEGIN TRANSACTION;

UPDATE accounts SET balance = balance - 100 WHERE account_id = 1;
UPDATE accounts SET balance = balance + 100 WHERE account_id = 2;

COMMIT;
```

In the example above, money is transferred from one account to another. If both updates are successful, the transaction is committed. If either update fails, the transaction is rolled back, ensuring that the accounts remain in a consistent state.

## Data Manipulation and Definition Languages

### DML (Data Manipulation Language)

DML includes SQL commands that deal with the manipulation of data:
- **SELECT**: Retrieves data.
- **INSERT**: Adds new data.
- **UPDATE**: Modifies existing data.
- **DELETE**: Removes data.

### DDL (Data Definition Language)

DDL includes SQL commands that define the database structure:
- **CREATE**: Creates a new table or database.
  ```sql
  CREATE TABLE students (
      StudentID INT PRIMARY KEY,
      Name VARCHAR(100),
      Age INT
  );
  ```
- **ALTER**: Modifies an existing database object, like a table.
  ```sql
  ALTER TABLE students ADD COLUMN Email VARCHAR(100);
  ```
- **DROP**: Deletes a table or database.
  ```sql
  DROP TABLE students;
  ```

### DCL (Data Control Language)

DCL includes SQL commands that control access to data within the database:
- **GRANT**: Gives a user access privileges to the database.
  ```sql
  GRANT SELECT ON students TO user1;
  ```
- **REVOKE**: Removes user access privileges.
  ```sql
  REVOKE SELECT ON students FROM user1;
  ```

## Three-Schema Architecture

The three-schema architecture is a framework for understanding the different levels of database abstraction:

1. **External Schema**: The user's view of the database.
2. **Conceptual Schema**: The community user's view of the entire database.
3. **Internal Schema**: The physical storage structure of the database.

This architecture helps in database design and management by separating the user's view, the logical organization, and the physical storage.

## Conclusion

Databases are essential for managing data efficiently and effectively. They enable us to store, retrieve, and manipulate data with ease. Understanding the basics of databases, including their types, key concepts, and SQL commands, is crucial for anyone involved in data management or software development. Whether you're designing a small personal project or a large-scale application, the principles and techniques discussed in this essay will provide a solid foundation for working with databases. As technology continues to evolve, databases will remain a critical component of our digital world, driving innovation and enabling new possibilities.


---

# Overview of SQL Commands in PostgreSQL

### Data Definition Language (DDL) Commands

#### 1. `CREATE`

- **Database**
  ```sql
  CREATE DATABASE mydb;
  ```

- **Table**
  ```sql
  CREATE TABLE employees (
      id SERIAL PRIMARY KEY,
      name VARCHAR(100),
      position VARCHAR(50),
      salary NUMERIC
  );
  ```

- **Index**
  ```sql
  CREATE INDEX idx_employee_name ON employees (name);
  ```

- **Schema**
  ```sql
  CREATE SCHEMA myschema;
  ```

#### 2. `ALTER`

- **Table**
  ```sql
  ALTER TABLE employees ADD COLUMN email VARCHAR(100);
  ALTER TABLE employees DROP COLUMN email;
  ALTER TABLE employees RENAME COLUMN salary TO base_salary;
  ALTER TABLE employees RENAME TO staff;
  ```

- **Database**
  ```sql
  ALTER DATABASE mydb SET timezone TO 'UTC';
  ```

#### 3. `DROP`

- **Database**
  ```sql
  DROP DATABASE mydb;
  ```

- **Table**
  ```sql
  DROP TABLE employees;
  ```

- **Index**
  ```sql
  DROP INDEX idx_employee_name;
  ```

- **Schema**
  ```sql
  DROP SCHEMA myschema CASCADE;
  ```

### Data Manipulation Language (DML) Commands

#### 1. `INSERT`

- **Single Row**
  ```sql
  INSERT INTO employees (name, position, salary) VALUES ('Alice', 'Manager', 75000);
  ```

- **Multiple Rows**
  ```sql
  INSERT INTO employees (name, position, salary) VALUES 
  ('Bob', 'Developer', 60000), 
  ('Carol', 'Analyst', 65000);
  ```

#### 2. `SELECT`

- **Basic Query**
  ```sql
  SELECT * FROM employees;
  ```

- **Specific Columns**
  ```sql
  SELECT name, salary FROM employees;
  ```

- **With Conditions**
  ```sql
  SELECT * FROM employees WHERE salary > 60000;
  ```

- **Ordering Results**
  ```sql
  SELECT * FROM employees ORDER BY salary DESC;
  ```

- **Limiting Results**
  ```sql
  SELECT * FROM employees LIMIT 5;
  ```

#### 3. `UPDATE`

- **Basic Update**
  ```sql
  UPDATE employees SET salary = salary * 1.1 WHERE position = 'Developer';
  ```

#### 4. `DELETE`

- **Delete Rows**
  ```sql
  DELETE FROM employees WHERE name = 'Alice';
  ```

### Transaction Control Commands

#### 1. `BEGIN`

- **Start Transaction**
  ```sql
  BEGIN;
  ```

#### 2. `COMMIT`

- **Commit Transaction**
  ```sql
  COMMIT;
  ```

#### 3. `ROLLBACK`

- **Rollback Transaction**
  ```sql
  ROLLBACK;
  ```

### Data Control Language (DCL) Commands

#### 1. `GRANT`

- **Grant Privileges**
  ```sql
  GRANT SELECT, INSERT ON employees TO myuser;
  ```

#### 2. `REVOKE`

- **Revoke Privileges**
  ```sql
  REVOKE INSERT ON employees FROM myuser;
  ```

### Utility Commands

#### 1. `EXPLAIN`

- **Show Query Plan**
  ```sql
  EXPLAIN SELECT * FROM employees WHERE salary > 60000;
  ```

#### 2. `ANALYZE`

- **Collect Statistics**
  ```sql
  ANALYZE employees;
  ```

#### 3. `VACUUM`

- **Reclaim Storage**
  ```sql
  VACUUM FULL employees;
  ```

### Advanced SQL Features in PostgreSQL

#### 1. Common Table Expressions (CTEs)

- **WITH Clause**
  ```sql
  WITH department_totals AS (
      SELECT department_id, SUM(salary) AS total_salary
      FROM employees
      GROUP BY department_id
  )
  SELECT * FROM department_totals;
  ```

#### 2. Window Functions

- **Ranking Employees**
  ```sql
  SELECT name, salary, RANK() OVER (ORDER BY salary DESC) AS rank
  FROM employees;
  ```

#### 3. Full-Text Search

- **Basic Search**
  ```sql
  SELECT * FROM documents WHERE to_tsvector(content) @@ to_tsquery('keyword');
  ```

#### 4. JSON Operations

- **Storing and Querying JSON Data**
  ```sql
  CREATE TABLE orders (
      id SERIAL PRIMARY KEY,
      order_info JSONB
  );

  INSERT INTO orders (order_info) VALUES ('{"customer": "John Doe", "items": ["item1", "item2"]}');
  
  SELECT order_info->>'customer' AS customer FROM orders;
  ```

---

### Write Amplification

**1. UNION**

The UNION operator is used to combine the result sets of two or more SELECT statements into a single result set.

**Syntax:**
```sql
SELECT column1 FROM table1
UNION
SELECT column2 FROM table2;
```

**Example:**
```sql
SELECT employee_name FROM employees
UNION
SELECT customer_name FROM customers;
```

**2. COALESCE**

The COALESCE function is used to return the first non-null expression among its arguments.

**Syntax:**
```sql
COALESCE(expression1, expression2, ...);
```

**Example:**
```sql
SELECT COALESCE(NULL, 'default value');
```

**3. NULLIF**

The NULLIF function is used to return null if the two expressions are equal; otherwise, it returns the first expression.

**Syntax:**
```sql
NULLIF(expression1, expression2);
```

**Example:**
```sql
SELECT NULLIF(10, 10);
```

### Index

**1. Multi index**

A multi-column index is an index on multiple columns in a table. It allows for efficient retrieval of data based on multiple criteria.

**Syntax (Creation):**
```sql
CREATE INDEX index_name ON table_name (column1, column2, ...);
```

**Example:**
```sql
CREATE INDEX idx_name_age ON employees (name, age);
```

**2. AUTO_INCREMENT**

AUTO_INCREMENT is a feature in some database systems that automatically generates a unique value for a column whenever a new row is inserted into a table.

**Syntax (Creation):**
```sql
CREATE TABLE table_name (
    id SERIAL PRIMARY KEY,
    column1 datatype,
    ...
);
```

**3. ON CONFLICT**

ON CONFLICT clause is used with INSERT statements to handle conflicts arising from unique constraints.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...)
ON CONFLICT (constraint_column)
DO NOTHING;
```

**Example:**
```sql
INSERT INTO employees (id, name)
VALUES (1, 'John')
ON CONFLICT (id)
DO NOTHING;
```

**4. Upserting**

Upserting is the process of updating a row if it exists, or inserting it if it doesn't.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...)
ON CONFLICT (constraint_column)
DO UPDATE SET column1 = value1, column2 = value2;
```

**Example:**
```sql
INSERT INTO employees (id, name)
VALUES (1, 'John')
ON CONFLICT (id)
DO UPDATE SET name = 'John';
```

**5. EXCLUDED**

The EXCLUDED table contains values for columns that would have been inserted had there been no conflict.

### Date Functions

**1. INTERVAL vs AGE**

- INTERVAL is used to perform date arithmetic and manipulate intervals (such as adding days or months to a date).
- AGE is used to calculate the difference between two dates and returns the result as an interval.

**Syntax (INTERVAL):**
```sql
SELECT current_date + INTERVAL '1 day';
```

**Syntax (AGE):**
```sql
SELECT AGE('2022-01-01', '2020-01-01');
```

### Aggregate Functions

**1. AVG, MIN, MAX, SUM, ROUND, COUNT, CONCAT**

- AVG: Calculates the average value of a set of values.
- MIN: Returns the minimum value in a set of values.
- MAX: Returns the maximum value in a set of values.
- SUM: Calculates the sum of a set of values.
- ROUND: Rounds a numeric value to a specified number of decimal places.
- COUNT: Returns the number of rows in a result set.
- CONCAT: Concatenates two or more strings.

**Syntax (Example):**
```sql
SELECT AVG(salary), MIN(salary), MAX(salary), SUM(salary), ROUND(salary, 2), COUNT(*), CONCAT(first_name, ' ', last_name)
FROM employees;
```

### Scalar Functions

**1. LCASE, CASE, LEN, MID, ROUND, NOW, FORMAT, INITCAP, LEFT, RIGHT, CONCAT, ABS, CEIL, FLOOR**

- LCASE: Converts a string to lowercase.
- CASE: Evaluates a set of conditions and returns a result.
- LEN: Returns the length of a string.
- MID: Returns a substring from a string.
- ROUND: Rounds a numeric value to a specified number of decimal places.
- NOW: Returns the current date and time.
- FORMAT: Formats a value based on a specified format pattern.
- INITCAP: Capitalizes the first letter of each word in a string.
- LEFT: Returns the leftmost characters of a string.
- RIGHT: Returns the rightmost characters of a string.
- CONCAT: Concatenates two or more strings.
- ABS: Returns the absolute value of a number.
- CEIL: Returns the smallest integer greater than or equal to a number.
- FLOOR: Returns the largest integer less than or equal to a number.

**Syntax (Example):**
```sql
SELECT LCASE('HELLO'), CASE WHEN age > 18 THEN 'Adult' ELSE 'Minor' END, LEN('hello'), MID('hello', 2, 3), ROUND(10.567, 2), NOW(), FORMAT(123456.789, 'C', 'en-us'), INITCAP('hello world'), LEFT('hello', 3), RIGHT('hello', 3), CONCAT(first_name, ' ', last_name), ABS(-10), CEIL(10.5), FLOOR(10.5)
FROM employees;
```

### Aggregate vs Scalar

Aggregate functions perform calculations on a set of values and return a single value, while scalar functions operate on individual values and return a single value. Aggregate functions are typically used with GROUP BY clauses to calculate summary statistics for groups of rows, while scalar functions are applied to individual rows or values.


---


Here's an explanation of each item related to SQL/psql views:

### Pros and Cons of Views

#### Pros:
1. **Data Abstraction**: Views can hide the complexity of underlying tables and provide a simplified view of the data to users.
2. **Security**: Views can restrict access to certain columns or rows, providing a level of security by limiting what data users can see.
3. **Performance**: Views can improve query performance by pre-computing complex joins or aggregations and storing them as a virtual table.
4. **Code Reusability**: Views allow commonly used queries to be encapsulated and reused across multiple parts of an application.
5. **Data Integrity**: Views can enforce business rules and constraints, ensuring that data is consistent and valid.

#### Cons:
1. **Resource Overhead**: Materialized views can consume storage space and computing resources, especially for large datasets or complex queries.
2. **Data Staleness**: Materialized views may become stale over time if not refreshed regularly, leading to outdated or incorrect results.
3. **Maintenance Overhead**: Views may require additional maintenance effort, especially if underlying table structures change frequently.
4. **Performance Overhead**: Certain operations on views, such as joins or aggregations, may incur performance overhead compared to querying raw tables directly.
5. **Complexity**: Views can introduce additional complexity to the database schema, making it harder to understand and maintain over time.

### CREATE VIEW

The CREATE VIEW statement is used to create a virtual table based on the result set of a SELECT query. Views can be used to simplify complex queries, enforce security policies, and provide a reusable abstraction layer over the underlying data.

**Syntax:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**Example:**
```sql
CREATE VIEW employee_view AS
SELECT emp_id, emp_name, department
FROM employees
WHERE department = 'IT';
```

### Materialized View

A materialized view is a type of database object that stores the result set of a query as a physical table. Unlike regular views, materialized views persist the data on disk, allowing for faster access and improved query performance. However, materialized views need to be refreshed periodically to ensure that they reflect the latest changes in the underlying data.

**Syntax (PostgreSQL):**
```sql
CREATE MATERIALIZED VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**Example:**
```sql
CREATE MATERIALIZED VIEW sales_summary AS
SELECT date_trunc('month', order_date) AS month,
       SUM(total_sales) AS total_sales
FROM orders
GROUP BY date_trunc('month', order_date);
```

Materialized views can be refreshed using the REFRESH MATERIALIZED VIEW statement:
```sql
REFRESH MATERIALIZED VIEW view_name;
```

Materialized views offer improved query performance for frequently accessed or computationally expensive queries, but they come with the trade-off of potentially stale data and additional maintenance overhead. Therefore, it's important to carefully consider the use cases and performance requirements before creating materialized views in a database.


---


Here's an explanation of each function mentioned:

### Functions

1. **SELECT**: Used to retrieve data from a database table.
   ```sql
   SELECT column1, column2 FROM table_name;
   ```

2. **LIMIT**: Limits the number of rows returned in a result set.
   ```sql
   SELECT column1, column2 FROM table_name LIMIT 10;
   ```

3. **FETCH**: Similar to LIMIT, but allows for more flexibility, especially when combined with OFFSET.
   ```sql
   FETCH 5 FROM cursor_name;
   ```

4. **OFFSET**: Specifies how many rows to skip before starting to return rows from the query.
   ```sql
   OFFSET 10;
   ```

5. **AS**: Renames a column or table with an alias.
   ```sql
   SELECT column_name AS alias_name FROM table_name;
   ```

6. **DISTINCT**: Filters duplicate rows from the result set.
   ```sql
   SELECT DISTINCT column1 FROM table_name;
   ```

7. **GROUP BY**: Groups rows that have the same values into summary rows.
   ```sql
   SELECT COUNT(*), column1 FROM table_name GROUP BY column1;
   ```

8. **HAVING**: Specifies a search condition for a group or an aggregate function.
   ```sql
   SELECT COUNT(*), column1 FROM table_name GROUP BY column1 HAVING COUNT(*) > 1;
   ```

9. **GROUPING SETS**: Provides a way to specify multiple grouping sets in the GROUP BY clause of a SELECT statement.
   ```sql
   SELECT column1, column2 FROM table_name GROUP BY GROUPING SETS ((column1), (column2));
   ```

10. **ROLLUP**: Generates subtotals for the data, along with the grand total.
    ```sql
    SELECT column1, column2, SUM(column3) FROM table_name GROUP BY ROLLUP (column1, column2);
    ```

11. **CUBE**: Generates all possible subtotals.
    ```sql
    SELECT column1, column2, SUM(column3) FROM table_name GROUP BY CUBE (column1, column2);
    ```

12. **Having vs Where**: WHERE is used to filter rows before any groupings are made, while HAVING is used to filter rows after the grouping has been done.
    
13. **Limit vs Fetch**: LIMIT is used to limit the number of rows returned, while FETCH is used to retrieve a specific number of rows.

14. **FROM**: Specifies the tables from which to retrieve data.
    ```sql
    SELECT column1 FROM table_name;
    ```

15. **WHERE**: Filters the rows based on specified conditions.
    ```sql
    SELECT column1 FROM table_name WHERE condition;
    ```

16. **AND, OR**: Logical operators used to combine multiple conditions.
    ```sql
    SELECT column1 FROM table_name WHERE condition1 AND condition2;
    ```

17. **LIKE, ILIKE**: Used to search for a specified pattern in a column.
    ```sql
    SELECT column1 FROM table_name WHERE column2 LIKE '%pattern%';
    ```

18. **BETWEEN**: Selects values within a range.
    ```sql
    SELECT column1 FROM table_name WHERE column2 BETWEEN value1 AND value2;
    ```

19. **IN**: Specifies multiple values for a column.
    ```sql
    SELECT column1 FROM table_name WHERE column2 IN (value1, value2, ...);
    ```

20. **IS NULL, IS NOT NULL**: Tests whether a column contains NULL values.
    ```sql
    SELECT column1 FROM table_name WHERE column2 IS NULL;
    ```

21. **ORDER BY**: Sorts the result set in ascending or descending order.
    ```sql
    SELECT column1 FROM table_name ORDER BY column2 DESC;
    ```

22. **DELETE**: Removes rows from a table based on specified conditions.
    ```sql
    DELETE FROM table_name WHERE condition;
    ```

23. **DELETING FOREIGN KEY**: Deleting a foreign key constraint from a table.
    ```sql
    ALTER TABLE table_name DROP CONSTRAINT constraint_name;
    ```

24. **CASCADE**: Specifies that the effect of a data modification also affects data with a related foreign key constraint.
    ```sql
    DELETE FROM table_name WHERE condition CASCADE;
    ```

25. **UPDATE**: Modifies existing records in a table.
    ```sql
    UPDATE table_name SET column1 = value1 WHERE condition;
    ```

26. **SET**: Assigns new values to columns in an UPDATE statement.
    ```sql
    UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
    ```

27. **RENAME COLUMN**: Renames a column in a table.
    ```sql
    ALTER TABLE table_name RENAME COLUMN old_column TO new_column;
    ```

28. **JOIN**: Combines records from two or more tables.
    - **INNER JOIN**: Returns records that have matching values in both tables.
    - **LEFT JOIN**: Returns all records from the left table, and the matched records from the right table.
    - **RIGHT JOIN**: Returns all records from the right table, and the matched records from the left table.
    - **FULL JOIN (FULL OUTER JOIN)**: Returns all records when there is a match in either left or right table.
    - **SELF JOIN**: Joins a table to itself.
    - **CROSS JOIN**: Returns the Cartesian product of the two tables.
    - **NATURAL JOIN**: Joins two tables based on the equality of all columns with the same name in both tables.
    ```sql
    SELECT * FROM table1 JOIN table2 ON table1.column = table2.column;
    ```

---

