---
tags:
  - SQL
---
# NVL Null Function
NVL (express 1, substitute expression)
```SQL
SELECT country_name, NVL(internet_extension, 'None') AS "Internet Extn"
FROM wf_countries
WHERE location = 'Southern Africa'
ORDER BY internet_extension DESC;
```
- You can use *NVL function* to convert column values containing nulls to a number before doing calculations
- When an arithmetic calculation is performed with null, the result is null
- The *NVL function* can convert the null value to a number before arithmetic calculations are done to avoid a null result.
```SQL
SELECT last_name, NVL(commission_pct, 0)*250 as "Commission"
FROM employees
WHERE department_id in(89,90);
```



