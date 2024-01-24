---
tags:
  - SQL
---
# Literal Values
- Is a fixed data value such as a character, number or date. The following examples are literal values: 
	- 'dollars' 
	- 1000 
	- 'January 1, 2009'
> [!note] Literal values can be includes in the SELECT list with the concatenation operator or as a stand-alone
 
> [! Warning] Literal values must be enclosed in a set of single quotes

### Examples
```SQl
SELECT last_name || ' has a monthly salary of ' || salary || ' dollars. ' AS pay FROM employees;
```

```SQL
SELECT last_name || ' has a ' || 1 || ' year salary of ' || salary * 12 || ' dol;ars. ' AS Pay 
FROM employees;
```



