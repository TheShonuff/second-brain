---
tags:
  - SQL
---

# FLASHBACK TABLE
- If a table is dropped by mistake, you may be able to bring the table and its data back.
- Each database user has his own "recycle bin" into which dropped objects are moved.

## Syntax
```SQL
FLASHBACK TABLE tablename TO BEFORE DROP;
```


>[!tip] It is possible to see which objects can be restored by querying the data dictionary view **USER_RECYCELBIN**

```SQL
SELECT original_name, operation, droptime
FROM user_recyclebin
```
>[!note] view the user_recyclebin

