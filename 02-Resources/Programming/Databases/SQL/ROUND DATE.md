---
tags:
  - SQL
---
# ROUND DATE
- [[Date Functions|Function]] returns a date rounded to a specific unit.

## Syntax
```SQL
ROUND(date, format)
```
- Accepts two arguments
	- **Date** value or expression that evaluates to a date
	- **Format** a string format which specifies the unit to round.
		- If omitted, Oracle will round to the nearest day.

| Format                 | Description                              |     |
| ---------------------- | ---------------------------------------- | --- |
| CC, SCC                | Century, with or without minus sign      |     |
| YYYY, YEAR, YYY, YY, Y | Year                                     |     |
| IYYY, IYY, IY, I       | ISO Year                                 |     |
| Q                      | Quarter                                  |     |
| Month, Mon, MM, RM     | Month                                    |     |
| IW, WW                 | Week number                              |     |
| W                      | Day of the week                          |     |
| DDD, DD, J             | Day(of the year/of the month/Julian day) |     |
| Day, DY, D             | Closest Sunday                           |     |
| HH, HH12, HH24         | Hours                                    |     |
| MI                     | Minutes                                  |     |


### Example
```SQL
SELECT hire_date, ROUND(hire_date, 'Month')
FROM employees
WHERE department_id = 50;
```
> [!note] Rounds hire date to nearest month


