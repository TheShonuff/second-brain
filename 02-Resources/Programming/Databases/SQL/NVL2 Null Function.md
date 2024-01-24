---
tags:
  - SQL
---
 

# NVL2 Null Function
NVL2 (expression 1 (may contain a null) , expression 2 value to return if 1 is not null, epxression 3 value to replace if expression 1 is null)

> [!tip] An easy way to remember NVL2 is to think "if expression 1 has a value, substitute expression 2; if expression 1 is null, substitute expression3"

```SQL
SELECT last_name, salary, 
	NVL2(comission_pct, salary + (salary * commission_pct), salary)
	AS income
FROM employees
WHERE department_id in(80,90);
```



