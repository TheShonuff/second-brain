---
tags:
  - SQL
---

# LAST DAY
 - [[Date Functions|Function]] returns the last day of the month of that date.

## Syntax
```SQL
LAST_DAY(date)
```
- Accepts one argument.
	- **Date** value or expression that evaluates to a date.

### Examples
```SQL
SELECT LAST_DAY (SYSDATE) as "End of the Month"
FROM dual;
```
> [!note] Returns the last date mm/dd/yyyy of the current month

```SQL
SELECT LAST_DAY(SYSDATE) - SYSDATE
FROM dual;
```
> [!note] Returns the numbers of days left in the month
