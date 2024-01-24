---
tags:
  - SQL
---
# ALTER TABLE
- User the <code>ALTER TABLE</code> statement to alter the definition of a table.
- **Prerequistes**:
	- The table must be in your [[SQL Schema|Schema]]
		- Or have <code>ALTER</code> [[SQL Privileges and Schemas|Privilege]]
		- Or have <code>ALTER ANY TABLE</code> [[SQL Privileges and Schemas|Privilege]]
- Statements are used to:
	- [[ALTER TABLE ADD|Add]] a new column
	- [[MODIFY Table|Modify]] an existing column
	- Define a DEFAULT value for a column
	- [[DROP COLUMN|Drop]] a column

>[!tip] You can add or modify a column in a table, but you cannot specify where the column appears.

- A newly added column always becomes the last column of the table
- If the table already has rows of data and a column is added to the table the new column is initially null for all of the pre-existing rows.




## Syntax
```SQL
ALTER TABLE <table_name> action;
```



### Example
```SQL
ALTER TABLE my_cd_collection
ADD (release_date DATE DEFAULT SYSDATE);
```




