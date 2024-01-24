---
tags:
  - SQL
---

---
Created: [[05-01-2023]]
tags: 
---
# SQL Schema
- Is a collection of database objects.
- Owned by a database user
	- Has the same name as the db user.
- **Schema Objects** are logical structures created by users.
	- Tables
	- [[SQL Indexes|Indexes]]
	- [[Views]]
	- [[SQL SYNONYM|Synonoyms]]
	- [[Sequences]]
	- [[Database Links]]
	- Directory Objects
	- Reorganize Objects

>[!tip] Some of there object types can exist independently and others can not.

- Database objects taking up significant sorage space are know as segments
	- Tables and Indexes are examples of segements.
	- Values are stored in columns of each row take up significant physical disk space
- Views, Constraints, Sequences, and Synonyms the space they require is in the definition of the object.
	- None of these have any data rows associated with the,

- The database stores the definitions of all database objects in a **Data Dictionary**
- The **Data Dictionary** can be queried by all database users