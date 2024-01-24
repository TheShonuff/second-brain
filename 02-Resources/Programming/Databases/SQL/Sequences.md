---
tags:
  - SQL
---
# Sequences
- Automatically generate unique numbers
- A shareable Database object
- Typically used to create a primary-key value.
- Stored and generated independently of tables.
- The same sequence can be used for multiple tables.

## Syntax
```SQL
CREATE SEQUENCE sequence
	[INCREMENT BY n]
	[START WITH n]
	[{MAXValue n | NOMAXVALUE}]
	[{MINVALUE n | NOMINVALUE}]
	[{CYCLE | NOCYCLE}]
	[{CACHE n | NOCACHE}]
```


| Name         | Description                                                                                                                            |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| sequence     | The name of the sequence generator                                                                                                     |
| INCREMENT BY | Specifies the interval between sequence numbers where n is an integer, if omitted the sequence is incremented by                       |
| START WITH   | Specifies the first sequence number to be generated, if omitted the sequence starts with 1                                             |
| MAX VALUE    | Specifies the maximum value the sequence can generate                                                                                  |
| NOMAXVALUE   | Specifes a maximum value of 10^27 for an ascending seqeunce and -1 for descending sequence(Default)                                    |
| MINVALUE     | Specifies the minimum sequence value                                                                                                   |
| NOMINVALUE   | Specifies a minimum value of 1 for ascending sequence and -(10^26) for descending sequence (default)                                   |
| CYCLE        | Specifies whether the sequence continues to generate values after reaching its maximum or minimum value(NOCYCLE is the default option) |
| CACHE        | Specifies how many values the Oracle server pre-allocates and keeps in memory( BY default, the Oracle server caches 20 values) If the system crashes, the values are lost.                                                                                                                                       |

>[!warning] Don't use CYCLE option if the sequence is used to generate primary-key values unless there is a reliable mechanism that deletes old rows faster than new ones are created.

### Example
```SQL
CREATE SEQUENCE runner_id_seq
	INCREMENT BY 1
	START WITH 1
	MAXVALUE 50000
	NOCACHE
	NOCYCLE;
```

## Confirming Sequences
- To verify that a sequnce was created, query the USER_OBJECTS data dictionary.
- To see all the of the sequence settings, query the USER_SEQUENCES data dictionary 
- If no NOCACHE is specified, the last_number column in the query displays the next available sequence number.
- if CACHE is specifed, the last_number column displays the next available number in the sequence which has not been cached into memory.

```SQL
SELECT sequence_name, min_value, max_value, increment_by, last_number FROM user_sequences;
```

## Modifying a Sequence
- Some validation is performed when you alter a sequence.
	- Altering a sequence with a MAX  VALUE less than what was intially created would create an error.

## Guidlines
- A few guidlines apply when executing an ALTER SEQUENCE statement:
	- You must be the owner or have ALTER privilege for the sequence
	- Only future sequence numbers are affected by the ALTER SEQUENCE statement
	- The START WITH option cannot be changed using the ALTER SEQUENCE. 
		- The sequence must be droppped and re-created in order to restart the sequence at a different number

## Removing a Sequence
- To remove a sequence from the data dictionary, use the DROP SEQUENCE statement
- You must be the owner of the sequence or have DROP ANY SEQUENCE privileges
- Once removed the sequence can no longer be reference

```SQL
DROP SEQUENCE runner_id_seq
```