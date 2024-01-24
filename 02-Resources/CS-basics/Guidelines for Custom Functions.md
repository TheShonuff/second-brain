---
tags:
  - cs
---

# Guidelines for Custom Functions

## Naming
- The name of the custom function must be distinct from the built-in functions
- Name cannot end with an underscore.
	- This denotes a private function
- The name of a custom function must be declared with the proper syntax
	- `function myfunction()` **not** `var myFunction = new function()`
- Capitalization does not matter, although the names of spreadsheet functions are traditionall uppercase.

## Arguments
- Like built-in functions, a custom function can take arguments as input values.
- If you call your function with a reference to a signle cell the arugment will be the value of that cell.
- If you call you function with a reference to a range of cells as an argument, the argument will be a two-dimensonal array.

## Return Values
- Every custom function must return a value to display
- If a custom function returns a two-dimensonal array of values, the values overflow into adjacent cells as long as those cell are empty.
- Cannot affect cells other than those it reutrns a value to.
- A custom function must return within 30 otherwise cell will display an error.

