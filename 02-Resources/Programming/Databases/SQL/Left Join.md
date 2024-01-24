---
tags:
  - SQL
---
# Left Join
- Left join or **LEFT OUTER JOIN**
- Takes all the rows from one table, defined as the *LEFT* and joins it with a second table.
- The join is based on the conditions supplied in the ON clause
- Will always include the rows from the LEFT table, even if there are no matching rows in the table it is JOINed with.
- When there is no match, the corresponding rows will use NULL to represent the missing values from the second table.
![outer-left-join | center | 400](https://www.oracletutorial.com/wp-content/uploads/2019/02/Oracle-Joins-Left-Join.png)

- Sometimes you want to get only rows form the left table. To achieve this use the [[WHERE]] clause
- The following diagram illustrate the left join with the exclusion of rows from the right table.

![left-outer-join where| center | 400](https://www.oracletutorial.com/wp-content/uploads/2019/02/Oracle-Joins-Left-Join-with-Where.png)

### Examples
```SQL
SELECT e.last_name, d.department_id, d.department_name
FROM employees e
LEFT OUTER JOIN departments d ON (e.department_id = d.department_id);
```



