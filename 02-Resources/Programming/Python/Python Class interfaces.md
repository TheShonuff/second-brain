---
title: Python Class Interfaces
creation date: 2023-7-23
tags:
  - python
  - Objects
---

---
# Python Class interfaces

- Consists of the **methods** that a programmer calls to create, modoify, or access a class interface.

>[!tip] **Methods** work with an object in some way

- *Interal methods that are not accessed with start with an underscore.*
	- These are typically helper functions that assist other methods to achieve a result.
- Methods are semantically the same as functions with two differences
	- Methods are defined insaide a class definition in order to make the relationship between the class and method explicit.
	- The syntax of invoking a method is different from the syntax for calling a function.

- Procedural attribute, like a function that works only with the class
- Python always passes the actual object as the first argument
	- convention is to use **self** as the name of the first argument of all methods.
- Use the dot operator to access attribute. see [[Python Getter & Setter|Getter & Setters]]
- 


```Python
class RaceTime:
	def __init__(self, start_time, end_time, distance):
	###
	def print_time(self):
	###
	def print_pace(self):
```



