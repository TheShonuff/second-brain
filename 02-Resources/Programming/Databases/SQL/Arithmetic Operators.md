---
tags:
  - SQL
---
# Arithmetic Operators
- Calculations are possible in queries and *only appear in the output*. We can add, subtract, multiply and divide.
```SQL
SELECT last_name, salary, salary + 300 FROM employees
```
> [!note] This example would display a table with 3 columns. A last_name, a salary and a column with the salary plus 300.

> [! warning] Order of precedence applies: Multiplication, Division, Addition then Subtraction.



