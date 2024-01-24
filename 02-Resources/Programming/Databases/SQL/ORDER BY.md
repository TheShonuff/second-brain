---
tags:
  - SQL
---
# ORDER BY
- This clause is used to order data in ascending or descending order.
- Can specify several ways in which to order rows returned in a query.

> [!tip] The default sort order is ascending

> [! tip] Null values are displayed last in ascending order and first in descending order.

- **NULLS FIRST** Specifies that NULL values should be returned before non-NULL values
- **NULLS LAST** Specifies that NULL values should be returned after non-NULL values.

```SQL
SELECT last_name, hire_date
FROM employees
ORDER BY hire_date;
```
> [! note] Order by hire date by ascending

```SQL
SELECT last_name, hire_date
FROM employees
ORDER BY hire_date DESC;
```
> [! note] Order hire date by descending

> [! tip] Columns can be ordered by using column aliases

```SQL
SELECT last_name, hire_date as "Date Started"
FROM employees
ORDER BY "Date Started"
```
> [! note] Alias used to sort hire date by ascending values.
>

> [! tip] It's possible to order output by a column *not* in the SELECT clause

```SQL
SELECT employee_id, first_name
FROM employees
WHERE employee_id < 105
ORDER BY last_name;
```
> [! note] Ordered by a column not in the [[SELECT]] clause.

> [!tip] There is no limit on how many columns you can add to the **ORDER BY** clause

