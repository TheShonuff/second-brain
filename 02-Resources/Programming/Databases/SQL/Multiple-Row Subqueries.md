---
tags:
  - SQL
---
# Multiple-Row Subqueries
- Returns several rows
> [! tip] If in doubt, write a multiple-row subquery!
- Three comparison operators:
	- [[IN Operator|IN]] used within the outer query [[WHERE]] clause to select only those rows which are **IN** the list of values returned from the inner query.
	- [[ANY Operator|ANY]] used when we want the outer-query [[WHERE]] clause to select the roows which match the criteria of *at least* one value in the subquery result set.
	- [[All Operator|ALL]] used when we want the outer-query [[WHERE]] clause to select the rows which match the criteria (<,>,=,etc) of *all* of the values in the subquery result set.
> [! tip] The NOT operator can be used with any of these operators

## Null Values
- If one of the values returned by a multiple-row subquery is null, but other values are not.
	- If [[IN Operator|IN]] or [[ANY Operator|ANY]] are used, the outer query will return rows which mathc the non-null values.
	- if [[All Operator|ALL]] is used, the outer query returns no rows. [[All Operator|ALL]] compares the outer query row with every value returned by the subquery, including null.

## GROUP BY and HAVING
[[GROUP BY]] and [[HAVING]] clauses can be used with multiple-row subqueries.

### Example
```SQL
SELECT department_id, MIN(salary)
FROM employees
GROUP BY department_id
HAVING MIN(salary) < ANY
	(SELECT salary
	 FROM employees
	 WHERE department_id IN (10,20))
ORDER BY department_id;
```
>[!note] Returns the salaries of employees in department 10 and 20


## Multiple-Column Subqueries
- Subquries can use one or more columns.
- Can be either pair-wise comparison or non-pair-wise comparisons.

### Example
```SQL
SELECT employee_id, manager_id, department_id
FROM employees
WHERE(manager_id, department_id) IN
	(SELECT manager_id, department_id
	 FROM employees
	 WHERE   employee_id IN (149,174))
	 AND employee_id NOT IN (149,174);
```
> [!note] Multiple-column pair-wise subquery lists the employees whose manager and departments are the same as the manager and department of employees 149 or 174

```SQL
SELECT employee_id, manager_id, department_id
FROM employees
WHERE manager_id IN
	(SELECT manager_id
	 FROM employees
	 WHERE employee_id IN (149,174))
AND department_id IN
	(SELECT department_id
	 FROM employees
	 WHERE employee_id IN (149,174))
AND employee_id NOT IN (149,174);
```
>[! note] A multiple-column non-pair-wise subquery
