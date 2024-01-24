---
tags:
  - SQL
---
# Substitution Variables
- Are variables that hold a value
```SQL
SELECT first_name, last_name, salary, department_id
FROM employees
WHERE department_id = 10;
```

An alternative is

```SQL
SELECT first_name, last_name, salary, department_id
FROM employees
WHERE department_id=:enter_dept_id;
```

>[!tip] The use of the colon is the trick to making **substitution variables** work

While using APEX this will create a pop-up window that will prompt for a value to be entered.

> [!tip] Substituation variables are treated as *character strings*.

