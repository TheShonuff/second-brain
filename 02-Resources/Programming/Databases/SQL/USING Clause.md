---
tags:
  - SQL
---
# USING Clause
- Specifies the columns that should be used for the join.
- The clause allows the use of [[WHERE]] to restrict rows from one or both tables
```SQL
SELECT first_name, last_name, department_id, department_name
FROM employees JOIN departments USING (department_id)
WHERE last_name = 'Higgins';
```

> [!warning] Use this clause only if the join columns in both table have the same name.

There are two situations where you **cannot** use this clause.
1. When the column names are not the same in the two tables
2. When you want to use the joining column

