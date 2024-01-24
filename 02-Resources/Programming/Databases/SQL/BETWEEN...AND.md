---
tags:
  - SQL
---
# BETWEEN...AND
- The **BETWEEN** is a logical operator that allows to specify a range to test.

> [!tip] Operator is inclusive. The start and end values are included in the test

## Syntax
```SQL
column | expression BETWEEN start_expression AND end_expression
```
```SQL
column | expression NOT BETWEEN start_expression AND end_expression
```

- The **BETWEEN** operator returns *TRUE* if the expression to test is greater than or equal to the value of the *start_expression* and less than or equal to the value of the *end_expression*.
- The opposite is *TRUE* for **NOT BETWEEN**

### Examples 
```SQL
SELECT last_name, salary
FROM employees
WHERE salary BETWEEN 9000 AND 11000;
```
>[!note] Returns salaries between 9000 and 11000

```SQL
SELECT last_name, salary
FROM employees
WHERE salary >= 9000 AND salary <=11000;
```
> [!note] The **BETWEEN..AND** can be substituted for symbols.


