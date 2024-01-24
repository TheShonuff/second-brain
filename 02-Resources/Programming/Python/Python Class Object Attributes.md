---
title: Python Class Object Attributes
Created: 2023-10-07 19:56
tags:
  - python
aliases:
---

---
# Python Class Object Attributes
- Defined above the `__init__` dunder method.
- Same for any instance of a class.
	- Doesn't need self when assigning
	- Requires self when referencing.
- [[Python Class Constructors|Attribues]] are futher exampled when instaniating a method.

```Python
class Dog():
	'''
	Class Object Attribute
	Same for any instance of a class
	'''
	species = 'mammal'

	def __init__(self,breed,name,spot)
	'''
	User define attributes
	'''
	self.breed = breed
	self.name = name
	self.spots = spots
```


## Passing in Tuples or Arrays
- Assign the variable normally to the self.name = name
- Unpack or loop through the tuple or array in the method.

```Python 
class Line:
    
    def __init__(self,coor1,coor2):
        self.coor1 = coor1
        self.coor2 = coor2
    
    def distance(self):
        x1,y1 = self.coor1
        x2,y2 = self.coor2

        return ((x2-x1)**2 + (y2-y1)**2)**0.5
    
    def slope(self):
        x1,y1 = self.coor1
        x2,y2 = self.coor2
        return (y2-y1) / (x2-x1)
```
