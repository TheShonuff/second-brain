---
tags:
  - SQL
---
# Single-Row Subqueries
- Used when the **main query** (outer query) results are based on a single, unknown value.
- Return only one row of results consisting of only one column to the main query
- Use single-row comparison operators: =, >, >=, <, <=, <>

### Examples
```SQL
SELECT first_name, salary, department_id
from employees
WHERE salary = (SELECT MIN(salary) FROM employees);
```
>[!note] subquery results one results and the main query returns all employees whose salary is equal to the minimum salary

```SQL
SELECT department_id, TO_CHAR(ROUND(AVG(salary),2), '$999999.99') "Average Salary" FROM employees
GROUP BY department_id
HAVING AVG(salary) > 
    (SELECT salary FROM employees WHERE last_name = 'Ernst');
```
> [! note] Returns a list of department id's and average slaries where the department's average salary is greater than Ernst's Salary

If a single-row subquery returns a null value and uses the equality comparison operator it will return NO ROWS