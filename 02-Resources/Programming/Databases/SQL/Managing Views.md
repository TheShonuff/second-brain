---
tags:
  - SQL
---
# Managing Views


## Deleting a View
- Removing a view does not affect the data in the underlying tables.
- If the view had a DML operation performed in the past, those changes to the base tables remain.
- Deleting a view simply removes the view definition from the database.
	- Views are stored as SELECT statements in the data dictionary.
- Only the creator or users with the <code>DROP ANY VIEW</code> privilege can remove a view.

### Example
```SQL
DROP VIEW viewname;
```


## Inline Views
- Referred to as subqueries in the FROM clause.
- You insert a subquery in the FROM clause just as if the subquery was a table name.
- Commonly used to simplify complex queries by removing join operations and condensing several queries into one.

### Example
```SQL
SELECT e.last_name, e.salary, e.department_id, d.maxsal
FROM employees e,
	(SELECT department_id, max(salary) maxsal
	 FROM employees
	 GROUP BY department_id) d
WHERE e.department_id = d.department_id
AND e.salary = d.maxsal
```
>[!note] The data returned by the subquery is given an alias (d) which is then used in conjunction with the main query to return select columns from both query sources.

## TOP-N-ANALYSIS
- SQL operation to rank results
- Useful when you want to retrieve the top 5 records, or top-n records, of a result set returned by a query.
- Uses an inline query (a subquery) to return a result set.
- You can use **ROWNUM** in the query to assign a row number to the result set.
- The main query then uses **ROWNUM** to order the data and return the top-n records.

### Example
```SQL
SELECT ROWNUM AS "Longest employed", last_name, hire_date
FROM employees
WHERE ROWNUM <= 5
ORDER BY hire_date
```
>[!note] Returns the top 5 longest employed employees

```SQL
SELECT ROWNUM AS "Longest employed", last_name, hire_date
FROM (SELECT last_name, hire_date
	  FROM employees
	  ORDER BY hire_date)
WHERE ROWNUM <= 5
```