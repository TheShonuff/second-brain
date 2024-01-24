---
tags:
  - SQL
---
# Confirming Indexes
- Confirm the existence of indexes from the USER_INDEXES data dictionary view.
- Check the columns involved in an index by querying the USER_IND_COLUMNS view

### Example
```SQL
SELECT DISTINCT ic.index_name, ic.column_name, ic.column_position, id.uniqueness
FROM user_indexs id, user_ind_columns ic
WHERE id.table_name = ic.table_name
AND ic.table_name = 'EMPLOYEES'
```
>[!note] A join between USER_INDEXES table and USER_IND_COLUMNS table


