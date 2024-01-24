---
title: Python Testing
Created: 2023-10-19 20:02
tags:
  - python
aliases:
---

---
# Python Assert
- The world of testing is divided into two categories
	- **Manual Testing** A user interacts with the software manipulating results
	- **Automated Testing** Tests are performed with code. This is faster and less error prone.

## assert
- Can be used to test that a condition is met. 
- If the condition evaluates false, an **AssertionError** is raise with an optional message.
- This is a quick way to verify a program is in the correct state.

```Python
number expression[, assertion_message]
```

```Python
number = 42

assert number > 0, f"number greater than 0 expected, got: {number}"
```
