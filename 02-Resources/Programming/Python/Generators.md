---
title: Generators
Created: 2023-10-21 14:42
tags:
  - python
aliases:
---
# Generators
- Allows for the creation of [[Iterator Objects|iterators]] without having to implement the **iterator protocol**.
- Improves code readability

- There are two types of generators in Python:
	1. Generator Functions
	2. Generator Expressions

- The contents of the generator object are not store in memory.


## Yield Vs Return
- Generator functions are similar to regular functions
- The major difference is they use **yield** instead of *return*.

>[!tip] Any code written after a **yield** expression will execute on the next iteration of the iterator.

- The `yield` expression will suspend the execution of the function and preserve any local varibales that exist with the function.
- The `return` statement terminates the function immediately and return the results to the caller.

```Python

def course_generator():
	yield "Computer Science"
	yield "Art"
	yield "Business"

courses = course_generator()
for course in courses:
	print(course)
```


## Next and StopIteration
- Generator functions return an iterator object.
- `next()` can be used to retrieve the next value.
	- Causes the generator function to resume its execution until the next `yield` expression.
	- If there are no additional `yield` expression a `StopIteration` is raised.

```Python
def prize_generator():
	students_into = {
	"Joan Stark": 355,
	"Billy Mars": 45,
	"Tori Rivers": 18,
	"Kyle Newman": 25
	}

	for student in student_info:
		name = student
		id = student_info[name]
		if id % 3 == 0 and id % 5 == 0:
			yield student + " gets prize c"
		elif id % 3 == 0:
			yield student + " gets prize A"
		elif id % 5 === 0:
			yield student = " gets price B"
```
>[!note] A raffle where student whose student ID is multiple of 3 wins prize A and every student whoe ID is a multiple of 5 wins prize B. Any student whose ID is both a multiple of 3 and 5 wins prize C

## Generator Expression
- Allow for clean, single-line definition and creation of an iterator.
- There is no need to define a full generator function

```Python
a_list = [i*i for i in range(4)]

a_generator = (i*i for i in range(4))

for i in a_generator:
	print(i)
```
>[!note] `a_list` is a [[Python List Comprehensions|list comprehension]] while `a_generator` is a generator expression

>[!tip] The difference between a **list comprehension** and **generator expression** is the square brackets for parens

>[!warning] Unlike **list comprehesion** the generator object can not be accessed directly. It will need to be traversed to retrieve the values

```Python
cs_generator_exp = (f'Computer Science {i}' for i in range(1,5))
cs_generator_exp = ("Computer Science {}".format(i) for i in range(1,5))

for course in cs_generator_exp:
	print(course)
```
>[!note] generates a string with a integer

## Generator Methods: Send()
- `send()` allows to send a value to a generator using the `yield` expression.
- If `yield` is assigned to a variable the argument passed in `send()` will be assigned to that varibale.

```Python
def count_generator():
	while True:
		n = yield
		print(n)
my_generator = count_generator()
my_generator.send(3)
```

```Python
def generator():
	count = 0
	while True:
		n = yield count
		if n is not None:
			count = n
		count += 1

my_generator = generator()
print(next(my_generator))
print(next(my_generator))
print(my_generator.send(3))
print(next(my_generator))
```


## Generator Methods: Throw()
- `throw()` provides the ability to raise an exception inside the generator from the caller point.

```Python
def generator():
	i = 0
	while True:
		yield 1
		i += 1
my_generator = generator()
for item in my_generator:
	if item == 3
		my_generator.throw(ValueError, "Bad value given")
```

## Generator Methods: Close()
- `close()` is used to terminate the generator early.

```Python
def generator():
	i = 0
	while True:
		try:
			yield 1
		except GeneratorExit:
			print("Early exit, BYE!")
			break
		i += 1

my_generator = generator()
for item in my_generator:
	print(item)
	if item == 1:
		my_generator.close()
```

## Connecting Generators
- Connecting generators is similiar to [[Itertools]] `chain()` method.
- To connect generators use `yield from`

```Python
def cs_courses():
	yield "Computer Science"
	yield "Artificial Intelligence"
def art_courses():
	yield "Intro to Art"
	yield "Selecting Mediums"
def all_courses():
	yield from cs_courses()
	yield from art_courses()

combined_generator = all_courses()
```

## Generator Pipelines
- Often referred to as *nested generators*.

```Python
def number_generators():
	i = 0
	while True:
		yield i
		i += i
def even_number_generator(numbers):
	for n in numbers:
		if n % 2 == 0:
			yield n
even_numbers = even_number_generator(number_geneator())

for e in even_numbers:
	print(e)
	if e == 100:
		break
```

```Python
def course_generator():
	yield ("Computer Science", 5)
	yield ("Art", 10)
	yield ("Business", 15)
	
def add_five_students(courses):
	for course, num_students in courses:
		yield(course, num_students + 5)

increased_courses = add_five_students(course_generator())
	for course in increased_courses:
	print(course)
```
