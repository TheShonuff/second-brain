---
tags:
  - python
---

---
Created: [[06-25-2023]]
tags: python
---
# Python Loops


## Nested Loops
- A loop that appears as part of the body of another loop. Comprised of a:
	- **Outer loop**
	- **Innter loop**

### Example
```Python
c1 = 'a'
while c1 < 'b':
    c2 = 'a'
    while c2 <= 'c':
        print(f'{c1}{c2}', end = ' ')
        c2 = chr(ord(c2) + 1)
    c1 = chr(ord(c1) + 1)
```

- `ord()` - Takes a unit-length text as an argument and returns the unicode equivalnt of the specificed parameter
- `char()` - Takes an integer argument and returns the string representing a character 

