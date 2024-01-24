---
tags:
  - SQL
---
# CUBE
- Produces cross-tabulation reports.
- Can be applied to aggregate functions including:
	- AVG
	- SUM
	- MIN
	- MAX
	- COUNT
- Columns listed in the [[GROUP BY]] clause are cross-reference to create a superset of groups.
- Every possible combination of rows is aggregated by **CUBE**
- If you have n columns in the [[GROUP BY]] clause, there will be ***2n** possible super-aggregate combinations.*
>[! Tip] Often used in queries that use columns from seperate tables rather than separate columns from a single table.

> [!tip] A commonly requested cross-tabulation report might include subtotals for all possible cominations of sales across a Month, Region, and Product.

### Example
```SQL
SELECT department_id, job_id, SUM(salary)
FROM employees
WHERE department_id < 50
GROUP BY CUBE(department_id, job_id);
```

## Whats the difference?
The one major difference between [[ROLLUP]] and **CUBE** is [[ROLLUP]] operator generates aggregated results for the selected columns in a hierarchical way. **CUBE** generates a aggregated results that contains all the possible combinations for the selected columns.
[The Difference Between Cube and Rollup](https://www.sqlservercentral.com/articles/the-difference-between-rollup-and-cube)

## Which Should I use?
- [[ROLLUP]] if you wantr your data hierarchically.
- **CUBE** if you want all possible combinations.
