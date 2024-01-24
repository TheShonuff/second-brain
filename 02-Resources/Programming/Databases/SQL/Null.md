---
tags:
  - SQL
---
# Null
- Is a value that is unavailable, unassigned, unknown or inapplicable.
- ***It is not the same as zero or space.*** 
> [! tip] A zero is a number and space is a character.

## Testing For Null
- A test can be performed in the [[WHERE]] clause to limit rows.
	- The *IS NULL* condition tests for unavailable, unassigned, or unknown data.
	- *IS NOT NULL* tests for data that is available in the database.

```SQL
SELECT last_name, manager_id 
FROM employees
WHERE manager_id IS NULL;
```
> [! note] limits rows to where manager_id is null


```SQL
SELECT last_name, manager_id
FROM employees
WHERE manager_id IS NOT NULL;
```
> [! note] Limits rows to where manager_id has a value



