---
tags:
  - SQL
---
# Data Dictionary
- Often called *metadata*
- Consists of two levels:
	- **Internal Level** contains all base tables that are used by the various DBMS software components and they are normally not accessible by end users.
	- **External Level** provides numerous views on these base tables to access information about objects and structures at different levels of detail.
- A **Data Dictionary** contains:
	- users and [[SQL Privileges and Schemas|pivileges]]
	- Names of [[SQL Schema|Schema Objects]]
		- Tables
		- [[Views]]
		- [[SQL Indexes|Indexes]]
		- [[SQL SYNONYM|Synonyms]]
		- [[Sequences]]
		- [[SQL Functions|Functions]]
		- [[SQL Data Types|Data types]]
	- Information about [[SQL Constraints|Integrity Constraints]]
	- Stastistics about tables and indexes used by the multiplexer
	- [[SQL Privileges and Schemas|Privileges]] granted on database objects
	- Storage structurs of the databse
		- How much space has been allocated and is currently used by the objects

### Viewing The Data Dictionary
For a [[Data Dictionary Views|full list of views]]
```SQL
SELECT * FROM DICT
```
>[!note] Lists all tables and views of the data dictionary accessible to the user.

```SQL
SELECT * FROM TAB
```
>[!note] Retrieves the names of all tables owned by the user who issues the command.

- All owned by a special Oracle user called SYS and only SELECT statement should be used when working with any of these tables
- To makes these tables safe from accidental user access, they all have views created through which the data dictionary is accessed by database users.
- When you are using the Data Dictionary views in SQL Commands Interface, you need to know the names of the Dictionary views you are working with.

```SQL
SELECT table_name, status
FROM USER_TABLES
```

```SQL
SELECT table_name, status
FROM ALL_TABLES
```


