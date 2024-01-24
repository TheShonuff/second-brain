---
tags:
  - SQL
---
# Multi-Table Insert
- Can be uncoditional or conditional
- In a unconditional insert - Oracle will insert all rows returned by the subquery into a table insert clauses found the statement.
- In a conditional insert - You can specify either all or FIRST
	- **Specifying ALL:**
		- The default value
		- The database evaluates each WHEN clause regardless of the results
		- For each TRUE condition the database executes the corresponding INTO clause list
	- **Specifying FIRST:**
		- The database evaluates each WHEN clauses in the roder in which it appears in the statement
		- For the first WHEN clause that evaluate to TRUE, the database executes the corresponding ITNO clause and skip subsequen WHEN clauses for the given row
- **ELSE:**
	- For a given row, if no WHEN clause evaluates to true, the database executes the ITNO clause list associated with the ELSE clause
	- If no else cluase, the database takes no action for that row.


## Syntax
```SQL
INSERT ALL INTO clauses VALUES clause SUBQERY
```

### Example
```SQL
INSERT ALL
	INTO my_employees
		VALUES (hire_date, first_name, last_name)
	INTO copy_my_employees
		VALUES (hire_date, first_name, last_name)
SELECT hire_date, first_name, last_name
FROM employees;
```

