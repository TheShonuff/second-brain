---
tags:
  - python
---
# DictWriter
- Creates an object which operates like a regular writer but maps dictionaries onto output rows.

## Syntax
```Python
csv.DictWriter(filename, fieldname, restval='', extrasection='raise', dialect='excel', *args, **kwds)
```

### Example
```Python
import csv

with open('players.csv', 'w', newline='') as file:
    fieldnames = ['player_name', 'fide_rating']
    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()
    writer.writerow({'player_name': 'Magnus Carlsen', 'fide_rating': 2870})
    writer.writerow({'player_name': 'Fabiano Caruana', 'fide_rating': 2822})
    writer.writerow({'player_name': 'Ding Liren', 'fide_rating': 2801})
```

