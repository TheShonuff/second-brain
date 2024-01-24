---
tags:
  - SQL
---
# DEFAULT
- In the event that a new row is inserted and no value for the column is assigned
-  default value can be:
	- A literal value
	- An expression
	- SQL function
- Must match the data type of the column
- Can be specified for a column when the table is created or altered

### Example
```SQL
CREATE TABLE my_employees (
	hire_date     DATE DEFAULT SYSDATE,
	first_name    VARCHAR2(15),
	last_namae    VARCHAR2(15));
```
> [!note] Default value specified for the hire_date column

## Explicit DEFAULT with INSERT
- Explicit defaults can be used in [[SQL INSERT|INSERT]] and [[UPDATE]] statements

### Example
```SQL
INSERT INTO my_employees
	(hire_date, first_name, last_name)
VALUES
	(DEFAULT, 'Angelina', 'Wright')
```
>[!note] Explicit use of default in my_employee insertion

```SQL
INSERT INTO my_employees
	(hire_date, first_name, last_name)
VALUES
	('Angelina', 'Wright')
```
>[!note] Implicit use of default in my_employee insertion

## Explicit DEFAULT with UPDATE

### Example
```SQL
UPDATE my_employee
SET hire_date = DEFAULT
WHERE last_name = 'Wright';
```
> [!note] If the default value was specified the column is assigned the default value. If no default value was specified when the column was created, a null value is assigned

