---
tags:
  - SQL
---
# External Table
- The data rows are not held inside the database files but are found in flat file, stored externally from the database.
- Typically an external table is used to store data migrated from older versions of the databases used by a company
- 

### Example
```SQL
CREATE TABLE emp_load
	(employee_number CHAR(5),
	 employee_dob CHAR(20),
	 employee_last_name CHAR(20),
	 employee_first_name CHAR(15),
	 employee_middle_name CHAR(15),
	 employee_hire_date DATE)
ORGANIZATION EXTERNAL
	(TYPE ORACLE_LOADER
	 DEFAULT DIRECTORY def_dirl
	 ACCESS PARAMETERS
	 (RECORDS DELIMITED BY NEWLINE
	  FIELDS (employee_number CHAR(2),
				  employee_dob CHAR(20),
				  employee_last_name CHAR(18),
				  employee_first_name CHAR(11),
				  employee_middle_name CHAR(11),
				  employee_hire_date CHAR(10) date_format DATE MASK "mm/dd/yyyy"))
		LOCATION ('info.dat'));
```

