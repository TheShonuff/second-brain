---
tags:
  - SQL
---

# IN Operator




### Example
```SQL
SELECT last_name, hire_date
FROM employees
WHERE EXTRACT(YEAR FROM hire_date) IN
	(SELECT EXTRACT(YEAR FROM hire_date)
	 FROM employees
	 WHERE department_id = 90);
```
> [!note] Employees that were hired the same year as an employee in department 90

```SQL
SELECT last_name
FROM employees
WHERE salary IN 
	(SELECT MIN(Salary) FROM employees GROUP BY department_id);
```
> [!note] Returns the last names of all employees whose salaries are the same as the minimum salary for any department

