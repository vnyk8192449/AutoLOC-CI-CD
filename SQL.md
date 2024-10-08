**SQL Concepts Revision Guide**

**1. Introduction to SQL**

- What is SQL?
- Importance of SQL in databases.
- SQL Standards (SQL-92, SQL-99, SQL-2003, etc.)

**2. SQL Basics**

- Data Definition Language (DDL)

  - `CREATE`: Used to create databases, tables, indexes, etc.
  - `DROP`: Removes databases or tables.
  - `ALTER`: Modifies table structure (add/remove columns).
  - `TRUNCATE`: Removes all records from a table but keeps the structure.

- Data Manipulation Language (DML)

  - `INSERT`: Add records to a table.
  - `SELECT`: Retrieve data from tables.
  - `UPDATE`: Modify existing records.
  - `DELETE`: Remove records from a table.

- Data Control Language (DCL)

  - `GRANT`: Give access privileges.
  - `REVOKE`: Remove access privileges.

- Transaction Control Language (TCL)
  - `COMMIT`: Save the changes.
  - `ROLLBACK`: Undo changes.
  - `SAVEPOINT`: Creates points within groups of transactions to roll back to.

---

**3. SQL Data Types**

- Numeric: `INT`, `FLOAT`, `DECIMAL`
- String: `CHAR`, `VARCHAR`, `TEXT`
- Date/Time: `DATE`, `TIME`, `TIMESTAMP`
- Boolean: `BOOLEAN`

---

**4. Constraints**

- `PRIMARY KEY`: Ensures uniqueness for each record.
- `FOREIGN KEY`: Ensures referential integrity between tables.
- `UNIQUE`: Ensures unique values in a column.
- `NOT NULL`: Ensures that a column cannot have `NULL` values.
- `CHECK`: Ensures that values satisfy a specific condition.
- `DEFAULT`: Assigns a default value if none is provided.

---

**5. SQL Joins**

- **Inner Join**: Returns records that have matching values in both tables.

  ```sql
  SELECT columns FROM table1 INNER JOIN table2 ON condition;
  ```

- **Left Join (Left Outer Join)**: Returns all records from the left table, and the matched records from the right table.

  ```sql
  SELECT columns FROM table1 LEFT JOIN table2 ON condition;
  ```

- **Right Join (Right Outer Join)**: Returns all records from the right table, and the matched records from the left table.

  ```sql
  SELECT columns FROM table1 RIGHT JOIN table2 ON condition;
  ```

- **Full Join (Full Outer Join)**: Returns all records when there is a match in either left or right table.
  ```sql
  SELECT columns FROM table1 FULL OUTER JOIN table2 ON condition;
  ```

---

**6. Aggregate Functions**

- `COUNT()`: Returns the number of rows.
- `SUM()`: Returns the total sum.
- `AVG()`: Returns the average value.
- `MAX()`: Returns the maximum value.
- `MIN()`: Returns the minimum value.

---

**7. Grouping and Filtering**

- `GROUP BY`: Groups rows that have the same values.

  ```sql
  SELECT column, COUNT(*) FROM table GROUP BY column;
  ```

- `HAVING`: Used to filter data after `GROUP BY`.
  ```sql
  SELECT column, COUNT(*) FROM table GROUP BY column HAVING COUNT(*) > value;
  ```

---

**8. Subqueries**

- **Single-row subquery**: Returns a single value.

  ```sql
  SELECT column FROM table WHERE column = (SELECT value FROM table2 WHERE condition);
  ```

- **Multi-row subquery**: Returns multiple values.
  ```sql
  SELECT column FROM table WHERE column IN (SELECT column FROM table2 WHERE condition);
  ```

---

**9. Indexes**

- **Creating Indexes**: Used to improve the speed of data retrieval.

  ```sql
  CREATE INDEX index_name ON table(column);
  ```

- **Dropping Indexes**: Removes an index.
  ```sql
  DROP INDEX index_name;
  ```

---

**10. Views**

- **Creating a View**: A virtual table based on the result of an SQL query.

  ```sql
  CREATE VIEW view_name AS SELECT column1, column2 FROM table WHERE condition;
  ```

- **Dropping a View**:
  ```sql
  DROP VIEW view_name;
  ```

---

**11. Normalization**

- 1NF (First Normal Form): Eliminate duplicate columns and ensure atomic values.
- 2NF (Second Normal Form): Remove partial dependency (no non-primary key should depend on part of a primary key).
- 3NF (Third Normal Form): Remove transitive dependency (non-primary key column depends on another non-primary key column).
- BCNF (Boyce-Codd Normal Form): A stricter version of 3NF.

---

**12. Transactions**

- Properties of Transactions (ACID):
  - **Atomicity**: All operations must succeed or fail as a unit.
  - **Consistency**: Transactions should move the database from one valid state to another.
  - **Isolation**: Operations of one transaction must be isolated from others.
  - **Durability**: Once committed, transactions should be permanent.

---

**13. SQL Functions**

- **String Functions**: `CONCAT()`, `LENGTH()`, `SUBSTRING()`, `UPPER()`, `LOWER()`
- **Date/Time Functions**: `NOW()`, `CURDATE()`, `DATEDIFF()`
- **Numeric Functions**: `ABS()`, `ROUND()`, `FLOOR()`, `CEIL()`

---

**14. Advanced SQL**

- **Stored Procedures**:

  ```sql
  CREATE PROCEDURE procedure_name()
  BEGIN
     -- SQL Statements
  END;
  ```

- **Triggers**:

  ```sql
  CREATE TRIGGER trigger_name BEFORE INSERT ON table_name FOR EACH ROW BEGIN -- logic END;
  ```

- **Functions**:

  ```sql
  CREATE FUNCTION function_name(parameters) RETURNS return_datatype
  BEGIN
     -- SQL logic
  END;
  ```

---
