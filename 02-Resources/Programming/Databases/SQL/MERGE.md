---
tags:
  - SQL
---
# MERGE
- Accomplishes two tasks at the same time.
- Will [[SQL INSERT|INSERT]] and [[UPDATE]] simultaneously.
- [[Aliases]] can be used with the **MERGE** statement

>[! tip] You'll need to have INSERT and UPDATE privileges on the target table and SELECT privileges on the source table

- One row at a time is read form the source table and compared to rows in the destination table using the matching condition
- If a matching row exists, the source row is used to update one or more columns in the matching destination row.
- If a match does not exist, values from the source row are used to insert a new row into the destination table.

## Syntax
```SQL
MERGE INTO destination_table USING source_table
	ON matching-condition
WHEN MATCHED THEN UPDATE
	SET ...
WHEN NOT MATCHED THEN INSERT
	VALUES (...);
```


### Example
```SQL
MERGE INTO copy_emp c USING employee e
	ON (c.employee_id = e.employee_id)
WHEN MATCHED THEN UPDATE
	SET c.last_name = e.last_name
		c.department_id =  e.department_id
WHEN NOT MATCHED THEN INSERT
	VALUES(e.employee_id, e.last_name, e.department_id);
```
>[!note] Uses employees table as a data source to insert and update rows in a copy of the table name copy_emp



