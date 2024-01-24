---
tags:
  - python
---

# DictReader
- Creates an object that operates like a regular reader but maps the information in each row to a dict whose keys are given by the optional fieldnames paramter.

## Syntax
```Python
csv.DictReader(file, fieldnames=None, restkey=None, restval=None, dialect='excel', *args, **kwds)
```

### Example
```Python
import csv
with open('people.csv', 'r') as file:
	csv_file = csv.DictReader(file)
	for row in csv_file:
		print(dict(row))
```

