---
tags:
  - SQL
---
# COALESCE
COALESCE (expression 1, expression 2, ... expression n)

```SQL
SELECT last_name, COALESCE(commission_pct, salary, 10) AS "comm"
FROM employees
ORDER BY commission_pct;
```



