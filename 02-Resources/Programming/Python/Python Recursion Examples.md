---
title: Python Recursion Examples
Created: 2023-10-02 20:25
tags:
  - python
  - algorithms
aliases:
---

---
# Python Recursion Examples

## Reverse a string
```Python
def reverse(string)
	if len(string) == 0:
		return ""
	else:
		return reverse(string[1:]) + string[0]
```

## Palindrome Checker
```Python
def is_palindrome(string):
	if len(string) <= 1:
		return True
	else:
		return string[0] == string[-1] and is_palindrome(string[1:-1])
```

