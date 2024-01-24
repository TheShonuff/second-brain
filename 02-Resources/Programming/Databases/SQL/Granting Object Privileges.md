---
tags:
  - SQL
---

# Granting Object Privileges
- Guidlines:
	- To grant privileges on an object, the object must be in your own schema.
		- Or must have been granted the privilege using <code>WITH GRANT OPTION</code>
	- An object owned can grant any object privilege on the object to any other user or role of the database
	- The owner of an object automatically acquires all object privileges on that object.

## Syntax
```SQL
GRANT object_priv [(column list)]
	ON Object_name
TO {user|role|PUBLIC}
	[WITH GRANT OPTION]
```



