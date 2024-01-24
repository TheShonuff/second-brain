---
tags:
  - SQL
---

# COMMENT
- You can add a comment of up to 2,000 character about a column, table, or view.

## Syntax
```SQL
COMMENT ON TABLE tablename | COLUMN table.column
	IS 'place your comment here';
```

```SQL
SELECT table_name, comments
FROM user_tab_comments;
```
>[!note] viewing comments on a table

### Example
```SQL
COMMENT ON TABLE employees
	IS 'Western Region Only'
```

