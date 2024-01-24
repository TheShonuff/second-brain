---
tags:
  - SQL
---
# CHECK Option
- Ensures that DML operations performed on the view stay within the domain of the view.
- Any attempt to change data will fail

### Example
```SQL
CREATE OR REPLACE VIEW view_dept50
AS SELECT department_id, employee_id, first_name, last_name, salary
	FROM employees
	WHERE department_id = 50
WITH CHECK OPTION CONSTRAINT view_dept50_check;
```
>[!note] Adding a check option constraint to the view creation

```SQL
UPDATE view_dept50
SET department_id = 90
WHERE employee_id =124
```
>[!note] Attempting to [[UPDATE]] the view will result in a error *ORA-01402 view WITH CHECK OPTION where-clause violation*

