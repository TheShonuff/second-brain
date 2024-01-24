---
tags:
  - python
---

---
Created: [[07-05-2023]]
tags: 
---
# Python List Slicing
- We can use **slice notation** to read multiple elements from a list, creating a new list that contains only the desired elements.
- `list[ Initial : End : IndexJump]`


## Common List Slicing Operations

| Operation                   | Description                                                | Example Code           |
| --------------------------- | ---------------------------------------------------------- | ---------------------- |
| `my_list[start:end]`        | Get a list from start to end (minus 1)                     | `print(my_list[0:2]`   |
| `my_list[start:end:stride]` | Get a list of every stride element from start to end       | `print(my_list[0:5:3]` |
| `my_list[start:]`            | Get a lits from start to end of the list                   | `print(my_list[2:]`    |
| `my_list[:end]`             | Get a list from beginning of the list to the end (minus 1) | `print(my_list[:4]`    |
| `my_list[:]`                | Get a copy of the list                                     | `print(my_list[:]`                       |

