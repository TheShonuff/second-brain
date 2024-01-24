---
tags:
  - SQL
---
# Concatenation
- Multiple columns can be combined using the || operator
- The CONCAT( ) function can also be used.

```SQL
SELECT first_name || ' ' || last_name FROM employees;
```


> [! tip] When values are concatenated, the resulting value is a character string.



