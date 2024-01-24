---
tags:
  - SQL
---

# Filtering Dates
- There are two ways to filter date values in SQL
	- Single quotes in a specific format
	- Using a function
> [! Warning] Date formatting is dependant on what is currently being used in the database

### Example
```SQL
SELECT *
FROM employee
WHERE hire_date = '03-OCT-2010';
```



