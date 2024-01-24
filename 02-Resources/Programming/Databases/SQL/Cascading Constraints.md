---
tags:
  - SQL
---
# Cascading Constraints
- Allows you to define the actions the database server takes when a user attempts to delte or update a key to which existing foreign keys point
- The **CASCADING CONSTRAINTS** clause is used along with the [[DROP COLUMN]] clause
- Drops all multicolumn constraints defined ont eh dropped columns.
- Drops all referential-integrity constraints that refer to the primary and unique keys defined on the dropped columns.

- If an [[ALTER TABLE]] statement does not include the **CASCADE CONSTRAINTS** option, any attempt to drop a primary key or multicolumn constraint will fail.

```SQL
ALTER TABLE table_name
DROP(column_name(s)) CASCADE CONSTRAINTS; 
```

