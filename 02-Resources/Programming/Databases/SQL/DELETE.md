---
tags:
  - SQL
---
# DELETE
- Used to remove existing rows in a table
- The **DELETE** statement requires two values:
	1. The name of the table
	2. The condition that identifies the rows to be deleted.

>[! warning] All rows in a table are deleted if the [[WHERE]] clause is omitted

### Example
```SQL
DELETE from copy_employees
WHERE employee_id = 303;
```
> [! note] Delete one row with employee id 303


## Subquery Delete
- Can be used in **DELETE** statements.

### Example
```SQL
DELETE FROM copy_employees
WHERE department_id = (SELECT department_id
					   FROM departments
					   WHERE department_name = 'Shipping');
```
>[! note] Will delete rows of employees in the shipping department

```SQL
DELETE FROM copy_employees e
WHERE e.manager_id IN (SELECT d.manager_id
					   FROM employees d
					   HAVING count (d.department_id) < 2
					   GROUP BY d.manager_id)
```
> [! note] Deletes rows of all employees who work for a manager that manages less than 2 employees

