---
tags:
  - SQL
---
# Conditional Expressions
- There a two conditional expressions used
	- **CASE**
	- **DECODE**
> [!note] NULLIF is logically equivalent to the CASE expression.

> [!note] There are two sets of commands or syntax used **ANSI / ISO SQL 99** and **Oracle proprietary statments**


# Case
- This expression basically does the work of an IF-THEN-ELSE statement.
- Data types of CASE, WHEN, and ELSE must be the same

```SQL
SELECT last_name,
CASE department_id
	WHEN 90 Then 'Management'
	WHEN 80 THEN 'Sales'
	WHEN 60 Then 'It'
	ELSE 'Other dept'
END AS "Department"
FROM employees;
```

# Decode
- The function evaluates an expression in a similar way to the IF-THEN-ELSE logic.
- Compares an expression to each of the search values.
> [!warning] If the default value is omitted, a null value is returned where a search value does not match any of the values

> [!tip] Syntax is similar to [[Match]] statements in rust

```SQL
SELECT last_name,
DECODE (department_id,
	   90, 'Management',
	   80, 'Sales',
	   60, 'It',
	   'Other dept')
AS "Department"
FROM employees;
```
