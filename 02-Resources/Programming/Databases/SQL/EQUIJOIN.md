---
tags:
  - SQL
---
# EQUIJOIN
- A **simple** or [[Inner Join]].
- A table join that combine rows that have the same values for the specified columns.
- The equavalent ANSI:
	- NATURAL JOIN
	- JOIN USING
	- JOIN ON
#### The Basics
- **What** The select clause the specifies the column names to display
- **Where** The FROM clause specifies the tables the database must access
- **How** The WHERE cluase specifies how the tables are to be joined
>[!note] An Equijoin uses the equals operators to specify the join condition
>

```SQL
SELECT employees.last_name, employess.job_id, jobs.job_title
FROM employess, jobs
WHERE employees.jobs_id = jobs.job_id;
```

```SQL
SELECT employees.last_name, departments.department_name
FROM employees, departments
WHERE employees.department_id = departments.department_id;
```

 



