---
tags:
  - SQL
---
# Join Clauses
- Allow records from multiple statements and/or named states to be combined, based on a relationship between certain attributes in these statements.
- The *JOIN clause* modifies a **FROM** clause.
- Any number of joins can be performed in a single statement.
```SQL
FROM <statement> [alias]
	[INNER, CROSS, LEFT, RIGHT,, FULL] JOIN <statement2> [alias]
	ON (Boolean-expression) [JOIN <statementN> [alias] (Boolean-expression)]
```

[[USING Clause]] can be used to match only one column when more than one column matches.
> [!Warning] Use this clause if the join columns in both tables have the same name

[[ON Clause]] can be used to join columns that have different names.
