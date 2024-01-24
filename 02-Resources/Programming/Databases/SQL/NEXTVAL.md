---
tags:
  - SQL
---
# NEXTVAL
- Pseudocolumn used to extract successive sequence numbers from a specified squence.
- Must be qualified with the sequence name.
- When reference a new sequence number is generated and the current sequence number is placed in CURRVAL

## Viewing the Next Value
- If the sequence was created with NOCACHE, it is possible to view the next available sequence value without incrementing it by querying the USER_SEQUENCES table.

### Example
```SQL
INSERT INTO departments
	(department_id, department_name, location_id)
VALUES
	(department_seq.NEXTVAL, 'Support', 2500)
```


```SQL
SELECT sequence_name, min,value, max_values, last_number AS "NEXT number" 
FROM USER_SEQUENCES
WHERE sequence_name = 'RUNNER_ID_SEQ'
```
>[!note] Viewing the next value query

>[!warning]  if any SQL queries contains references to both CURRVAL and NEXTVAL, then Oracle increments the sequence and returns the same value for both CURRVAL and NEXTVAL regardless of their order in the statement.
