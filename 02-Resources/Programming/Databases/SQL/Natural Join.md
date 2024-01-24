---
tags:
  - SQL
---
# Natural Join
- A natural join is based on all columns in two tables that have the same name and select rows from the two tables that have equal values in all matched columns.

```SQL
SELECT first_name, last_name, job_id, job_title
FROM employees NATURAL JOIN jobs
WHERE department_id > 80;
```
> [!note] This join will return all columns from the employees table and their related job_title from the jobs table based on the common column job_id.

```SQL 
SELECT deparment_name, city 
FROM departments NATURAL JOIN locations;
```

> [! tip] This JOIN will drastically simplify some queries that require specific matched columns. Where this query will automatically join matching columns




