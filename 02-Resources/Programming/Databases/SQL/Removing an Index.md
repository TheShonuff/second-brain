---
tags:
  - SQL
---
# Removing an Index
- You cannot modify indexes.
- To change an index:
	- Drop the index
	- re-create the index.
- Remove an index definition from the data dictionary by issuesing the <code>DROP INDEX</code> statement

>[!warning] To drop an index, you must be the owner of the index or have **DROP ANY INDEX** privilege.

>[!warning] Constraints are automatically dropped but [[Views]] and [[Sequences]] remain

### Example
```SQL
DROP INDEX upper_last_name_idx
```



