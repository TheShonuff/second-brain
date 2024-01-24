---
tags:
  - SQL
---
# Cartesian Product Join
- If two tables in a join query have no join condtion specified in the WHERE clause or the join condition is invalid, The Oracle Server returns the Catesian product of the two tables.
>[!warning] This is equivalent to the CROSS JOIN
- To avoid a Cartesian product, always include a valid join condition in a WHERE clause.
```SQL
SELECT employees.last_name, departments.department_name
FROM employees, departments;
```

#### Restricting Rows In a Join
- The WHERE clause can be used to restrict the rows considered in one ore more tables of the join.
```SQL
SELECT employees.last_name, employees.job_id, jobs.job_title
FROM employees, jobs
WHERE employees.job_id = jobs.job_id
	AND employees.department_id = 80;
```







