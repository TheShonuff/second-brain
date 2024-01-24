---
tags:
  - SQL
---
# ROLLUP
- A subset of [[CUBE]] n+1 levels of subtotal.
- Creates subtotals that roll up the most detailed level to a grand total, using the gouping listed specified in [[GROUP BY]] clause
- Uses an ordered list of grouping columns in its argument list
	- First, it calculates the standard aggregate values
	- Next, it creates a progressively higher-level subtotals, moving from right to left through the list of grouping columns
	- Finally, creates a grand total

### Example
```SQL
SELECT department_id, job_id, SUM(salary)
FROM employees
WHERE department_id < 50
GROUP BY ROLLUP (department_id, job_id);
```

> [!tip] The number of columns or expressions that appear in the **ROLLUP** argument list determines the number of groupings.

- The formula is (number of columns) + 1
- The above example would generate 3 values

### Example
```SQL
SELECT manager_id, job_id, SUM(salary),
GROUPING(manager_id), GROUPING(job_id)
FROM employees
GROUP BY ROLLUP (manager_id, job_id);
```
>[!note] For each manager, the total salary earned by all employees within each job_id

