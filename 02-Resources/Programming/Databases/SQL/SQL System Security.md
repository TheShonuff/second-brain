---
tags:
  - SQL
---

---
Created: [[04-27-2023]]
tags: 
---
# SQL System Security

## Object Security
- This level of security covers access and use of the database objects and the actions users can have on those objects.
- Each object has a particular set of grantable privileges.
- It's important to note the following four points regarding object privileges:
	- The only privileges that apply to a sequence are <code>SELECT</code> and <code>ALTER</code>
	- Remeber, a sequence users <code>ALTER</code> to change the <code>INCREMENT</code>, <code>MAXVALUE</code>, <code>CAHCE/NOCACHE</code>, or <code>CYCLE/NOCYCLE</code> options
	- <code>START WITH</code> cannot be changed using <code>ALTER</code>
- You can grant <code>UPDATE</code>, <code>REFERENCES</code>, and <code>INSERT</code> privileges on individual columns in a table.
```SQL
GRANT UPDATE (salary)
	ON employees TO steven_king
```
- A <code>SELECT</code> privilege can be restricted by creating a view with a subset of columns and granting the <code>SELECT</code> privilege only on the view.

>[! warning] You can't grant <code>SELECT</code> on indiviudal columns

- A privilege granted on a synonym is converted to a privilege on the base table referenced by the synonym.
	- Simply a synonym is a new, easier-to-use name.


### Examples
```SQL
CREATE USER scott INDENTIFIED BY tiger
```
>[!note] Create user for database with password tiger

```SQL
GRANT SELECT, UPDATE
	ON d_clients TO scott
```
>[!note] Grant SELECT and UPDATE privileges to scott on d_clients table.

