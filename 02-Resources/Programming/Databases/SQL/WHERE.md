---
tags:
  - SQL
---
# WHERE
- A condition that limits the number of rows displayed. This condition immediately follows the FROM keyword. 
>[! tip] The condition uses all the basic logic testers; Greater than, less than, less than or equal to...etc

> [! Warning] Character strings and dates in the WHERE clause must be enclosed in single quotes.

```SQL
SELECT employee_id, first_name, last_name
FROM employees
WHERE employee_id = 101;
```
> [! note] Returns all rows where employee ID equals 101

```SQL
SELECT first_name, last_name
FROM employees
WHERE last_name = 'Taylor';
```
> [! note] Returns all rows where the last name is Taylor

> [!warning] All character searches are case-sensitive

- **WHERE** can be combined with conditial statements like [[BETWEEN...AND]], [[IN]] and [[LIKE]]
- Simple comparison operators can be used to filter rows.
- There are two symbols that represent **not equal**

## Not Equal
- !=
- <>

```SQL
SELECT *
FROM departments
WHERE Department_id < 90;
```
> [! note] Comparison operator that will list all departments with ID's less then 90

