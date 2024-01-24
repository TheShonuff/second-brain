---
title: Python For Loop
Created: 2023-09-20 20:23
tags:
  - python
aliases:
---

---
# Python For Loop
- The most common loop in Python
- Two types of loops
	- **Indefinite Iteration** where the number of times the loop is executed depends on how many times a condition is met
	- **Definite Iteration** where the number of times the loop will be executed is defined in advance (usually based on the collection size).
		- see [[Python Range|Range]]

>[!tip] When comparing items in a for loops **always** compare the current to the previous item.


## Checking the Next item in a loop
- Setup a condition if the end of the list is detected.
```Python
for index, num in enumerate(list):
	if index < (len(list) - 1):
		if dif something <= something_else[index + 1]:
			do_seomthing()
	else:
		break
```







