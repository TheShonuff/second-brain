---
tags:
  - SQL
---
# CROSS Join
- Joins each row in one table to every row in the other table.
- The result set represent all possible row cominations from the two tables.
- Does not let you specify a join clause.
	- You can specify a [[WHERE]] clause in the [[SELECT]] statement
> [!warning] If you CROSS JOIN a table with 20 rows with a table with 100 rows, the query will return 2000 rows.



### Examples
```SQL
SELECT last_name, department_name
FROM employees CROSS JOIN departments;
```

```SQL
SELECT * FROM cities CROSS JOIN flights
```

