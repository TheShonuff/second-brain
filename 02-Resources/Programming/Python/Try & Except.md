---
title: Try / Except
tags:
  - python
---
# Try & Except
- A form of exception handling
- Use this in [[Python For Loop|for loops]]

![[Pasted image 20231018214428 1 1.png]]
- Breaking it down
	- Python will first attempt to execture code inside the **try** clause code block
	- If no exception is encountered in the code, the `except` clause is skipped and the program continues normall
	- If an expection does occure inside the try code block, Python will immediately stop exectuing the code and begin executing the code inside the **except** code block. *Sometimes called a handler*
```Python
color = {
		 'red': 'FF0000',
		 'blue': '0000FF',
		 'yellow': 'FFFF00',
	}

for color in ('red', 'green', 'yellow'):
	try:
		print('The hex value of ' + color ' is ' + colors[color])
	except:
		print('An exception occurred! Color does not exist')
		
	print('Loop continues')
```

## Catching Specific Exceptions
- It is generally considered best practice to be as specific as possible with exceptions we want to raise unless there is a specific reason for catching any type of exception.

```Python
try:
	print(undefined_var)
except NameError:
	print("We hit a NameError")
```
>[!note] Will only execute if a **NameError** is encountered in the **try** block

```Python
try:
	print(undefined_var)
except NameError as errorObject:
	print("We hit a NameError")
	print(errorObject)
```
>[!note] **errorObject** is an arbitrary name that can be replaced with anything.

### Multiple Exceptions
- We can use a tuple to list more than one exception.

```Python
try:
	#some code
except (NamError, ZeroDivisionError) as e:
	print('We hit an Exception!')
	print(e)
```

```Python
try: 
	#some code
except NameError:
	print("name error")
except TypeError:
	print("Type error")
```

## The Else Clause
- If we want to run some code only if we do not encounter an exception.
![[Pasted image 20231018221119 1.png]]

```Python
try:
	check_password()
except ValueError:
	print("Wrong Password! Try again")
else
	login_user()
```

>[!tip] The use of the else clause is better than adding additional code to the try clause because it avoids accidentally catching an exception that wasn’t raised by the code being protected by the try … except statement.




