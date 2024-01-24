---
tags:
  - SQL
---
# CREATE TABLE
- This statement creates a table that contains columns, rows and constraints.
- Must have CREATE TABLE privilege.
	- Granted through the DATA CONTROL LANGUAGE (DCL)
- Tables belonging to other users are not in your schema
- If you want to use a table that is not in your schema, use the table owner's name as the prefix to the table name.

## Syntax
```SQL
CREATE TABLE table
(column data type [DEFAULT expression])
```

### Example
```SQL
CREATE TABLE my_cd_collection
(cd_number NUMBER(3),
 title VARCHAR2(20),
 artist VARCHAR2(20),
 purchase_date DATE DEFAULT SYSDATE);
```
>[!note] Creates a table with title, artist, date columns with defined data types


# CREATE TABLE AS
- The alternate form CREATE TABLE statement. 
- Column names and/or data types can be specified in the query
- If nothing is provided then the columns provided in the statement as used to create the same-named columns.

## Syntax
```SQL
CREATE TABLE <copy_table_name>
	AS (SELECT * FROM <table_name>)
```

### Example
```SQL
CREATE TABLE copy_employees
	AS (SELECT * FROM employees)
```
>[!note] Creates a exact copy of the employees table



```SQL
SELECT * 
FROM mary.students
```
>[!note] Selecting elements from a table not owned by the user using a prefix. Access must be granted

