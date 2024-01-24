---
tags:
  - SQL
---

# HAVING
- Used to restrict groups returned from a [[GROUP BY]] clause
- The **HAVING** clause can precede the [[GROUP BY]] clause in a SELECT statement, it is best practice to use the order shown
- ORDER BY is *always last*
> [! tip] If you use the HAVING clause without the GROUP BY clause, it works similar to a [[WHERE]] clause

- Having clause filter groups of rows
- [[WHERE]] clause filters rows

## Syntax 
```SQL
SELECT column, group_function
FROM table
WHERE
GROUP BY [group list]
HAVING [conditions]
ORDER BY
```

### Example 
```SQL
SELECT department_id, MAX(salary)
FROM employees
GROUP department_id
HAVING COUNT(*) > 1
ORDER BY department_id;
```



