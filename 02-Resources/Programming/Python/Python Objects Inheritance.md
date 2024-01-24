---
title: Python Objects Inheritance
creation date: 2023-9-10
tags:
  - python
  - Objects
---

---
# Python Objects Inheritance
- You can get features you want from an existing class(parent) to create a new class(child) through a process called **inheritance**
- By **inheritance** you can:
	- obtain the features of a parent class
	- change the features that you don't need
	- add new features to you child class

>[!note] Every class created in Python implicity derives from object

>[!note] An explicity created class would be `MyClass(object)`

- Essentially **inheritance** is the mechanism you'll use to create hierarchies of related classes.
	- These class will all share a common interface.
	- Derived classes can specialize the interface by providing a particular implementation.
## Parent Class
- The class which we inheit is called the **Parent Class, Superclass** or **Base Class**
```Python
class Data_Professional:
	def __init__(self, name, SQL):
		self.name = name
		self.SQL = SQL
	def knows_maths_stats(self):
		return True
	def knows_programming(self):
		return True
```
>[!note] Example of parent class


## Child Class
- The new class which was created by inheriting functionalities of the parent class is called **Child Class, Derived Class** or **Sublass**
- The `__init__()` function overrides the parent class `__init__()` function
```Python
class Data_Scientist(Data_Professional):
	def __init__(self, name, SQL):
		super().__init__(name, SQL)
```
>[!note] Example of child class inheriting from Data_Professional

- `super()` is used to initialize the memebers of the base class.
- You can also just the name of the base class. `Data_Profession.__init__(self, name, SQL`
- **Abstract Base Classes** exist to be inherited, but never instantiated.
	- use leading underscores in class names to communicate that objects of that class should not be created.
	- The **abc module** in the Python standard library provides functionality to prevent creating objects from abstract base classes.

## Implementation Inheritance vs Interface Inheritance
- When you derive one class from another, the derived class inherits both:
	- **The base class interface**: The dervied class inherits all the methods, properties, and attributes of the base class.
	- **The base class implementation**: The derived class inherits the code that implements the class interface.


### Types Of Inheritance
![[Pasted image 20230909214146.png]]

## Inheriting Multiple Classes
- Python is one of the few programming languages that supporst multiple inheritance.
- **Multiple inheritance**: is the ability to derive a class from multiple base classes at the same time.