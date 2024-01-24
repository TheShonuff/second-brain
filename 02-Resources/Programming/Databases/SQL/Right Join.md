---
tags:
  - SQL
---
# Right Join
- Similar to a [[Left Join]] execpt the roles between tables are reversed.
- **RIGHT OUTER JOIN**
- All rows on the second table are included along with any matching rows from the first table.

![right-outer-join | center | 400](https://www.oracletutorial.com/wp-content/uploads/2019/02/Oracle-Joins-Right-Join.png)

- You get only rows from the right table but not the left table by adding a [[WHERE]] clause
![right-outer-join-where | center | 400](https://www.oracletutorial.com/wp-content/uploads/2019/02/Oracle-Joins-Right-Join-with-Where.png)
### Example
```SQL
SELECT e.last_name, d.department_id, d.department_name
FROM employees e
RIGHT OUTER JOIN departments d ON (e.department_id = d.department_id);
```

