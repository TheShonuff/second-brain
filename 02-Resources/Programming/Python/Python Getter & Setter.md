---
title: Python Getter & Setter
creation date: 2023-9-14
tags:
  - python
  - Objects
---

---
# Python Getter & Setter
- Used to add validation logic around getting a setting a value.
- Avoids direct access of a class field.
- **Getter**: A method that allows you to access an attribute in a given class
- **Setter**: A method that allows you to set or mutate that value of an attribute in a class.
- 

```Python
class Geek:
	def __init__(self, age = 0):
		self._age = age
	# Getter Method
	def get_age(self):
		return self._age
	#setter method
	def set_age(self, x):
		self._age = x

rej = Geek()

raj.set_age(21)
print(raj.get_age())
print(raj._age)
```

## Attribute Reference
- Use the standard syntax used for all attribute references in Python
	- **obj**.*name*
- Valid attribute names are all the names that were in the class's namespace whe the class object was created.

## getattr
- The `getattr()` method returns the value of the name attribute of an object. 
	- If not found, it returns the default value provided to the function.

### Syntax
```Python
getattr(object, name[, default])
```

>[!note] `object.name` is the equivalent
#### Parameters
- **Object** - object whose named attribute's value is to be returned
- **name** - string that contains the attribute's name
- **default (Optional)** - value that is returned when the named attribute is not found.

## setattr
- The `setattr()` function set the value of the attribute of an object

### Syntax
```Python
setattr(object, name, value)
```

#### Paratmeters
- **Object** - object who attribute has to be set
- **name** - attribute name
- **value** value given to the attribute