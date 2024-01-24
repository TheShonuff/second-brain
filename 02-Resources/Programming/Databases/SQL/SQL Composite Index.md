---
tags:
  - SQL
---

---
Created: [[04-23-2023]]
tags: 
---
# SQL Composite Index
- A concatenated index.
- An index that you create on multiple columns in a table.
- Can appear in any order and need not be adjacent in the table.
- Spped retrieval of data for SELECT statements in which the [[WHERE]] clause reference all or the
- Null values are not included in the composite index.
- You can create and index on FOREIGN KEY columns, to speed up the search to match rows to the PRIMARY KEY column
- The optimizer does not use an index if the [[WHERE]] clause contains the IS NULL expression


### Example
```SQL
CREATE INDEX emps_name_idx
ON employees(first_name, last_name)
```



