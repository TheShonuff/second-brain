---
tags:
  - SQL
---

# JOINs
- A SQL `JOIN` clause combines fields of 2 (or more) tables in a relational database
- There are two sets of commands or syntax which can be used to make connections between tables in a database.
	- **Oracle prprietary joins**
		- [[Cartesian Product Join|Cartesian Product]]
		- [[EQUIJOIN]] 
		- Non-equijoin
	- **ANSI/ISO SQL 99 compliant standard joins**
		- [[CROSS Join]]
		- [[Natural Join]]
		- Join USING
		- JOIN ON
		- ON clause

>[!tip] The purpose of a JOIN is to bind data together, across tables, without repeating all of the data in every table

### Qualify your columns
- To make it easier to read a join statement and to speed up database access, it is good practice to preface the column.
- The combination of table name and column name helps eliminate ambigous names when two tables contain a column with the same column name.
- **tablename**.*columnname*

### Aliases
- To distinguis columns that have identical names but reside in different tables
- Table alias is similar to a column alias.
- Created by entering the new name for the table just after the table name in the FROM clause
```SQL
SELECT last_name, e.job_id, job_title
FROM employees e, jobs j
WHERE e.job_id = j.job_id
	AND department_id = 80;
```

> [!warning] If a table alias is used in the FROM clause, then that table alias must be substituted for the table name throughout the SELECT statement.

#### Join Three Tables
```SQL
SELECT last_name, city
FROM employees e, departments d, locations l
WHERE e.department_id = d.department_id
	AND d.location_id = l.location_id;
```
> [!note] This example is using the [[Oracle Propretary Join]] syntax


----


