---
tags:
  - SQL
---
# MODIFY Table
- We can <code>MODIFY</code> objects in a table.

## Rules and Restrictions When Modifying
- You can increase the width or precision of a numeric column
- You can increate the width of a character column
- You can decrease the width of a NUMBER column if the column contains only NULL values, or if the table has no rows.
- For VARCHAR types, you can decrease the width down to the largest value contained in the column.
- You can change the data type only if the column contains NULL values
- You can convert CHAR column to VARCHAR2 or convert VARCHAR2 to CHAR onluy if the column contains NULL values, or if you do not change the size to something smaller than any value in the column.
- A change to the DEFAULT value of a column affects only later insertions to the table.

## Sytnax
```SQL
ALTER TABLE table_name
	MODIFY column_name DataType Constraint
```

### Examples
```SQL
ALTER TABLE persons MODIFY (
	phone VARCHAR2(20) NOT NULL,
	email VARCHAR2(255) NOT NULL
);
```

