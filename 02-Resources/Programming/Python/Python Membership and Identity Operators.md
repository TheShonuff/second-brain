---
tags:
  - python
---

---
Created: [[06-15-2023]]
tags: 
---
# Python Membership and Identity Operators
- The `in` and `not in` operators are know as **membership operators**
- These will yield True or False if the left operand matches the value of an element in the right operand, which is always a container.
- They can be used with sequence types.
- They can be used to check whether a string is a substring, or matching a subset of characters, of a larger string.
- Membership in a dictionary implies that a specific key exists in the dictionary.
	- A common error is to assume that a membership operator checks the values of each dictionary key as well.

- Sometimes a you'll want to determine whether two variables are the same object.
- The identity operator `is` can check whether two operands are bound to a single object.
	- The inverse operator is `is not` 
- Identity operators do not check object values.
- Identity operators compare object identities to determine equivalence.
- Object identity is usually the memory address of an object.
- Will return True if the operands reference the same object.


