---
tags:
  - SQL
---

# Subqueries
- Simply a query within another query.
	- The outer query is called the **main query** #main-query
	- The inner query is called the **subquery**

> [!tip] - The subquery executes to find the information you don't know.
> - The main query uses that information to find out what you need to know.

- Can be placed in a number of clauses:
	- [[WHERE]]
	- [[HAVING]]
	- [[SELECT]]
	- UPDATE
	- INSERT
	- DELETE
	
>[! warning] The subquery executes before the main query.

- The result of the **subquery** is used but the **main query**
- Subqueries are on the right side of the comparison operator.
	- Should select the column being compared.

>[! warning] A subquery must be enclosed in parentheses

## Guidelines
- The outer and inner queries can get data from different tables.
- Only one [[ORDER BY]] clause can be used for a [[SELECT]] statement
	- If used, it must be the last clause in the outer query
- Cannot have its own [[ORDER BY]] clause
- The only limit on the number of subqueries is the the buffer size the query uses.

## Syntax
```SQL
SELECT column_name
FROM table_name
WHERE column_name <comparison operator>
	(SELECT column_name FROM table_name WHERE ....);
```

## Two Types of Subqueries
- **[[Single-Row Subqueries|Single-Row]]** use single row operators and return only one row from inner query
- **[[Multiple-Row Subqueries|Multi-row]]** use multiple-row operators and return more than one row from the inner query.

### Examples
```SQL
SELECT first_name, last_name, hire_date
FROM employees
WHERE hire_date > 
	(SELECT hire_date
		FROM employees
		WHERE last_name = 'Vargas');
```
>[!note] Finds the employees hired after Vargas

```SQL
SELECT name FROM d_events
WHERE theme_code = 
	(SELECT code FROM d_themes
	 WHERE description = "Tropical")
```
>[! note] Returns the list of DJs on Demand events whose theme code is the same as the code for "Tropical"

## Subquery and Null
- If a subquery returns a null value or no rows, the outer query takes the results of the subquery and uses this result in its [[WHERE]] clause.
- The outer query will return no results. Comparing any value to null is null.
