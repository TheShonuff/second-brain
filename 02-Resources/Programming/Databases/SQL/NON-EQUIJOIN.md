---
tags:
  - SQL
---
# NON-EQUIJOIN
- Used to match table column that are that do not have corresponding names.
>[!note] Since there is no exact match between the two columns in each table, the equality operator = can't be used.
- [[BETWEEN...AND]] is an effective way to execute a nonequijoin
- This join is equivalent to **ANSI** JOIN [[ON Clause|ON]]
	- The condition used is something other than equals.

### Example
```SQL
SELECT last_name, salary, grade_level, lowest_sal, highest_sal
FROM employees, job_grades
WHERE (salary BETWEEN lowest_sal AND highest_sal);
```


## Outer Join
- Used to see rows that have corresonding value in another table plus those rows in one of the tables that no matching value in the other table.
- To indicate which table may have missing data using Oracle Join Syntax
	- Add a plus sign **(+)**
	- After the table's column name in the WHERE clause
```SQL
SELECT e.last_name, d.department_id, d.department_name
FROM employees e, departments d
WHERE e.department_id = d.dpartment_id(+);
```
>[!note] The same results can be obtained using a [[Left Join|LEFT OUTER JOIN]]

```SQL
```SQL
SELECT e.last_name, d.department_id, d.department_name
FROM employees e, departments d
WHERE e.department_id(+) = d.dpartment_id;
```
>[!note] The same results can be obtained using [[Right Join|RIGHT OUTER JOIN]]

> [!Tip]  It's not possible to have the equivalent of a [[Full Join|FULL OUTER JOIN]] by adding a **(+)** to both columns in the join condition

