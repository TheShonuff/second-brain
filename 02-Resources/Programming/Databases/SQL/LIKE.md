---
tags:
  - SQL
---
# LIKE
- This condition allows the selection of rows that match either characters, dates, or a number of patterns.

> [!tip] This is considering PARTIAL MATCHING

## Syntax
```SQL
column | expression LIKE pattern [ESCAPE escape_character]
```
```SQL
column | expression NOT LIKE pattern [ESCAPE escape_character]
```

#### Pattern 
- A sequence of character to search for in the column or expression.
	- The percent wildcard **%** matches any string of zero or characters.
	- The underscore matches any single character
	- A list of characters can be used to match a signle character
	- The carrort **^** will match any single character not within a list or range.

### Examples
> [! tip] '\_ara' would find *Sara*, *Tara*, but not **Clara** 

```SQL
SELECT last_name
FROM employees
WHERE last_name LIKE 'z%'
```
>[!note] Will find any employee whose name starts with **z**

```SQL
SELECT last_name
FROM employees
WHERE last_name LIKE '%er'
```
> [!note] will find any employee whose last name ends with **er**

```SQL
SELECT last_name
FROM employees
WHERE last_name LIKE 't%s'
```
> [!note] Will find any employee who last name starts with **t** and ends with **s**

```SQL
SELECT last_name
FROM employees
WHERE last_name LIKE '_o%';
```

```SQL
SELECT last_name
FROM employees
WHERE last_name LIKE '_u%'
```
>[!note] Will find any employee whose last name's second character is **u**

