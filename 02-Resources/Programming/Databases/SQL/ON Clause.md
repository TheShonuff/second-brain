---
tags:
  - SQL
---
# ON Clause
- If columns need to be joined that have different names, or if the join uses non-equality comparison operators or [[BETWEEN...AND|BETWEEN]] 
	- Use the ON clause to specify conditions or specify columns to join.
- The clause allows the use of [[WHERE]] to restrict rows from one or both tables.
### Syntax
```SQL
SELECT table1.column, table2.column
FROM table1
JOIN table2 ON (table1.column_name = table2.column_name);
```

### Example
```SQL
SELECT last_name, job_title
FROM employees e JOIN jobs j
ON (e.job_id = j.job_id)
WHERE last_name LIKE 'H%';
```

### Example with non-equality operator
```SQL
SELECT last_name, salary, grade_level, lowest_sal, highest_sal
FROM employees JOIN job_grades
ON(salary BETWEEN lowest_sal AND highest_sal);
```

## Joining Three Tables
- Both USING and ON can be used to join three or more tables.
```SQL
SELECT last_name, department_name AS "Department", city
FROM employees JOIN departments USING (department_id)
JOIN locations USING (location_id);
```



