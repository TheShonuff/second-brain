---
tags:
  - SQL
---

# Full Join
- Retreives all matching rows and all unmatched rows from both tables without duplication
- Essentially a combination of [[Left Join]] & [[Right Join]]
- The lest commonly used JOIN
- The `OUTER` keyword is optional.


![full-join | center | 400](https://www.oracletutorial.com/wp-content/uploads/2019/02/Oracle-Joins-Full-Outer-Join.png)

- To get a set of rows that are unique from the left and right tables 
	- Use a [[WHERE]] clause to exclude rows

![full-outer-join- where | center | 400](https://www.oracletutorial.com/wp-content/uploads/2019/02/Oracle-Joins-Full-Outer-Join-with-Where.png)

### Examples
```SQL
SELECT e.last_name, d.department_id, d.department_name
FROM employees e
FULL OUTER JOIN departments d ON (e.department_id d.department_id);
```


```SQL
SELECT 
	a.id id_a
	a.color color_a
	b.id id_b,
	b.color color_b
FROM
	palette_a a
FULL JOIN palette_b b ON a.color = b.color
WHERE a.id IS NULL OR b.id IS NULL;
```
>[!note] Use a WHERE clause to exclude rows from the join

