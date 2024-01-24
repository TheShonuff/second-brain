---
tags:
  - SQL
---
# View DML Operations
- [[SQL INSERT|INSERT]], [[UPDATE]] and [[DELETE]] can be performed on [[Simple View]]
- Can be used to change the data in the underlying base tables.

>[!warning] If you create a view that allows users to view restricted information using the [[WHERE]] clause, users can still perform DML operations on all columns of the view.

- To control view data access, two options can be added to the CREATE VIEW statement
	- [[CHECK Option|WITH CHECK OPTION]] Ensures DML operations performed on the view stay within the domain of the view.
	- [[READ ONLY|WITH READ ONLY]]

## DML Restrictions
- [[Simple View|Simple]] and [[Complex View|Complex]] views differ in their ability to allow DML operations through a view.
- [[Simple View]] DML operations can be performed through the view
- [[Complex View]] DML operations are not always allowed.
- The following three rules must be considered when performing DML operations on views:
	1. *You cannot remoave a row from an underlying base table if the view contains any of the following:*
		- Group functions
		- A Group By clause
		- The DISTINCT keyword
		- The pseudocolumn ROWNUM keyword
	2. *You cannot modify data through a view if the view contains:*
		- Group functions
		- A Group BY clause
		- The DISTINCT keyword
		- The pseudocolumn ROWNUM keyword
		- Columns defined by expressions
	3. *You cannot add data through a view if the view:*
		- includes a group function
		- includes a GROUP BY clause
		- includes the DISTINCT keyword
		- includes the pseudocolumn ROWNUM keyword
		- includes columns defined by expressions
		- does not include NOT NULL columns in the base tables.

### Example
```SQL
CREATE VIEW view_dept50
AS SELECT department_id, employee_id, first_name, last_name, salary
FROM copy_employees
WHERE department_id = 50;
```
>[!note] Create a view for the managers of department 50. It's possible for managers to perform DML operations for all rows in the view, even if this results in a row no longer being part of the view.

```SQL
SELECT * FROM view_dept50
```



