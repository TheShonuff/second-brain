---
tags:
  - SQL
---

---
Created: [[03-20-2023]]
tags: 
---
# UNION
- This operator is used to comine the data from the result of two or more **SELECT** statements into a single distinct result set.
> [! Tip] This operator *removes any duplicates* in the result

![img|600](https://www.simplilearn.com/ice9/free_resources_article_thumb/Union_illustration-SQL_Union.PNG)

- The number of columns being retreived by each **SELECT** statement must be the same.
- Columns in the same positions should have similar data types
- Columns must be in the correct order.

> [! Tip] Results can be ordered with [[ORDER BY]]

- The [[WHERE]] clause can be used in one or both statements to filter rows.**