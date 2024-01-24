---
tags:
  - SQL
---

# IN
- This condition is also know as the **membership condition**. 
- This is used to test whether a value is *IN* a specified set of values.

>[!tip] Used to remove the need for multiple **OR** conditions

```SQL
SELECT city, state_province, country_id
FROM locations
WHERE country_id IN('UK', 'CA');
```
>[!note] Limits rows with country ID = UK OR CA

```SQL
SELECT city, state_province, country_id
FROM locations
WHERE country_id = 'UK' OR country_id = 'CA'
```
> [!note] Longer form of the same condition. Limit's rows with country ID = UK OR CA


