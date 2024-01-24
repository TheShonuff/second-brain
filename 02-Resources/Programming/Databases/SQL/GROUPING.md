---
tags:
  - SQL
---
# GROUPING
- When [[ROLLUP]] and [[CUBE]] is used to create reports with subtotals, it's hard to tell what's a calculated output versus an actual row from a table. 
- The GROUPING function handles this problem.

### Example
```SQL
SELECT department_id, job_id, SUM(salary)
	GROUPING(department_id) AS "Dept sub total",
	GROUPING(job_id) AS "JOb sub total"
FROM employess
WHERE department_id < 50
GROUP BY CUBE (department_id, job_id);
```



