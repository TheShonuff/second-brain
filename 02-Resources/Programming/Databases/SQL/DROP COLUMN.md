---
tags:
  - SQL
---
# DROP COLUMN
- The following rules apply when dropping a column.
	- A column containing data may be droppped.
	- Only one column can be dropped at a time.
	- You can't drop all the columns in a table; at least one column must remain.
	- Once a column is doppped, the data values in it cannot be recovered.


## Syntax
```SQL
ALTER TABLE tablename
DROP COLUMN column name
```


### Example
```SQL
ALTER TABLE my_cd_collection
DROP COLUMN release_date;
```

## SET UNUSED
- Dropping a column from a large table can take a long time.
- A quicker alternative is to mark the column as unusable.
	- The column values remain in the database but cannot be accessed in any way, so the effect is the same as dropping the column.

```SQL
ALTER TABLE tablename SET UNUSED (column name)
```

- A drop statement can be used to target UNUSED columns.