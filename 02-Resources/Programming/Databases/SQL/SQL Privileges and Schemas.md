---
tags:
  - SQL
---

---
Created: [[04-27-2023]]
tags: 
---
# SQL Privileges and Schemas
- Privileges are the right to execute particular SQL statements
- Users require system privileges to gain access to the database
- Users require object privileges to manipulate the content of the objects in a database.
- Users can be given privileges to grant other users privileges.
	- Called "groups of related privileges"

>[!tip] The DBA is a high-level users with the ability to grant acess

- The DBA users <code>GRANT</code> statement to allocate system privileges to a user.

## Syntax
```SQL
GRANT privilege [,privilege...]
TO USER [,user| role, PUBLIC...];
```

>[!warning] A user must have <code>CREATE SESSION</code> privilege and a user id if the user is to be able to access a database.


- A [[SQL Schema|schema]] is collection of objects, such as tables, views and sequences.
- The **schema** is owned by the database user and has the same name as that user.

## Confirming Privileges
- You can access the data dictionary to view the privileges that you have.

