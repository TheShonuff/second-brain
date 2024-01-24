---
tags:
  - SQL
---

---
Created: [[03-28-2023]]
tags: 
---
# SQL INSERT
- Adds one or more rows of data to a database table.
- Requires three values
	1. The name of the table
	2. the names of the column in the table to populate
	3. corresponding values for each column
	
> [! tip] Always check the table first before inserting data into a table. Use **DESCRIBE** to get a description of datatypes.

## Syntax
```SQL
INSERT INTO table_name
	(column_1_name, column_2_name, column_3_name )
VALUES
	(column_1_value, column_2_value, column_3_value)
```
>[! note] Values are inserted as explicity described in the *insert into*

```SQL
INSERT INTO table_name
VALUES
	(column_1, column_2, column3...)
```
>[! note] Implicitly add values to columns by omitting the column names.

>[!warning] Implicitly adding values must correspond to the column data type

### Example
```SQL
INSERT INTO copy_departments
	(department_id, department_name, manager_id, location_id)
Values
	(200, 'Human Resources', 205, 1500)
```
>[!note] Inserts explicity defined row into the copy of departments table

## Inserting Values With Null Values
- The **INSERT** statement need not specify every column
	- Nullable columns may be excluded.
	- If every column that requires a value is assigned a value, the insert works.
- Implicit insert with automatically insert a null value
- To explicitly insert a null value, use the keyword **NULL** in the values list.
- Missing or empty data use empty single quotation marks with no space.

## Inserting Specific Data Values
- The default format model for the date data type is DD-MON-YYYY
- To insert a non-default format for the date column use the <code>TO_DATE()</code> [[Date Functions|function]]

### Example
```SQL
INSERT INTO copy_employees
	(employee_id, first_name, last_name, email, phone_number, hire_date, job_id, salary)
VALUES
	(301, 'Kaite', 'Hernandez', 'khernandez', '8586667641', 
	TO_DATE('July 8, 2015', 'Month fmdd, yyyy'), 'MK_REP', 4200)
```
>[! note] Insert employee into copy of employee table with a hire_date format

## Using A Subquery To Copy Rows
- Can copy multiple rows to a new table
- The number of columns and their data types in the column list of the **INSERT** clause must match the number of columns and their data types in the subquery.
- The subquery is not enclosed in parentheses as like in the [[WHERE]] clause of a [[SELECT]] statement.

### Example
```SQL
INSERT INTO sales_reps(id, name, salary, commission_pct)
	SELECT employee_id, last_name, salary, commission_pct
	FROM employees
	WHERE job_id LIKE '%REP%';
```
>[!note] A new table is populated with copies of some of the rows and columns from the EMPLOYEES table.


