---
tags:
  - SQL
---

---
Created: [[02-07-2023]]
tags: 
---
# SQL Logical Operators
- A logical operator combines the results of two to more conditions to produce a single result.
- This logical operators are placed in the [[WHERE]] clause of the SQL statment.
	- **AND** Returns *TRUE* if both conditions are true
	- **OR** Returns *TRUE* if either condition is true
	- **NOT** Returns *TRUE* if the condition is false


### Examples
```SQL
SELECT last_name, department_id, salary
FROM employees
WHERE department_id > 50 AND salary > 12000;
```

```SQL
SELECT department_name, manager_id, location_id
FROM departments
WHERE location_id = 2500 OR manager_ud = 124;
```

```SQL
SELECT department_name, location_id
FROM departments
WHERE location_id NOT IN (1700, 1800);
```
