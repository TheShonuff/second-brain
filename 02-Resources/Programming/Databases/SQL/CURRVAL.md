---
tags:
  - SQL
---
# CURRVAL
- - Pseudocolumn used to refer to a sequence number that the current user has just generated
- NEXTVAL must be used to generate a sequence number in the current user's session before **CURRVAL** can be referenced.
- Must be qualified with the sequence name.

```SQL
INSERT INTO employees
	(employee_id, department_id, ...)
VALUES ( employees_seq.NEXTVAL, dep_depti_seq.CURRVAL, ...)
```

- You can use **NEXTVAL** & **CURRVAL** in the following contexts:
	- The SELECT list of a SELECT statement that is not part of a subquery
	- The SELECT list of a subquery in an INSERT statement
	- The VALUES clause of an INSERT statement
	- The SET clause of an UPDATE statement.
- You cannot use **NEXTVAL** & **CURRVAL** in the following contexts:
	- The SELECT list of a view
	- A SELECT statement with the DISTINCT keyword
	- A SELECT statement with GROUP BY, HAVING, or ORDER BY clasues
	- A subquery in a SELECT, DELETE, or UPDATE statement
	- The DEFAULT statement in a CREATE TABLE or ALTER TABLE statement.

>[!warning]  if any SQL queries contains references to both CURRVAL and NEXTVAL, then Oracle increments the sequence and returns the same value for both CURRVAL and NEXTVAL regardless of their order in the statement.

