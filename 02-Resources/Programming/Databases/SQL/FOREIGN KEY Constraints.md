---
tags:
  - SQL
---

# FOREIGN KEY Constraints
- Also called *"referential integrity"* constraints
	- To satisfy a "referential integrity" constraint, a foreign key value **must** match an existing value in the parent table or be null.
- Designates a column or combination of columns as a foreign key.

>[!tip] A foreign keys links back to the primary key in another table, and this link is the basis of the relationship between tables.

- The table containing the foreign key is called the *"child"* table
- The table containg the reference key is called the *"parent"* table.

>[!Warning] A primary-key can exist without a corresponding foreign-key value; **however** a foreign-key must have a corresponding primary key

#### The Rule
- Before you define a referential-integrity constraint in the child table, the referenced [[UNIQUE Constraint|UNIQUE]] or [[PRIMARY KEY Constraints|PRIMARY KEY]] constraint on the parent table must already be define.
- **TL:DR** You must have a parent primary key defined before you can create a foreign key.

>[!tip] Use the suffix **_fk** in the constraint name


```SQL
CREATE TABLE copy_employees
(employee_id NUMBER(6,0) CONSTRAINT copy_emp_pk PRIMARY KEY,
 first_name VARCHAR2(20),
 last_name VARCHAR2(25).
 department_id NUMBER(4,0) CONSTRAINT c_emps_id_fk REFERENCES departments(department_id),
 email VARCHAR2(25));
```
>[!note] Column-level foreign key constraint

```SQL
CREATE TABLE copy_employees
(employee_id NUMBER(6,0) CONSTRAINT copy_emp_pk PRIMARY KEY,
 first_name VARCHAR2(20),
 last_name VARCHAR2(25).
 department_id NUMBER(4,0),
 email VARCHAR2(25),
 CONSTRAINT c_emps_id_fk FOREIGN KEY (department_id) REFERENCES departments(department_id));
```