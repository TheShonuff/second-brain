---
tags:
  - python
---

---
# Python List Comprehensions
- Iterates over a list, modifies each element, and returns a new list of the modified elements.
```Python
new_list = [expression for loop_variable_name in iterable]
```

```Python
my_list = [10, 20, 30]
list_plus_5 = [(i+5) for i in my_list]

print(f'New List contains: {list_plus_5}')
```

- This can replace some **for loops** and produce more efficient code.
- Not an exact replace because it creates a new list object whereas the typical for loop modifies the list in-place.
### Examples
```Python
numbers = [i for i in x if i < 0]
```
>[!note] Only negative values from list x

```Python
numbers = [i for i in x if i < 0 and i % 2 != 0]
```
>[!note] Only negative odd values from the list x

