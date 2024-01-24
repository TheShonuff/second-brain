---
tags:
  - SQL
---

---
Created: [[02-26-2023]]
tags: 
---
# SQL Data Types
- There are several different data types.
### **CHAR**
Used for text and *character data of fixed length*, including numbers, dashes, and special characters
>[!warning] Will fill the space with trailing spaces to fill upto the specified value

### **VARCHAR2**
Used for *character data of variable length*, including numbers, dashes and special characters
- When you create a table with a VARCHAR2 column you specify a maximum column length (in bytes **not characters**) between 1 and 2000.

### **VARCHAR**
Synonymous with VARCHAR2

### **NUMBER**
- Used to store *variable-length numeric data*. No dashes, text, or other non numeric data are allowed.
- Stores fixed and floating point numbers.
- Up to 38 digits of precision.
> [!note] Currency is stored as number data type.

### **DATE**
Used for date and time values. Internally, Oracle stores dates as numbers. 
- Stores a 'point-in-time' value.
> [!note] by default, DATE information is displayed as DD-MM-YYYY
- Can store a value of centures down to whole seconds bu cannot store fractions of a second.
- **TIMESTAMP** data type is an extension of the **DATE** data type which allows fractions of a second.
- **TIMESTAMP WITH TIME ZONE** stores a time zone value as a displacement from the UCT
- **TIMESTAMP WITH LOCAL TIME ZONE** the time is automatically converted to the selecting users TIME ZONE
- **INTERVAL** stores the elapsed time, or interval of time, between to date-time values
	- **INTERVAL YEAR TO MONTH** a period of time measured in years and months
	- **INTERVAL DAY TO SECOND** a period of time measured in days, hours, minutes, and seconds

### **LONG**
Can store variable-length character data containing up to two gigabytes of information.
- Long data is text data.

### RAW & BLOB
- for binary values (eg. multimedia: jpg, wav, mp3... etc)
- **RAW** variable size, maximum 2000 bytes
- **BLOD** variable size, maximum 128 terabytes