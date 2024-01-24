---
tags:
  - SQL
---

# Function-based Indexes
- Stores the indexed values and uses the index based on a SELECT statement to retreive the data.
- An index based on expressions.
- Built from table columns, constants, SQL functions and user-defintions
- To ensure that the Oralce Server uses the index rather than performing a full table scan, be sure that the value of the function is not null in subsequent queries.

>[!tip] Useful for when you don't know in what case the data was stored in the database.

>[!tip] Oracle Server treats indexes with columns marked DESC as function-based indexes

### Example
```SQL
CREATE INDEX upper_last_name_idx
ON employees(UPPER(last_name));
```
>[!note] Function-based index that can be used with a SELECT statement using UPPER and WHERE clause

```SQL
SELECT *
FROM employees
WHERE UPPER(last_name) = 'KING'
```


```SQL
SELECT *
FROM employees
WHERE UPPER(last_name) IS NOT NULL
ORDER BY UPPER(last_name)
```
>[!note] Guaranteed to use the index, but without the WHERE clause the Oracle Server may perform a full table scan.

```SQL
SELECT first_name, last_name, hire_date
FROM employees
WHERE TO_CHAR(hire_date, 'yyyy') = '1987'
```
>[!note] Function-based index to find employees hired in 1987. This query is a **Full table scan** which can be an expensive operation.

```SQL
CREATE INDEX emp_hire_year_idx
FROM employees (TO_CHAR(hire_date, 'yyyy'));
```
>[!note] To make the above query better we can create an index to avoid the full table scan.


