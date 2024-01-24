---
tags:
  - SQL
---
# Date Functions
- Take a date as an input or output.
- Default date display DD-MM-YYYY
- **SYSDATE** Function that returns the current database server date and time.

## Working With Dates

```SQL
SELECT last_name, hire_date + 60
FROM employees
```
> [!note] Adds 60 days to hire date

```SQL
SELECT last_name, (SYSDATE - hire_date) / 7
FROM employees
```
> [!note] Displays the number of weeks since the employee was hired

```SQL
SELECT employee_id, (end_date - start_date) / 365 AS "Tenure in last job"
FROM job_history
```
> [!note] Finds the number of days employees held a job, then divides by 365 to display in years.

## Date Functions
| Function       | Description                                             |
| -------------- | ------------------------------------------------------- |
| MONTHS_BETWEEN | number of months between two dates                       |
| ADD_MONTHS     | Add calendar months to date                             |
| NEXT_DAY       | Date of the next occurence of day of the week specified |
| LAST_DAY       | Last day of the month                                   |
| ROUND          | Round date                                              |
| TRUNC          | Truncate date                                           |















DAY of the week
select to_char(to_date('23.06.2008', 'dd.mm.yyyy'), 'Day') from dual;