---
tags:
  - SQL
---
# PRIMARY KEY Constraints
- A rules that the values in one column or combination of columns must uniquely identify each row in a table.
	- No primary-key value can appear in more than one row in the table.
- To satisfy a **PRIMARY KEY Constraint**:
	- No column that is part of the primary key can contain a null.
	- A table can have only one primary key
- These constraints at be defined at the **Table** or **Column** level.

>[!tip] The suffix **_pk** is typically used to identify a primary key constraint

```SQL
CREATE TABLE clients
(client_number NUMBER(4) CONSTRAINT clients_client_num_pk PRIMARY KEY,
 first_name VARCHAR2(14),
 last_name VARCHAR2(13));
```
>[!note] Column-level PRIMARY KEY constraint

```SQL
CREATE TABLE clients
(client_number NUMBER(4),
 first_name VARCHAR2(14),
 last_name VARCHAR2(13),
 CONSTRAINT clients_client_num_pk PRIMARY KEY (client_number));
```
>[!note] Table-level PRIMARY KEY constraint

>[!tip] Composite PRIMARY KEY must be defined at the table level rather than the column level

