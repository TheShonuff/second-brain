---
tags:
  - SQL
---
# NEXT DAY
- [[Date Functions|Function]] returns the date of the first weekday specified by day name that is later than a date

## Syntax
```SQL
NEXT_DAY(date, weekday)
```
- Accepts two arguments
	- **Date** value or expression that evaluates to a date
	- **Weekday** the day of the week you want to return

### Example
```SQL
SELECT NEXT_DAY (SYSDATE, 'Saturday') AS "Next Saturday"
FROM dual;
```
>[!note] Returns the date of the next saturday


