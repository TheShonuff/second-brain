---
tags:
  - SQL
---
# ALTER Constraints
- The ALTER statement requires:
	- The name of the table
	- The name of the constraint
	- Type of constraint
	- Name of the column affected by the constraint.

## Syntax
### ADD
```SQL
ALTER TABLE table_name
ADD [CONSTRAINT constraint_name] type of constraint (column_name)
```
- The the constraint is a [[FOREIGN KEY Constraints|FOREIGN KEY]] constraint the **REFERENCES** keyword must be included
```
ALTER TABLE table_name
ADD CONSTRAINT constraint_name FOREIGN KEY(column_name)
REFERENCES tablename(column_name)
```
- If the constraint is a [[NOT NULL CONSTRAINT|NOT NULL]] constraint, the [[ALTER TABLE]] statement uses **MODIFY** in place of *ADD*.
```SQL
ALTER TABLE table_name
MODIFY (column_name CONSTRAINT constraint_name NOT NULL);
```

### DROP
```SQL
ALTER TABLE table_name
DROP CONSTRAINT name [CASCADE]
```

### DISABLE
```SQL
ALTER TABLE table_name
DISABLE CONSTRAINT constraint_name [CASCADE]
```

### ENABLE
```SQL
ALTER TABLE table_name
ENABLE CONSTRAINT constraint_name;
```
---

### DISABALE / ENABLE
- You can use the **DISABLE or ENABLE** clause in both the [[ALTER TABLE]] and the [[CREATE TABLE]] statement.

### CASCADE
- Disables dependent integrity constraints.
- If the constraint is later enabled, the dependent constraints are not automatically enabled.

## Enabling Constraint Considerations
- If you enable a constraint, that constraint applies to all the data in the table.
- all the data in the table must fit the constraint
- If a UNIQUE or PRIMARY KEY constraint is enabled, an index is created automatically
- Enabling a PRIMARY KEY constraint that was disabled with CASCADE option does not enable any foreign keys that are depedent on the primary key.

### Examples
```SQL
ALTER TABLE employees
ADD CONSTRAINT emp_id_pk PRIMARY KEY (employee_id);
```
>[!note] Adding a [[PRIMARY KEY Constraints|PRIMARY KEY]] constraint to the employees table


