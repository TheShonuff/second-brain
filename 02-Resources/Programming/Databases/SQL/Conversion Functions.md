---
tags:
  - SQL
---

# Conversion Functions
Understanding [[SQL Data Types]] will be helpful in fully understanding the material.

## Implicit Data Conversion
- The Oracle Server can automatically convert **VARCHAR2** and **CHAR** data to **NUMBER** and **DATE** data types.
- The Oracle Server can convert **NUMBER** and **DATE** data back to **CHARACTER** data type.

| FROM             | TO       |
| ---------------- | -------- |
| VARCHAR2 or CHAR | NUMBER   |
| VARCHAR2 or CHAR | DATE     |
| NUMBER           | VARCHAR2 |
| DATE             | VARCHAR2         |

## Format Models
| Input          | Output                                           |
| -------------- | ------------------------------------------------ |
| YYYY           | Full year in numbers                             |
| YEAR           | Year spelled out                                 |
| MM             | Two-digit value for month                        |
| MONTH          | Full name of the month                           |
| MON            | Three-letter abbreviation of the month           |
| DY             | Three-letter abbreviation of the day of the week |
| DAY            | Full name of the day of the week                 |
| DD             | Numeric day of the month                         |
| DDspth         | FOURTEENTH                                       |
| Ddspth         | Fourteenth                                       |
| ddspth         | fourteenth                                       |
| DDD or DD or D | Day of year, month or week                       |
| HH24:MI:SS AM  | 15:45:32 PM                                      |
| DD "of" MONTH  | 12 of October                                                 |

> [!note] extensive list of conversions can be found in [[TO_CHAR]]

# Date Conversion to Character Data
```SQL
SELECT TO_CHAR(hire_date, 'Month dd, YYYY') FROM employees;
```
**Output** June 07, 1994

```SQL
SELECT TO_CHAR(hire_date, 'fmMonth dd, YYYY') FROM employees;
```
**Output** June 7, 1994

```SQL
SELECT TO_CHAR(hire_date, 'fmMonth ddth, YYYY') FROM employees;
```
**Output** June 7th, 1994 

```SQL
SELECT TO_CHAR(hire_date, 'fmDay ddth Mon, YYYY') FROM employees;
```
**Output** Tuesday 7th Jun, 19994

```SQL
SELECT TO_CHAR(hire_date, 'fmDay ddthsp Mon, YYYY') FROM employees;
```
**Output** Tuesday, seventh Jun, 1994

```SQL
SELECT TO_CHAR(hire_date, 'fmDay, ddthsp "of" Month, Year') FROM employees;
```
**Output** Tuesday, seventh of June, Nineteen Ninety-Four

### Time Conversions
```SQL
SELECT TO_CHAR(SYSDATE, 'hh:mm') FROM dual;
```
**Output** 02:07

```SQL
SELECT TO_CHAR(SYSDATE, 'hh:mm pm') FROM dual;
```
**Output** 02:07 am

```SQL
SELECT TO_CHAR(SYSDATE, 'hh:mm:ss pm') FROM dual;
```
**Output** 02:07:23 am

# Number Conversion to Character Data
- Number Conversion to Character Data
	- Number stored in the database have no formatting.
		- There are no signs, symbols, commas, decimals
	- To add formatting convert the number using [[TO_CHAR]]
```SQL
SELECT TO_CHAR(salary, '$99,999') AS "Salary" FROM employees;
```

| Element | Description                                        | Example    | Result   |
| ------- | -------------------------------------------------- | ---------- | -------- |
| 9       | Numeric Position(# of 9's determine width)         | 999999     | 1234     |
| 0       | Display Leading zeros                              | 099999     | 001234   |
| $       | Floating dollar sign                               | $999999    | $1234    |
| L       | Floating local currency                            | L999999    | FF1234   |
| .       | Decimal point in position specified                | 999999.99  | 1234.00  |
| ,       | Comma in position specified                        | 999,999    | 1,234    |
| MI      | Minus sign to right (negative values)              | 99999MI    | 1234-    |
| PR      | Paratehesize negative numbers                      | 999999PR   | <1234>   |
| EEEE    | Scientific notation (must have four E's)           | 99.999EEEE | 1,23E+03 |
| V       | Multiply by 10 n times (n = number of 9's after V) | 9999V99    | 9999V99  |
| B       | Display zero values as blank, not 0                | B9999.99   | 1234.00         |

```SQL
SELECT TO_CHAR(3000, '$99999.99') FROM dual;
```
**Output** $3000.00

```SQL
SELECT TO_CHAR(4500, '99,999') FROM dual;
```
**Output** 4,500

```SQL
SELECT TO_CHAR(9000, '99,999.99') FROM dual;
```
**Output** 9,000.00
```SQL
SELECT TO_CHAR(4422, '0009999') FROM dual;
```
**Output** 0004422


# Character Conversion to Number
- To convert a character string to a number **TO_NUMBER**
```SQL
TO_NUMBER('character string', 'format model')
```
- The format model is optional, but should be included.

> [!warning] You cannot reliably perform calculations with character data

# Character Conversion to Date
- To convert a character string to a date format **TO_DATE**
```SQL
TO_DATE('Character String', 'format mode')
```
- This conversion take a non-date value character string linke "November 3, 2001" and converts it to date value.
```SQL
TO_DATE('November 3, 2001', 'Month dd, yyyy')
```
**Output** 03-Nov-2001
- The *fx* (format exact) modiifer specifies exact matching for the character argument and the date format model.
```SQL
SELECT TO_DATE('May10,1989', 'fxMonDD,YYYY') AS "Convert" FROM dual;
```
**Output** 10-May-1989

## fx Modifier Rules
- Punction and quoted texxt in the character argument must match the corresponding parts of the format model exactly (except for case)
- The character argument cannot have extra blanks.
	- Without fx, the Oracle Server ignores extra blanks.
- Numeric data in the character argument must have the same number of digits as the corresponding element in the format model.
	- Without fx, numbers in the character argument can omit leading zeros.

### Examples
```SQL
SELECT TO_DATE('Sep 07, 1965', 'fxMon dd, YYYY') AS "Date" FROM dual;
```
**Output** 07-Sep-1965

```SQL
SELECT TO_DATE('July312004', 'fxMonthDDYYYY') AS "Date" FROM dual;
```
**Output** 31-Jul-2004

```SQL
SELECT TO_DATE('June 19, 1990', 'fxMonth dd, YYYY') AS "Date" FROM dual;
```
**Output** 19-Jun-1990

> [!tip] If the data being converted from character data to date data contains only a two-digit year, Oracle has a way of interpreting these dates in the correct century.

> [!warning] If YY is used in the format model, the year is assumed to be in the current century.

- If the two-digit year is not in the current century, **RR** is used.
```SQL
SELECT TO_DATE('27-Oct-95', 'DD-Mon-RR') AS "Date" FROM dual;
```
**Output** 27-Oct-1995

- If the date format is specified with the **RR**, the return value has two possibilites, depending on the current year. 
	- If the current year is between 00-49
		- **Dates from 0-49** The date will be in the current century
		- **Dates from 50-99** the date will be from the last centry
	- If the current year is between 50-99
		- **Dates from 0-49** The date will be in the next century
		- **Dates from 50-99** The date will be in the current century