---
tags:
  - SQL
---
# UNIQUE Constraint
- Requires that every value in a column or set of columns (a composite key) be unique.
	- No two rows of a table can have duplicate values.
- A column or set of columns that is defined as **UNIQUE** is called a *unique key*.
- If the combination of two or more columns must be unique for every entry, that constraint is said to be a *composite unique key*.
	- No two rows in the table can have the same combination of values in the key columns.
	- Stating all combinations of email and last name must be unique is an example of *composite unique key*.
- Allows the input of nulls *unless* the column has a [[NOT NULL CONSTRAINT|NOT NULL]] constraint.
	- It will satisfy a UNIQUE constraint because nulls are not considered equal to anything.
- A primary key is also unique

>[!tip] The word "key" refers to the columns, not the constraint names.

## Defining UNIQUE Constraints
> [!tip] It's customary to use the suffic *_uk* in the constraint name

>[! warning] To define a composite unique key, you must define the constraint at the table level

## Sytanx
```SQL
CONSTRAINT constraint_name UNIQUE(value1,value2)
```
>[!note] Defining a table-level constraint

