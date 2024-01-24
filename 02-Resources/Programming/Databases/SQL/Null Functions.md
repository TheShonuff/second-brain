---
tags:
  - SQL
---
# Null Functions
- Oracle has four general functions that pertain to the use of [[Null]] values
	- [[NVL Null Function|NVL]] Converts a null value to a know value of a fixed data typoe, either date, character, or number
		- The data types of the null value column and the new value must be the same.
	- [[NVL2 Null Function|NVL2]] Evaluates an expression with three values.
		- If the first value value **is not null**, then the *NVL2 function* returns the second expression
		- If the first value **is null**, then the third expression is returned.
		- The values in expression 1 can have any data type.
		- Expressions 2 & 3 can have any data type except LONG
		- The data type of the returned value is always the same as the data type of expression 2, unless expression 2 is character data, in which case the returned type is VARCHAR2
	- **[[NULLIF]]** Compares two expressions.
		- If expressions are equal, the function returns null
		- If the are not equal, the function returns the first expression
	- **[[COALESCE]]** is an extension of the NVL function, except COALESCE can take multiple values. 
		- If the first expression is null, the function continues down the line until a not null expression is found.

