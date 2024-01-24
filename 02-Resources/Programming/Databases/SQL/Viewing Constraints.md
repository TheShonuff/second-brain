---
tags:
  - SQL
---
# Viewing Constraints
- After creating a table you can confirm its existence by issuing a **DESCRIBE** command.
- The only constraint that you can verify using **DESCRIBE** is the [[NOT NULL CONSTRAINT|NOT NULL]] constraint.
- [[NOT NULL CONSTRAINT|NOT NULL]] constraint also appears in the [[Data Dictionary]] as a [[CHECK]] constraint.
- To view all constraints on your table, query the <code>USER_CONSTRAINTS</code>

```SQL
SELECT constraints_name, table_name, constraint_type, status
FROM USER_CONSTRAINTS
WHERE table_name = 'COPY_EMPLOYEES';
```

## Constraint Types are
- **P** Primary Key
- **R** References (foreign key)
- **C** Check
- **U** UNIQUE


