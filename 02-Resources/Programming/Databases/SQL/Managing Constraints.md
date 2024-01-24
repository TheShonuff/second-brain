---
tags:
  - SQL
---
# Managing Constraints
- The [[ALTER TABLE]] statement is used to make changes to constraints in existing tables.
- These changes can include:
	- Adding constraints
	- Dropping constraints
	- Enabling or Disabling constraints
	- Adding a [[NOT NULL CONSTRAINT|NOT NULL]] constraint
	
>[!warning] You can add, drop, enable, disable a constraint, but you cannot modify its structure.

>[!tip] You can add a [[NOT NULL CONSTRAINT|NOT NULL]] constraint to an existing column by using the **MODIFY** clause of the [[ALTER TABLE]] statement

>[!warning] You can define a [[NOT NULL CONSTRAINT|NOT NULL]] constraint only if the table is empty or if the column contains a value for every row.







