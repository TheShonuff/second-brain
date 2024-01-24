---
title: Python Exceptions
Created: 2023-10-18 20:32
tags:
  - python
  - error-handling
aliases:
---

---
# Python Exceptions
- Runtime errors
![[Pasted image 20231018203333.png]]
- Python offers a tool for gaining insight into exceptions with **traceback**.

## Built-in Exceptions
- Exception are objects that inherit directly from a class called *Exception*.
- They are all dervied directly or indirectly from the **BaseException** class.
```Python
print(NameError.__bases__)
print(Exception.__bases__)
```
>[!note] Call to examine to base classess by using the `__bases__`

## Raising Exceptions
- We can throw an exception at anytime using the **raise** keyword.
- Any of the built-in expcetions can be used
- A custom exception can be created using **Exception**
```Python
def open_register(employee_status):
	if employee_status == "Authorized"
		print("Successfull opened cash register")
	else:
		raise Exception('Employee does not have access!')
```


- We can handle exceptions without breaking the application using [[Try & Except]]
- 