---
tags:
  - SQL
---
# NULLIF
NULLIF(epxression 1, expression 2)

```SQL
SELECT first_name, LENGTH(first_name) AS "Length FN", last_name, LENGTH(last_name) AS "Length LN", NULLIF(LENGTH(first_name), LENGTH(last_name)) AS "Compare Them" 
FROM employees;
```



