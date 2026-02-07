
### ER Diagram
##### **Cardinality**:
- 1:1
- 1:N
- M:N
- In DBMS, **cardinality** refers to the uniqueness of data in a column (high/low) or the number of related records between tables ([one-to-one](https://www.google.com/search?q=one-to-one&oq=what+is+cardinality+in+dbms&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDc0OThqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&sei=U7dzafqDDIy64-EPxuaV4AQ&ved=2ahUKEwjGutKAn6KSAxWnzzgGHXlkD-gQgK4QegYIAAgAEAY), [one-to-many](https://www.google.com/search?q=one-to-many&oq=what+is+cardinality+in+dbms&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDc0OThqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&sei=U7dzafqDDIy64-EPxuaV4AQ&ved=2ahUKEwjGutKAn6KSAxWnzzgGHXlkD-gQgK4QegYIAAgAEAc), [many-to-many](https://www.google.com/search?q=many-to-many&oq=what+is+cardinality+in+dbms&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDc0OThqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&sei=U7dzafqDDIy64-EPxuaV4AQ&ved=2ahUKEwjGutKAn6KSAxWnzzgGHXlkD-gQgK4QegYIAAgAEAg)), defining how entities link and influencing database design for efficiency. It specifies how many instances of one entity can be associated with instances of another, like a single [customer](https://www.google.com/search?q=customer&oq=what+is+cardinality+in+dbms&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDc0OThqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&sei=U7dzafqDDIy64-EPxuaV4AQ&ved=2ahUKEwjGutKAn6KSAxWnzzgGHXlkD-gQgK4QegYIAAgAEAk) (one) having multiple [orders](https://www.google.com/search?q=orders&oq=what+is+cardinality+in+dbms&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDc0OThqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&sei=U7dzafqDDIy64-EPxuaV4AQ&ved=2ahUKEwjGutKAn6KSAxWnzzgGHXlkD-gQgK4QegYIAAgAEAo) (many).
##### Weak Entity
- No primary key of its own
- Depends on strong entity 
- Uses **partial key**

---
### Relational Model

##### Concepts
- **Relation** = Table
- **Tuple** = Row (eg. (1, John Doe, Software Engineer, 750000))
- **Attribute** = Column (eg. `Student`, `Employee`, or `Product`)
- **Domain** = Set of allowed values (eg. `Age` (integer between 18-65))
##### Keys
- Super key
- Candidate key
- Primary key
- Alternate key
- Foreign key
- Compound/Composite key

-------------------- **Super Key** --------------------
- A **set of one or more attributes** that can uniquely identify a record.
- May contain **extra attributes**.
**Example:**  
`{StudentID}`, `{StudentID, Name}`, `{StudentID, Email}`

-------------------- **Candidate Key** --------------------
- A **minimal super key**.
- No unnecessary attributes.
- A table can have **multiple candidate keys**.
**Example:**  
`StudentID` and `Email` both uniquely identify a student, so both are candidate keys

-------------------- **Primary Key** --------------------
- One **candidate key chosen** to uniquely identify records.
- **Cannot be NULL**
- **Must be unique**
- Only **one primary key per table**
**Example:**  
`StudentID`

-------------------- **Alternate Key** --------------------
- Candidate keys **not chosen** as the primary key.
- Still unique.
**Example:**  
If `StudentID` is primary key, then `Email` is an **alternate key**.

--------------------**Foreign Key** --------------------
- An attribute in one table that **refers to the primary key of another table**.
- Used to **maintain relationships** between tables.
- Can have duplicate values.
**Example:**  
`StudentID` in `Enrollment` table referring to `StudentID` in `Student` table.

-------------------- **Composite Key (Compound Key)** --------------------
- A key made of **two or more attributes**.
- Used when a single attribute is not enough.
**Example:**  
`{StudentID, CourseID}`  
(Used in enrollment tables)

---
### Relational Algebra (Procedural)

- Operations tell **how** to retrieve data.
- Relational Algebra in DBMS is a [procedural query language](https://www.google.com/search?q=procedural+query+language&oq=what+is+relational+algebra+in+dbm&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDYxODBqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjT18fJuqKSAxVTVmwGHT2mJEkQgK4QegYIAQgAEBE) that uses [operators](https://www.google.com/search?q=operators&oq=what+is+relational+algebra+in+dbm&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIHCAEQ6wcYQNIBCDYxODBqMGoxqAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjT18fJuqKSAxVTVmwGHT2mJEkQgK4QegYIAQgAEBI) (like Selection, Projection, Join, Union) to perform operations on tables (relations) and produce new relations as output, forming the mathematical foundation for SQL and enabling efficient data retrieval, filtering, and manipulation in databases
- **procedural** means -> You specify _how_ to get the data (the steps/operations), not just _what_ data you want.
- **Closure Property:** The output of one operation can be the input for another, allowing for complex query nesting.
#### Basic Operators
- **Selection (σ)**: Filters rows (tuples) from a relation based on a given condition (predicate) (**selects rows**).
- **Projection (π)**: Selects specific columns (attributes) from a relation, removing duplicates (**selects columns**).
- **Union (∪)**: Combines rows from two compatible relations, removing duplicates. (schema of 2 tables should be same).
<img src="../BIN/Pasted image 20260126230821.png">
- **Set difference (−)**: Returns rows present in the first relation but not in the second (must have same attributes/schema).
<img src="../BIN/Pasted image 20260126230913.png">
- **Cartesian product (×)**: Combines every row from one relation with every row from another.
<img src="../BIN/Pasted image 20260124014543.png">
#### Derived Operators
- **Intersection (∩)**: Returns rows common to both relations.
<img src="../BIN/Pasted image 20260126231127.png">
- **Rename (ρ)**: Renames attributes or relations.
- **Division (÷)**: Finding rows in one relation that match _every_ row in another. (used for "for all" type queries)
<img src="../BIN/Pasted image 20260124015032.png">
📌 **Division is used when query means**: "Find entities related to **all** entities in another set"

<img src="../BIN/dbms operators.jpg">

---
### Join (⨝)
A **JOIN** is used to **combine rows from two or more tables** based on a **related column** between them (usually a primary key and a foreign key).
[yt short for sql join](https://www.youtube.com/shorts/CQ52yLPTvIg)

<img src="../BIN/Pasted image 20260126193604.png">

>No. of attributes in result = Deg(table1) + Deg(table2)
>Degree (Deg): The degree of a table (or relation) refers to the total number >of attributes (columns) it contain.

**Types of Join's:**
- **Inner Join (equi join or simple join)**: Returns only the rows that have matching values in both tables.
```sql
SELECT * FROM Students INNER JOIN Enrollments
ON Students.student_id = Enrollments.student_id;

-- INNER JOIN and JOIN are the same
```
- **Left Join (left outer join)**: Returns all rows from the left table and matching rows from the right table, in short it keeps all the records/rows present in left table.
```sql
SELECT *
FROM Students
LEFT JOIN Enrollments
ON Students.student_id = Enrollments.student_id;
```
- **Right Join (right outer join)**: Just reverse of left join, it returns all the rows/records from the right table.
```sql
SELECT *
FROM Students
RIGHT JOIN Enrollments
ON Students.student_id = Enrollments.student_id;
```
- **Full Join (full outer join)**: Returns **all rows from both tables**. Matched rows are combined, unmatched rows show `NULL`.
```sql
SELECT *
FROM Students
FULL OUTER JOIN Enrollments
ON Students.student_id = Enrollments.student_id;

-- the below command is for Full Join in MySQL as it doesn't support the above command
SELECT * FROM table1 LEFT JOIN table2 ON table1.column = table2.column
UNION
SELECT * FROM table1 RIGHT JOIN table2 ON table1.column = table2.column;
```
- **Self Join**: A self join in SQL is a regular join where a table is joined with itself. This technique is used to compare rows within the same table or to query hierarchical data (e.g., employee-manager relationships).
```sql
SELECT e1.name AS Employee, e2.name AS Manager
FROM Employees e1
LEFT JOIN Employees e2
ON e1.manager_id = e2.emp_id;
```

---

## Tuple Relational Calculus (non-procedural language)

Tuple calculus is used to retrieve data by specifying the logical conditions that the desired data must satisfy, rather than the explicit steps on _how_ to retrieve it.

```
{ t | t ∈ STUDENT ∧ t.dept = "CSE" }
{ t | Employees(t) ∧ t.Salary > 50000 }
```

**Components of tuple calculus:**
- Tuple variable (t): Represents a **row (tuple)** in a relation.
- Predicate (condition)
	- A logical expression involving:
		- Comparison operators: `=, ≠, <, >, ≤, ≥`
		- Logical operators: `∧ (AND), ∨ (OR), ¬ (NOT)`
		- Quantifiers: `∃ (exists), ∀ (for all)`

---

## SQL

##### Categories
- **DDL (Data Definition Language)**: Used to define and modify database structure.
	- CREATE, DROP, ALTER
	- 'create' -> create table
	- 'drop' -> delete table, cannot be rolled back
	- 'alter' -> modifies an existing table, eg. adding attribute, deleting attribute
- **DML (Data Mainpulation Language**: Used to manipulate data in tables.
	- INSERT, UPDATE, DELETE
	- 'insert' -> adding new records/tuples
	- 'update' -> modify existing records
	- 'delete' -> delete records
- **DQL (Data Query Language)**: Used to retrieve data.
	- SELECT
- **DCL (Data Control Language)**: Used to control user access.
	- GRANT -> give permission
	- REVOKE -> removed permission
- **TCL  (Transaction Control Language)**: Used to manage transactions.
	- COMMIT -> saves changes permanently
	- ROLLBACK -> undo changes 
	- SAVEPOINT -> creates a point to rollback to

#### SQL Clauses
- HAVING
- WHERE
- GROUP BY
- ORDER BY
##### HAVING Clause vs WHERE Clause
```sql
SELECT dept, AVG(salary)
FROM Employee
WHERE salary > 30000
GROUP BY dept
HAVING AVG(salary) > 50000;
```

| Feature             | WHERE                  | HAVING             |
| ------------------- | ---------------------- | ------------------ |
| Filters             | Rows                   | Groups             |
| Used with           | SELECT, UPDATE, DELETE | GROUP BY           |
| Works on            | Individual rows        | Aggregated results |
| Aggregate functions | ❌ Not allowed          | ✅ Allowed          |
##### GROUP BY Clause
```sql
SELECT dept, COUNT(*) FROM Employee GROUP BY dept;
```

<img src="../BIN/Pasted image 20260127010950.png">

##### ORDER BY Clause
- Used to **sort the result set**.
- Default order is `ASC`
- Can sort by column name, alias, or position

> Without `ORDER BY`, **row order is NOT guaranteed**.

```sql
SELECT * FROM Employee ORDER BY salary DESC, name ASC;

SELECT * FROM Employee ORDER BY 2 DESC   -- second selected column`
```

#### Aggregate Functions
Used to perform calculations on a set of values

| Function | Purpose        |
| -------- | -------------- |
| COUNT()  | Number of rows |
| SUM()    | Total          |
| AVG()    | Average        |
| MIN()    | Minimum        |
| MAX()    | Maximum        |

```sql
SELECT COUNT(*), AVG(salary) FROM Employee;
```

>`COUNT(*)` in SQL means **“count how many rows are in the result set.”**, it returns the integer count of the rows

*Aggregate functions ignore NULL values (except `COUNT(*)`)*

#### SQL Execution Order
```
FROM
WHERE
GROUP BY
HAVING
SELECT
ORDER BY
```

#### Operators used in sub query
- IN
- ANY
- ALL
- EXISTS
##### IN
Checks if a value matches **any value** in a list or subquery
```sql
-- True if `dept_id` matches at least one returned value from sub query.
SELECT * FROM Employee WHERE dept_id IN (SELECT id FROM Department);
```
##### EXISTS
- Checks whether the subquery returns **at least one row**
- Often faster than `IN` for large datasets
- Ignores actual values — only cares if rows exist

```sql
-- Returns TRUE as soon as **one row exists**

SELECT * FROM Department d WHERE EXISTS (   
	SELECT 1 FROM Employee e WHERE e.dept_id = d.id
);
```
##### ANY
- Compares a value to **any one** value returned by a subquery
- Think: **OR logic**
```sql
-- True if salary is greater than **at least one** salary in dept 10  

SELECT * FROM Employee WHERE salary > ANY (   SELECT salary FROM Employee WHERE dept_id = 10 );
```
##### ALL
- Compares a value to **every** value returned by a subquery
- Think: **AND logic**
```sql
-- True only if salary is greater than **every** salary in dept 10  

SELECT * FROM Employee WHERE salary > ALL (   SELECT salary FROM Employee WHERE dept_id = 10 );
```

#### Set Operators
Set operators are used to combine results of two or more **SELECT** statements
eg. `(SELECT * FROM <table 1>) <set operator> (SELECT * FROM <table 2)`
- UNION -> duplicate rows are eliminated
- UNION ALL -> duplicate rows are retained
- INTERSECT -> selects only common rows
- EXCEPT/MINUS -> set difference

#### Sub query / Nested query
Query written in SQL query that is embedded within the **WHERE** clause

---

## Integrity Constraints
Rules that maintain correctness.
#### Types
- **Domain constraint**: Data type
- **Key constraint**: Unique primary key
- **Entity integrity**: PK ≠ NULL
- **Referential integrity**: FK must reference valid PK
- **General constraints**: CHECK, ASSERTION

---

## Normalization
Normalization protects the database from redundancy.
Process of grouping attributes into well structured relations that contain minimal redundancy.

#### Functional Dependency
```
FD: x -> y
if t1.x == t2.x
then t1.y == t2.y (this should be true)

X and Y are set of attributes (can contain one or more attributes)

eg.
Roll no. -> Name
(Dept., Course) -> Name
(Dept., Course) -> (Roll no., Name)
```

#### Closure Set of Attrbute
- closure of attribute (or set of attribute) is the **set of all attributes that can be functionally determined** from it using given **functional dependencies**.
- *X+ = (contains set of attributes determined by X)*
```
R(A B C D E F)

-- FD's --
AB -> C
DC -> AE
E -> F
B -> D

-- closures --
A+ = {A}
AB+ = {A, B, C, D, E, F}

Here AB is a super key as well as candidate key,
super key -> attribute or set of attribute that can determine all the attributes in a relation
```

**Normalized tables are:**
- Easier to understand
	- Easier to enhance and extend
- Protected from:
	- Insertion [^1]anomalies
	- Update anomalies
	- Deletion anomalies

>anomalies -> when there is duplicate values in table and we want to update that value, so when we update at one place and forget to update that value at another place then it leads to inconsistent values, for this we have to apply normalization in 
##### 1NF
Each column in a table should contain individual values
- write values in column individually/separately
- Every attribute must be atomic
##### 2NF -> removing partial dependency
All non-key attributes should be fully dependent on the primary key (no partial dependencies)
- make a separate table for multiple value attribute with foreign key as primary key of first table (first table should contain only unique values)
- This concept matters **only when the primary key has more than one column**.  (meaning primary key -> AB (A,B are attributes))
##### 3NF -> removing transitive dependency
- No Transitive Dependency. (A -> B -> C)
- No non-prime attribute should determine non-prime attribute (X -> Y, where X is non-prime attribute)
##### BCNF (Boyce-Codd Normal Form)
- L.H.S must be candidate key or super key.
- In other words attribute in R.H.S of functional dependency should only be determined by candidate key or super key.
- X -> Y, where X should be candidate key or super key
##### 4NF -> removing multivalued dependency
- No multivalued dependency
>A ->> B
>A multivalued dependency occurs when there are 2 values of B for the same value of A attribute.
>Ex. A1 -> B1, A1 -> B2

**Example Table**

| SID | course  | hobby   |
| --- | ------- | ------- |
| 1   | science | running |
| 1   | math    | reading |
| 1   | science | reading |
| 1   | math    | running |
For, student 1 there are multiple entries of course and hobby, even if there is not relation between course and hobby.
*Note: for multivalued dependency, there should be at-least 3 columns in a table*
##### 5NF -> removing join dependency
- It should not have Join dependency
- Lossless Decomposition should be there
- 5NF is also known has PJNF (Project Join Normal Form)

>A lossless decomposition is a process of decomposing a relation schema into multiple relations in such a way that it preserves the information contained in the original relation.
>
>Lossy decomposition in (DBMS) is when a table (relation) is split into smaller tables, but joining them back together doesn't perfectly recreate the original table, resulting in extra, "extraneous tuples" or lost information, often due to missing common keys or poor splitting.
>
> Decomposition: In **DBMS**, **decomposing a table** means **splitting one table into two or more smaller tables** in a structured way, **without losing information**, to make the database better designed.


[^1]: Anomalies -> when there is duplicate values in table and we want to update that value, so when we update at one place and forget to update that value at another place then it leads to inconsistent values, for this we have to apply normalization in

---

## File Organization

- Heap
- Sequential
- Hash (using hash function)
- Indexed (B tree, B+ tree)
- Clustered

---

## Indexing

**Below table shows which indexing to use at what situation

|                    | Key             | Non key         |
| ------------------ | --------------- | --------------- |
| **Ordered file**   | Primary Index   | Clustered Index |
| **Unordered file** | Secondary Index | Secondary Index |
