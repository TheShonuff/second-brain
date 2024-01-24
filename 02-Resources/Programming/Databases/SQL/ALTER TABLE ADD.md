---
tags:
  - SQL
---
# ALTER TABLE ADD
- The most common operation in the <code>ALTER TABLE</code> statement is to add an object.


## Syntax
```SQL
ALTER TABLE <table_name>
ADD <column_name> DataType Constraint
```

```SQL
ALTER TABLE tablename
ADD (column name data type [DEFAULT expression],
	column name data type [DEFAULT expression],..);
```

### Examples
```SQL
ALTER TABLE persons
ADD birthdate DATE NOT NULL;
```
>[!note] Add a birthdate column with a data type of DATE

