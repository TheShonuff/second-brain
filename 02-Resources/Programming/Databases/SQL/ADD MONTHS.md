---
tags:
  - SQL
---
# ADD MONTHS
- [[SQL Functions|Function]] adds a number of month (n) to a date and returns the same day n number of months away.

## Syntax
```SQL
ADD_MONTHS(date_expression, month)
```
- Function accepts two arguments.
	- **Date_expression** is a date value or expression that evaluates to a date
	- **Month** an integer that represents a number of months
		- Can be a zero, positive or negative integer
	

### Examples
```SQL
SELECT ADD_MONTHS (SYSDATE, 12) AS "Next Year"
FROM dual;
```
> [!note] Adds 12 months to the current date

```SQL
SELECT ADD_MONTHS (SYSDATE, -2) AS "Next Year"
FROM dual;
```
> [!note] subtracts 2 months from the current date

