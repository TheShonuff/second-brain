---
tags:
  - python
---

---
Created: [[06-25-2023]]
tags: python
---
# Python Enumerate
- The `enumerate()` function retrieves both the index and corresponding element value at the same time, providing a cleaner and more readable solution to **nested loops**.
- Yields a new [[Tuple]] each iteration of the loop.
	- Current Index
	- Corresponding element value

```Python
for count, value in enumerate(values):
	print(count, value)
```


- Sometimes you need to make adjustments based on list length.
	- `len(list) - 1` will allow to target a specific point on in the list.
	- Good for checking for the end of a list.
