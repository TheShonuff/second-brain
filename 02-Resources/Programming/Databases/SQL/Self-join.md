---
tags:
  - SQL
---

# Self-join
- To JOIN a table to iself as if it were two tables.
- To join a table to itself, the table is given two names or aliases.
	- Aliases can use AS or use shorthand and leave the AS out.
> [!tip] Use aliases that relate to the data's association with the table

```SQL
SELECT worker.last_name || ' works for ' }} manager.last_name
AS "Works for"
FROM employees worker JOIN employees manager
ON (worker.manager_id = manager.employee_id);
```

```SQL
SELECT worker.last_name, worker.manager_id, manager.last_name
AS "Manager Name"
FROM employees worker JOIN employees manager
ON (worker.manager_id = manager.employee_id);
```

> [!note] We can use other joins like [[Inner Join]] and [[Left Join]] with Self-join

## Hierarchical Queries
- closely related to self-joins
- Can retrieve data based on a natural relationship between rows in a table
- A method of reporting the branches of a tree in a specific order.
- Quereis have their own new keywords
	- **START WITH** identifies which row to use as the root for the tree.
	- **CONNECT BY PRIOR** Explains how to do the inter-row joins
	- **LEVEL** specifies how many branches deep the tree will traverse.

```SQL
SELECT employee_id, last_name, job_id, manager_id
FROM employees
START WITH employee_id = 100
CONNECT BY PRIOR employee_id = manager_id;
```

```SQL
SELECT LEVEL last_name || ' reports to ' || PRIOR last_name AS "Walk TOP DOWN" FROM employees
START WITH last_name = 'King'
CONNECT BY PRIOR employee_id = manager_id;
```

**LEVEL** is a pseudo-column used with hierarchical queries, and it cound the number of steps it has taken from the root of the tree.