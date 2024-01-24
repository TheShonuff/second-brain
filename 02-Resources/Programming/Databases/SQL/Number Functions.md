---
tags:
  - SQL
---
# Number Functions
- The three number functions are:
	- **ROUND** Can be used for both numbers and dates. Used for rounding numbers to  a specified number of decimal places.	
		- *ROUND(column|expression, decimal places)*
		- If no decimal places is not specified or is zero, the number will round to no decimal places.
		- If number is **positive** the number rounded is rounded to the supplied number to the right of the decimal
		- If a number is **negative** the number rounded is rounded to the supplied number to the left of the decimal.
	- **TRUNC** Can be used with both numbers and dates. It is mainly used to terminate the column expression, or value to a specified number of decimal places.
		- *TRUNC(column|expression, decimal places)*
		- If no decimal place is specified then the number is truncated to zero decimal places
		- **TRUNC does not round it only terminates to a given point**
	- **MOD** Find the remained after one value is divided by another value.
		- Typically used to find whether a number is even or odd.
		- *MOD(column|expression, value)*


