---
title: Python Super
creation date: 2023-9-15
tags:
  - python
  - Objects
---

---
# Python Super
- `super()` gives you access to methods in a **super class** from the **subclass** that inherits from it.
	- Calling previously built methods with the `super()` saves from needing to rewrite methods in the subclass.

>[!tip] You **do not** need to apply self to the arguments list

```Python
class School(object):

	def __init__(self,name, level, number_of_students):
		self.name = name
		self.level = level
		self.number_of_students = number_of_students
	  
	def get_level(self):
		return self.level
	
	def get_name(self):
		return self.name
	
	def get_num_students(self):
		return self.number_of_students

	def set_num_students(self, new_num):
		self.number_of_students = new_num

	def __repr__(self):
		return f'a {self.level} named {self.name} with {self.number_of_students} students'


class PrimarySchool(School):
	def __init__(self, name, number_of_students, pick_up_policy):
		super().__init__(name, "primary", number_of_students)
		self.pick_up_policy = pick_up_policy

	def get_pick_up_policy(self):
		return self.pick_up_policy

	def __repr__(self):
		return f'a {self.level} named {self.name} with {self.number_of_students} students with a {self.pick_up_policy}'
```
## Benifits of Super
- Need not remember or specify the parent class name to access its methods.
- Implements modularity and code reusability
- Super function is called dynamically.


## In Single Ineritance
- 



