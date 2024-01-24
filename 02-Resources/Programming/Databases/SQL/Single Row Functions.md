---
tags:
  - SQL
---

# Single Row Functions
- Divided into two categories
	- Functions that convert the case of character strings
	- Functions that join, extract, show, find, pad, and trim character strings

>[! tip] These functions can be used in **SELECT**, **WHERE**, and **ORDER BY** clauses

## Case Manipulation Functions
- **LOWER** converts to lowercase
- **UPPER** converts to uppercase
- **INITCAP** converts alpha character values to Uppercase for the first letter of each word
> [!tip] Helpful when you are looking for data and unsure whether the data is upper or lower case

## Character Manipulation Functions
- **CONCAT** Joins two values. Similar to the concatenation operator
- **SUBSTR** Extracts a string of a determined length. The *arguments* are (character string, starting position, length). The length is optional, if omitted, returns all the characters to the end of the string.
	- *SUBSTR(expression, start,length)*
> [! tip] The count starts at 1 not 0
- **LENGTH** Shows the length of a string as a number value
- **INSTR** Finds the numeric position of the specifed character(s)
	- *INSTR(string1, string2)*
- **LPAD | RPAD**
	- ***LPAD*** Pads the left side of a character string, resulting in a right-justified value. This function requires 3 arguments. 
		- A String
		- The total number of characters in the padded string
		- The character to pad with
		- *LPAD(string, length, pad_string)*
	- ***RPAD*** Pads the right-hand side of a character string. This also accepts 3 arguments.
- **TRIM** Removes all specified character from either the beginning, the end, or both beginning and end of a string. We can use **LEADING**, **TRAILING**, **BOTH** to specify how the string is trimmed.
- **REPLACE** Replaces a sequence of character in a string with another set of characters. REPLACE (string1, string_to_replace, replacement_string)





