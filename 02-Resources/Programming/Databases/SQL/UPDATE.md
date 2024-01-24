---
tags:
  - SQL
---
# UPDATE
- used to modify existing rows in a table
- **UPDATE** requires four values:
	1. The name of the table
	2. The name of the column(s) whose value will be modified
	3. A new value for each column(s) being modified
	4. A condition that identifies which rows in the table will be modified.
- The new value for a column can be the result of a [[Single-Row Subqueries|Single-row Subquery]]

> [! warning] If the [[WHERE]] clause is omitted, every row in the table will be updated.

### Example
```SQL
UPDATE copy_employee
SET phone_number = '123456'
WHERE employee_id = 303;
```
>[!note] Update the phone number for employee matching id 303

## Updating a Column with a value from a Subquery
- A [[Single-Row Subqueries|Single-row Subquery]] can provide the new value for an updated column.
	- A usual the subquery will execute first and retireve the data.

### Example
```SQL
UPDATE copy_employee
SET salary = (SELECT salary
			  FROM copy_employees
			  WHERE employee_id = 100)
WHERE employee_id = 101
```
> [!note] Changes the salary of one employee(id = 101) to the same salary as another employee(id = 100)

## Updating Two Columns with Two Subquery Statements
- It's possible to write multiple single-row subqueries, one for each column.

### Example
```SQL
UPDATE copy_employees
SET salary = (SELECT salary
			  FROM copy_employee
			  WHERE employee_id = 205),
	job_id = (SLECT job_id
			  FROM copy_employees
			  WHERE employee_id = 205)
WHERE employee_id = 206;
```
>[! note] Change the job_id and salary of one employe (id= 206) to match employee (id = 205)

## updating Rows Using Correlated Subquery
- In a correlated subquery, you are updating a row in a table based on a select from that same table

### Example
```SQL
UPDATE copy_employee e
SET e.department_name = (SELECT d.department_name
						 FROM departments d
						 WHERE e.department_id = d.department_id);
```