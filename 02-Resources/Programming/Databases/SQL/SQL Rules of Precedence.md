---
tags:
  - SQL
---

---
Created: [[02-07-2023]]
tags: 
---
# SQL Rules of Precedence
- The [[WHERE]] statement has a set order of precedence when evaluating operators

| order | operators                    |
| ----- | ---------------------------- |
| 1     | Arthmetic                    |
| 2     | Concatenation                |
| 3     | Comparison                   |
| 4     | IS(NOT) NULL, LIKE, (NOT) IN |
| 5     | (NOT) BETWEEN               |
| 6     | NOT                          |
| 7     | AND                          |
| 8     | OR                             |


> [!tip] Adding parenthesis changes the way the WHERE clause is evaluated, and the rows returned.


