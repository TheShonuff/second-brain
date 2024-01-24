---
tags:
  - SQL
---
# TRUNCATE
- Removes all rows from a table and releases the storage space used by that table.
- When using the **TRUNCATE TABLE** statement:
	- You cannot roll back row removal
	- You must be the owner of the table or have been given DROP ANY TABLE system privileges.

>[!tip] A command to quickly remove all data from the rows in a table without deleting the table itself

## Syntax
```SQL
TRUNCATE TABLE tablename;
```

- The [[DELETE]] statement also removes rows from a table, but it does not release storage space
- **TRUNCATE** is faster than [[DELETE]] because it does not generate rollback information

