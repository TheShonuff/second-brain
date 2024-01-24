---
tags:
  - SQL
---
# ON DELETE SET NULL
- Rather than having the rows in the child table deleted we can fill the values with **NULL**.

```SQL
CREATE TABLE copy_employees
(employee_id NUMBER(6,0) CONSTRAINT copy_emp_pk PRIMARY KEY,
 first_name VARCHAR2(20),
 last_name VARCHAR2(25),
 department_id NUMBER(4,0),
 email VARCHAR2(25),
 CONSTRAINT cdept_dept_id_fk FOREIGN KEY (department_id)
	 REFERENCES copy_departments(department_id) ON DELETE SET NULL)
```
>[!note] Will set deleted value to null.

>[!tip] Useful for updating values for future




