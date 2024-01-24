---
tags:
  - SQL
---
# READ ONLY
- Ensures no DML operations occur through the view.

### Example
```SQL
CREATE OR REPLACE VIEW view_dept50
AS SELECT department_id, employee_id, first_name, last_name, salary
	FROM employees
	WHERE department_id = 50
WITH READ ONLY;
```



