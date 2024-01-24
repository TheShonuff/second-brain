---
tags:
  - python
---

---
Created: [[06-11-2023]]
tags: 
---
# Python String Methods
- String objects have many useful methods.
	- `replace(old,new,count)` Returns a copy of the string will all occurrences of the substring old replaced by the string new an will replace the number of occurrences with count. **Count is optional**
	- `find(x)` Returns the index of the first occurrence of item x in the string
	- `find(x, start)` Returns the index of the first occurence after the start point
	- `find(x, start, end)` Returns the index of the first occurence between two points.
	- `rfind(x)` Returns the index of the first occurrence from the end of the string.
	- `count(x)` Returns the number of times x occures in the string.
- If the position is not important the `in` **membership operator** should be used to check if a character of substring is contained in the string.
```Python
If 'batman' in superhero_name
	# Statements to execute if superhero_name contains 'batman' in any position.
```
- Methods to check a string value that returns a True of False Boolean value:
	- `isalnum()` Returns true if all characters in the string are lowercase or uppercase
	- `isdigit()` Returns True if all characters are the number 0-9
	- `islower()` Returns True if all cased characters are lowercase letters
	- `isupper()` Returns True if all cased character are uppercase letters
	- `isspace()` Returns True if all characters are whitespace
	- `startswith(x)` Returns True if the string starts with x
	- `endswith(x)` Returns True if the string ends with x.

- Methods to create new strings
	- `capitalize()` Returns a copy of the string with the first character capitalized only
	- `lower()` Returns a copy of the string with all characters lowercased
	- `upper()` Returns a copy of the string with all characers uppercased
	- `strip()` Returns a copy of the string with leading and trailing whitespace removed
	- `titel()` Returns a copy of the string as a title, with first letters of words capitalized.

>[!note] it's good practice to sanitize user input



