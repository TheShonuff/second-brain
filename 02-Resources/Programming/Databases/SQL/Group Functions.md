---
tags:
  - SQL
---
# Group Functions
- Can operate on a whole table or on a specific grouping of rows.
- Each function returns *one result*
- The type of Group Functions:
	- **AVG** Returns avg of values *numeric data types*
	- **COUNT** Returns the number of rows *any data type*
	- **MIN** Returns minimum value *any data type*
	- **MAX** Returns maximum value *any data type*
	- **SUM** Returns total sum of values *Numeric data types*
	- **VARIANCE** Returns the spread of data around the mean *numeric data types*
	- **STDDEV** Returns standard deviation of the spread of data. *numeric data types*
>[!tip] Group functions are written in the SELECT clause

> [!warning] Group functions cannot be used in the [[WHERE]] clause

- Group functions ignore NULL values  by default.
	- [[Null Functions]] like NVL could be used to replace values.
```SQL
SELECT AVG(NVL(customer_orders, 0))
```

```SQL
SELECT AVG(NVL(commission_pct, 0))
FROM employees;
```

- There can be multiple Group Functions in a SELECT clause


