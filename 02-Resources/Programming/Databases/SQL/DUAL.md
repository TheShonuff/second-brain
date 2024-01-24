---
tags:
  - SQL
---
# DUAL
- The **DUAL** table is used to create SELECT statements and execute functions not directly related to a specific database table.
- These queries return one row as a result.

> [!tip] Useful to do calculations and also to evaluate expressions that are not derived from a table.

```SQL
SELECT (319/29) + 12
FROM DUAL
```



