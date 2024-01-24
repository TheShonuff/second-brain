---
tags:
  - SQL
---

---
Created: [[03-24-2023]]
tags: 
---
# Correlate Subqueries
- Oracle server performs a correlated subquery when the subquery references a column from a table referred to in the parent statement.
- Evaluated once for each row processed by the parent statement.
- The parent statement can be a [[SELECT]], [[SQL UPDATE|UPDATE]], or [[SQL DELETE|DELETE]] statement

### Example
```SQL
SELECT o.first_name, o.last_name, o.salary
FROM employees o
WHERE o.salary > 
	(SELECT AVG(i.salary)
	 FROM employees i
	 WHERE i.department_id = o.department_id);
```
> [!note] Returns whose salary is higher than the average salary of their department


# WITH
- Oracle allows you to write named subqueries in one single statement, as long as you start the statement with the keyword WITH.
- Retrieves the results of one or more query blocks and stores those results for the user who runs the query.
- Makes queries easier to read.

## Syntax
```SQL
WITH subquery-name AS (subquery), subquery-name AS (subquery)
	SELECT column-list
	FROM (table | subquery-name | view) WHERE condition is true.
```

### Examples
```SQL
WITH managers AS 
	(SELECT DISTINCT manager_id
	 FROM employees
	 WHERE manager_id iS NOT NULL)
SELECT last_name AS "Not a manager"
FROM employees
WHERE employee_id NOT IN
	(SELECT * 
	 FROM managers);
```
> [! note] List of employees that are not managers

```SQL
SELECT oe.last_name, oe.department_id, oe.salary
FROM employees oe
WHERE oe.salary = 
	(SELECT MAX(ie.salary) 
	 FROM employees ie 
	 WHERE NVL(ie.department_id,-1) = NVL(oe.department_id,-1));
```
> [! note] Returns the highest earners for each department.

