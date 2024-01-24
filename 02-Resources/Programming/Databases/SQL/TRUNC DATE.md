---
tags:
  - SQL
---
# TRUNC DATE
[[Date Functions|Function]] returns a date value truncated to a specified unit.

## Syntax
```SQL
TRUNC(date, format)
```
- Accepts two arguments
	- **Date** value or expression that evaluates to a date
	- **Format** a string that determine the unit to which date is truncated

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

### Examples
```SQL
SELECT hire_date, TRUNC(hire_date, 'Month')
FROM employees
WHERE department_id = 50;
```
> [!note] Returns the first day of the month for hire_date

