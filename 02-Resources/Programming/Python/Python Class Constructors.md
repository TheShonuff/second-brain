---
title: Python Class Constructor
Created: 2023-7-23
tags:
  - python
---

---
# Python Class Constructors

## Instatiation
- **Instantiation** operation is performed by "calling" the class, using paranthese like a function call as in `my_time = Time()`
	- The operation creates an instance, which is an idividual object of a given class
	- The operation automatically calls the `__init__` method that was defined.
	- A **method** is a function defined within a class.
		- The `__init__` **method** is a **constructor**.
		- Responsible for setting up the initial state of the new instance.
		- `__init__` is a **special method name**
			- indicating some special behavior of the class.
			- special methods are indicated by the double underscore.

>[!tip] The first item in the parameter list of every method is **self**

>[!tip] not all attributes need to be in the `__init__` dunder method call.

```Python
def __init__(self):
	self.data = []
```
> [! note] Automatically creates an empty array called data.

```Python
class Time:
	def __init__(self)
		self.hours = 0
		self.minutes = 0
```
>[!note] A new class containing two attributes, hours and minutes whose values are initially 0

>[!warning] We never directly invoke `__init__`

```Python
class Complex:
	def __init__(self, realpart, imagpart):
		self.r = realpart
		self.i = imagpart
```
> [!note] Assigns values to realpart and imagepart upon invocation




