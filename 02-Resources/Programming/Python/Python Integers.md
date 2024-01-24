---
title: Python Integers
Created: 2023-09-25 19:40
tags:
  - python
aliases:
---

---
# Python Integers

## Rounding Down
- `int()` will truncate towards 0.0
- `math.floor` returns the largest integer not greater than x
	- Equivalant math expression is $x // 1$


## Rounding Up
- `math.ceil()` returns the largest integer greater than x
	- Equivalant math expression is $x//1 + 1$


## Int
- Returns an integer from a given object or converts a number in a given base to a decimal.
```Python
x = int(x,base)
```
- **X** string represenation of integer value. defaults to 0 if no value provided
- **base** base of the number (2,8,10,16)

