---
tags:
  - SQL
---
# All Operator
- Comapres a value to every value returned by the inner query


### Example
```SQL
SELECT last_name, hire_date
FROM employees
WHERE EXTRACT(YEAR FROM hire_date) < ALL
	(SELECT EXTRACT(YEAR FROM hire_date)
	 FROM employees
	 WHERE department_id = 90);
```
>[!note] No rows returned. No employees hired before 1987


