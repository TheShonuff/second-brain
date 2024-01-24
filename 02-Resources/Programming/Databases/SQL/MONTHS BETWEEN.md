---
tags:
  - SQL
---
# MONTHS BETWEEN
- [[SQL Functions|Function]] returns the number of months between two dates.
## Syntax
```SQL
MONTHS_BETWEEN(minuend_date, subtrahend_date);
```

- Function requires two arguments
- Each argument can be a date or an expression that evaluates to a date
- **Minuend** is a date which is subtracted from
- **Subtrahend** the date which is to be subtracted

### Example
```SQL
SELECT last_name, hire_date
FROM employees
WHERE MONTHS_BETWEEN (SYSDATE, hire_date) > 240;
```
> [!note] Lists employees who have been at the complany longer than 240 days

```SQL
SELECT MONTHS_BETWEEN( DATE '2017-07-01', DATE '2017-01-01' ) MONTH_DIFF FROM DUAL;
```
> [!note] Returns the number of months, 6, between the two dates.

