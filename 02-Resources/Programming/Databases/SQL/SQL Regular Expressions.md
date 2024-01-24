---
tags:
  - SQL
---
# SQL Regular Expressions
- Method of describing simple and complex patterns for searching and manipulating.
- Based on the use of meta characters.
	- Special characters that have a special meaning, such as wildcard, a repeating character, a non-matching character, or a range of characters.
	- Several predefined meta character symbols in the pattern matching
- Can be used as part of the application code to ensure only valid data is stored in the database.
	- It's possible to call a REGEX function in a [[CHECK]] constraint


| Symbol | Description                                                                                      |
| ------ | ------------------------------------------------------------------------------------------------ |
| .(dot) | Match any character in the supported character set, expect NULL                                  |
| ?      | Matches zero or one occurrence                                                                   |
| *      | Matches zero or more occurrences                                                                 |
| +      | Matches one ore more occurrences                                                                 |
| ( )     | Grouping expression                                                                              |
| \      | Escape character                                                                                 |
| \|     | Alternation operator for specifying alternative matches                                          |
| ^/$    | Matches the start-of-line/end-of-line                                                            |
| [ ]     | Bracket expression for matching list matching any one of the expressions represented in the list |

## Functions
| Name           | Description                                                                                                                                                 |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| REGEXP_LIKE    | Similar to the LIKE operator, but performs regular expression matching instead of simple pattern matching                                                   |
| REGEXP_REPLACE | Searches for a reqular expression pattern and replaces it with a replacement string                                                                         |
| REGEXP_INSTR   | Searches for a given string for a regular expression pattern and returns the position where the match is found                                              |
| REGEXP_SUBSTR  | Searches for a regular expression pattern within a given string and returns the matched substring                                                           |
| REGEXP_COUNT   | Returns the number of times a pattern appears in a string. You specify the string and pattern. You can also specify the start position and matching options |

### Example
```SQL
SELECT first_name, last_name
FROM employees
WHERE REGEXP_LIKE(first_name, '^Ste(v|ph)en$')
```
>[!note] RegEX to list all employees with a first name of Stephen or Steven

```SQL
SELECT last_name, REGEXP_REPLACE(last_name, '^H(a|e|i|o|u)', '**')
	AS "Name Change"
FROM employees;
```

```SQL
ALTER TABLE employees
ADD CONSTRAINT email_addr_chk
CHECK(REGEXP_LIKE(email.'@'))
```
>[!note] Ensure no email address is added without the @ symbol