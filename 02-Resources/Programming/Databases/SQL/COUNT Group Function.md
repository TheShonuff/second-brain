---
tags:
  - SQL
---

---
Created: [[03-06-2023]]
tags: 
---
# COUNT Group Function
- Returns the number of non-null values in the expression column
- To count all rows use COUNT(\*) *including duplicates*
```SQL
SELECT COUNT(*)
FROM employees
WHERE hire_date < '01-Jan-1996';
```

- The [[DISTINCT|DISTINCT]] keyword can be used to return only non-duplicated values or combinations of non-duplicate values in a query. 

### Examples

```SQL
SELECT COUNT (DISTINCT job_id)
FROM employees;
```

```SQL
SELECT COUNT (DISTINCT salary)
FROM employees;
```

- Sometimes it is desirable to include null values in a group functions.[[GitHub CoPilot NVIM]]