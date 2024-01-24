---
tags:
  - SQL
---
# Aliases
- A way of renaming a column heading in the output. There are several rules when using aliases to format output.

> [! tip] The column name defaults to the name in the database.

- A column aliase:
	- Renames a column heading
	- is useful with calculations
	- Immediately follows the column name
	- May have the optional *AS* keyword between the column name and alias
	- **Requires double quotation marks if the alias contains spaces or special characters, or is case-sensitive.**
	
```SQL
SELECT * |colum|expr [AS alias], FROM table;
```
> [! note] Syntax for aliases

```SQL
SELECT last_name AS name, comission_pct AS comm FROM employees
```
> [!note] Using **AS** to create an alias

```SQL
SELECT last_name "Name", salary*12 "Annual Salary" FROM employees;
```
> [!note] Using quotations to create an alias without **AS**

### Aliases and Functions
- Often a column alias is used to name a function.
- The column alias will appear in the output instead of the actual function syntax.
>[!note] By default, the column name in a SELECT statement appears as the column heading.


