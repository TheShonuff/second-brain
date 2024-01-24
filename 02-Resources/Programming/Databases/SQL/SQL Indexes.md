---
tags:
  - SQL
---

---
Created: [[04-23-2023]]
tags: 
---
# SQL Indexes
- A schema object that can speed up the retrieval of rows by using a pointer.
	- Can be created explicitly or automatically
- Reduces the necessity of disk I/O by using an indexed path to locate data quickly.
- **ROWID** is a base 64 string representation of the row address containing:
	- Block indentifier
	- Row location in the block
	- Database file identifier.
- Indexes use **ROWID**'s because they are the fastest way to access any particular row.
- Indexes are logically and physically independent of the table they index.
	- They can be created or dropped with no effect to the table.

>[!tip] When you drop a table, corresponding indexes are also dropped.

- Two types of indexes can be created:
	- **Unique Index**: The Oracle Server automatically creates this index when you define a column in a table to have a [[PRIMARY KEY Constraints|PRIMARY KEY]] or a [[UNIQUE Constraint| UNIQUE KEY]] constraint.
		- The name of the index is the name given to the constraint.
		- It is recommended that you create a unique constraint in the table, which implicity creates a unqiue index.
	- **Nonunique Index**: An index that a user can create to speed up access to the rows.
		- To optimize joins, you can create an index on the FOREIGN KEY column, which speeds up the search to match rows in the PRIMARY KEY column.

- *An index should be created only if:*
	- The column contains a wide range of values
	- A column contains a large number of null values
	- One or more columns are frequently used together in a [[WHERE]] clause or a [[JOINs|JOIN]] condition
	- The table is large and most queries are expected to retrieve less than 2-4% of the rows.

>[!warning] You shouldn't use an index if the table requires DML operations. For each operation the indexes must be updated.

- *It is usually not worth creating an index if:*
	- The table is small
	- The columns are not often used as a condition in the query
	- Most queries are expected to retrieve more than 2-4% of the rows in the table
	- The table is updated frequently
	- The indexed columns are referenced as part of an expression

##  Syntax
```SQL
CREATE INDEX index_name
ON table_name (column..., column)
```

>[!warning] You must have the CREATE TABLE privilege

>[!warning] To create an index in any schema, you need the CREATE ANY INDEX privilege or the CREATE TABLE privilege on the table which you are creating the index.

>[!Warning] Null values are not included in the index.

### Example
```SQL
CREATE INDEX wf_cont_reg_id_idx
ON wf_countries(region_id)
```
>[!note] To improve speed of query access to the REGION_ID column in the WF_COUNTIRES table


