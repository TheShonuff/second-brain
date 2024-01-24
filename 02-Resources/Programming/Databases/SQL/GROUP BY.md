---
tags:
  - SQL
---

# GROUP BY
- Divides rows in a table into smaller groups.
- Group functions can return summary information for each group.
- Every distinct value of the column mentioned in the **GROUP BY** clause becomes a separate group.

### Example
```SQL
SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id
ORDER BY deparment_id;
```

> [!note] Maxiumum salary of employees in each department
```SQL
SELECT department_id, MAX(salary)
FROM employees
GROUP BY department_id;
```

> [!warning] Group functions require that any column listed in the SELECT clause that is not part of a group function must be listed in a GROUP BY clause

>[! Tip] Group Functions ignore null values

- A [[WHERE]] clause can be used to exclude rows **before** the remaining rows are formed.
```SQL
SELECT department_id, MAX(salary)
FROM employees
WHERE last_name != 'King'
GROUP BY department_id;
```

- Some guidlines to remeber when using GROUP BY clauses are:
	- If a group function(AVG, SUM, COUNT, MAX...) is found in a SELECT clause along with any other individual columns, each individual column must also appear in the GROUP BY clause
	- The Where clause excludes rows *before* they are divided into groups.
> [! warning] Column aliases cannot be used in GROUP BY clause


## Groups Within Groups
- Groups can be divided into smaller groups.
- Can be nested to a depth of two

```SQL
SELECT department_id, job_id, count(*)
FROM employees
WHERE department_id > 40
GROUP BY deparment_id, job_id;
```
> [!note] Group all employees by department, then within each department, group by job

