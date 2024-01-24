---
tags:
  - SQL
---

# ON DELETE CASCADE
- This optionenables the dependent rows in the child table to be deleted when a row in the parent table is deleted.
- If the foreign key does not have an **ON DELETE CASCADE** option, referenced rows in the parent table cannot be deleted.

```SQL
CREATE TABLE copy_employees
(employee_id NUMBER(6,0) CONSTRAINT copy_emp_pk PRIMARY KEY,
 first_name VARCHAR2(20),
 last_name VARCHAR2(25),
 department_id NUMBER(4,0),
 email VARCHAR2(25),
 CONSTRAINT cdept_dept_id_fk FOREIGN KEY (department_id)
	 REFERENCES copy_departments(department_id))
```
>[!note] Table created **without** ON DELETE CASCADE. Any attempt to delete department_id 110 from the departments table failsa s there are dependent rows in the employee table.

```SQL
CREATE TABLE copy_employees
(employee_id NUMBER(6,0) CONSTRAINT copy_emp_pk PRIMARY KEY,
 first_name VARCHAR2(20),
 last_name VARCHAR2(25),
 department_id NUMBER(4,0),
 email VARCHAR2(25),
 CONSTRAINT cdept_dept_id_fk FOREIGN KEY (department_id)
	 REFERENCES copy_departments(department_id) ON DELETE CASCADE);
```
>[!note] Table create with ON DELETE CASCADE. Deleting department_id 110 from the department table succeeds, and the depedent rows in the employee table are also deleted.




