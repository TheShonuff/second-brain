---
tags:
  - SQL
---

# Set Operators
- Used to combine the results from different SELECT statement into one single result output.

## Rules
- The number of columns and the data types of the columns must be identical in all of the SELECT statements used in the query.
- The names of the columns need not be identical
- Column names in the output are taken from the column names in the first SELECT statement.

>[! tip] Any column aliases should be entered in the first statement


- **[[UNION]]** Returns all rows from both tables after eliminating duplicates.
- **[[UNION ALL]]** Returns all rows from both tables, without eliminating duplicates.
- **[[INTERSECT]]** Returns all rows common to both tables
- **[[MINUS]]** Returns all rows found in one table but not the other


### Example
```SQL
SELECT hire_date, employee_id, job_id
FROM employees
	UNION
SELECT TO_DATE(NULL), employee_id, job_id
FROM job_history;
```

- You can control the order of the returned rows when using **SET** operators using the [[ORDER BY]] statement. *It can only be used once in the last statment.*

### Example
```SQL
SELECT hire_date, employee_id, job_id
FROM employees
	UNION
SELECT TO_DATE(NULL), employee_id, job_id
FROM job_history
ORDER BY employee_id;
```