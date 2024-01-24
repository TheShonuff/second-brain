---
title: Python Classes
aliases:
  - Classes
Created: 2023-3-27
tags:
  - python
  - Objects
  - Classes
---

---

# Python Classes
- The four pillars of object-oriented programming
	1. Inheritance
	2. Abstraction
	3. Polymorphism
	4. Encapsulation
- Classes provide a means of bundling data and functionality together.
- Class definitions, like function definitions, must be executed before they have any effect.
- We define a new class by providing a name and set of method definitions.
	- The first method that all classes should provide is the [[Python Class Constructors|constructor]]
		- Which defines the way the objects are created.
- **self** is a special parameter that will always be used to reference back to the object itself.
	- **self** is always the first formal paramter

- An **object** is a grouping of data (variables) and operations that can be performed on that data (functions or methods)
- The **class** keyword can be used to create a user-defined type of object containing groups of related variables and fucntions.
- The **object** maintains a set of attributes that determines the data and behavior

## Syntax
```Python
Class ClassName(object):
	<Statement-1>
	.
	.
	.
	<Statement-N>
```
>[! note] The simplest form of class definition

- When a class definition is entered, a new namespace is created, and used as the local scope.
	- All local variables go into this namespace
### Example
```Python
class Fraction:
	def __init__(self,top,bottom):
		self.num = top
		self.den = bottom
```

```Python
myfraction = Fraction(3,5)
```
>[!note] creates an object called myfraction representing a fraction 3/5 (three-fifths)


## Class and Instance Attributes
- Classes have attributes.
	- Defined above the `__init__()`
- Instances have attributes.
	- Defined beloew the `__init__()`
	- When instantiating you need to provide values for instance attributes.