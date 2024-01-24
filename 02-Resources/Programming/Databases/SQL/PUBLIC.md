---
tags:
  - SQL
---
# PUBLIC
- An owner of a table can grant access to all users by using the <code>PUBLIC</code> keyword.
- If a statement does not use the full name of an object, the Oracle server implicitly prefixes the object name with the current user's name (or schema)
- If a statement does not use the full name of an object, and the current user does not own an object of that name, the system prefixes the object name with <code>PUBLIC</code>

### Example
```SQL
GRANT select
	ON alice.departments
TO PUBLIC;
```



