---
tags:
  - SQL
---

---
Created: [[04-27-2023]]
tags: 
---
# SQL Roles
- A named group of related privileges that can be granted to a user.
- A role is created by a user to grant privileges.
- A user can have access to several roles
- To creat and assign a role, the DBA must create the role.
	- Then the DBA can assign privileges to the role and users.
- After the role is created, the DBA can use the <code>GRANT</code> statement to assign the role to users as well as assign privileges.

## Syntax
```SQL
Create ROLE role_name
```


### Examples
```SQL
CREATE ROLE manager;

GRANT create table, create view TO manager;

GRANT SELECT, UPDATE, DELETE ON employees TO manager

GRANT manager TO jennifer_cho;
```
>[!note] Create manager role, create privileges and assign role

```SQL
REVOKE DELETE ON employees FROM manager
```
>[!note] Revokes the delete privilege from the manager on the employees table. 



