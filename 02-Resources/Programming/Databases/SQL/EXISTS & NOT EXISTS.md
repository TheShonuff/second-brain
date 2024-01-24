---
tags:
  - SQL
---
# EXISTS & NOT EXISTS
- Tests for a **True**, or a matching result in the subquery
- Can return three values:
	- TRUE
	- FALSE
	- UNKNOWN
- A NULL in the subquery result will return an UNKNOWN.

### Example
```SQL
SELECT last_name AS "Not a Manager"
FROM employees emp
WHERE NOT EXISTS
	(SELECT *
	 FROM employees mgr
	 WHERE mgr.manager_id = emp.employee_id);
```
>[!note] Returns employees that are managers



