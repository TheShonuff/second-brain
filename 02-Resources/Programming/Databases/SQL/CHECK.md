---
tags:
  - SQL
---
# CHECK
- Explicitly defines a condition that must be met.
- To satisfy the constraint, each row in the table must make the condition either TRUE or unknown (due to null)
- The condition of a CHECK constraint can refer to any column in the specified table, but not columns of other tables.

```SQL
CREATE TABLE copy_job_history
(employee_id NUMBER(6,0),
 start_date DATE,
 end_date DATE,
 job_id VARCHAR2(10),
 department_id NUMBER(4,0),
 CONSTRAINT cjhist_emp_id_st_date_pk PRIMARTY KEY(employee_id, start_date),
 CONSTRAINT cjhist_end_ck CHECK (end_date > start_date));
```
>[!note] Check constraint to ensure that a value entered for end_date is later than the start_date.

- A CHECK constraint cannot be used in queries that refer to values in other rows.
- Cannot contain calls to the functions SYSDATE, UID, USER, USERENV
- Must only be on the row where the constraint is define.
- Cannot used the pseudocolumns CURRVAL, NEXTVAL, LEVEL, or ROWNUM
- A single column can have multiple **CHECK** constraints that reference the column it its definition
- There is no limit to the number of **CHECK** constraints that you can define on a column.
- Can be define on the table or column level.

```SQL
salary NUMBER(8,2) CONSTRAINT employees_min_sal_ck CHECK (salary > 0)
```
>[!note] Column-level check

```SQL
CONSTRAINT employees_min_sal_ck CHECK (salary > 0)
```
>[!note] Table-level check

