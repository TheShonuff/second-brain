---
tags:
  - SQL
---

# GROUPING SETS
- Gives the functionality of having multiple [[GROUP BY]] clauses in the same SELECT statement, which is not allowed in the normal syntax.

### Example
```SQL
SELECT department_id, job_id, manager_id, SUM(salary)
FROM employees
WHERE department_id < 50
GROUP BY GROUPING SETS
((job_id, manager_id), (department_id, job_id), (department_id, manager_id))
```

