---
title: The @property Decorator
Created: 2023-10-17 20:58
tags:
  - css
  - webdev
aliases:
---

# The @property Decorator
- Python [[Python Getter & Setter|getters and setters]] are useful tools for achieving encapsulation.

### Basic example
```Python
class Box:  
  def __init__(self, weight):  
    self.__weight = weight  
  
  def getWeight(self):  
    return self.__weight  
  
  def setWeight(self, weight):  
    if weight >= 0:  
      self.__weight = weight
```
>[!note] Box has one private attribute called weight. with a getter `getWeight` and setter `setWeight`.


## Built-in property() function
- The `property()` function accepts four optional arguements
	1. fget
	2. fset
	3. fdel
	4. doc

```Python
class Box:
  def __init__(self, weight):
    self.__weight = weight

  def getWeight(self):
    return self.__weight
 
  def setWeight(self, weight):
    if weight >= 0:
      self.__weight = weight

  def delWeight(self):
    del self.__weight

  weight = property(getWeight, setWeight, delWeight, "Docstring for the 'weight' property")
```

```Python
class Box:
 def __init__(self, weight):
   self.__weight = weight

 @property
 def weight(self):
   """Docstring for the 'weight' property"""
   return self.__weight


 @weight.setter
 def weight(self, weight):
   if weight >= 0:
     self.__weight = weight

 @weight.deleter
 def weight(self):
   del self.__weight
   
'''
box = Box(10)  
  
print(box.weight) #this calls .getWeight()  
  
box.weight = 5 #this called .setWeight()  
  
del box.weight #this calls .delWeight()  
  
box.weight = -5 #box.__weight is unchanged
'''
```
