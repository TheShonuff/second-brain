---
tags:
  - SQL
---
# ANY Operator
- 



### Example
```SQL
SELECT last_name, hire_date
FROM employees
WHERE EXTRACT(YEAR FROM hire_date) < ANY
	(SELECT EXTRACT(YEAR FROM hire_date)
	 FROM employees
	 WHERE department_id = 90);
```
>[!note] Returns any employee whose year hired is less than at least one year hired of employees in department 90

