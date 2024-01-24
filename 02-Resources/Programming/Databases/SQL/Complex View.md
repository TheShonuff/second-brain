---
tags:
  - SQL
---

# Complex View
- Views that can contain group functions and joins.


### Examples
```SQL
CREATE OR REPLACE VIEW view_euro_countries
	("ID","Country", "Capitol City", "Region")
AS SELECT c.country_id, c.country_name, c.capitol, r.region_name
	FROM wf_countires c JOIN wf_world_regions r
	USING (region_id)
	WHERE location LIKE '%Europe';
```
>[!note] Creates a complex view derived from two tables

```SQL
SELECT * FROM view_euro_countries
```


```SQL
CREATE OR REPLACE VIEW view_high_pop
	("REGION ID", "Highest Population")
AS SELECT region_id, MAX(population)
	FROM wf_countires
	GROUP BY region_id;
```
>[!note] Complex view created using a group function

```SQL
SELECT * FROM view_high_pop
```
