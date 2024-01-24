---
title: Dictionaries
tags:
  - python
---
# Dictionaries
- A [[Composite Data Type]]
- A Python container used to describe associative relationships
	- Generally know as associative array
- Use **Key**:*value* pairs
- Dictionaries and lists share the following characteristics:
	- Mutable
	- Dynamic
	- Can be nested
- Dictionaries differ from lists in how elements are accessed:
	- List elements are accesseded by their position via indexing
	- Dictionaries are access via keys.
- There are two ways to define a dictionary
```Python
d = dict([
		  (<key>,<value>),
		  (<key>, <value>),
		  .
		  .
		  .
		  (<key>,<value>)
])
```
```Python
MLB_team = dict({
		Colorado = "Rockies",
		Boston = 'Red Sox',
		Seattle = "Mariners"
})
```

## Finding the length of a dictionary
- The builtin method `len` can be used to find the length of a dictionary.
```Python
d = {"a":1, "b":2, "c":3}
length_key = len(d)
print(length_key)
```
## Accessing Dictionary Values
- A value is retreived from a dictionary by specifying its corresponding key in square brackets
```Python
MLB_team['Boston']
```

## Dictionary Methods
<code>d.get(key[, default])</code>
>[! tip] Default is the fallback if key is not found
```Python
d = {'a': 10, 'b': 20, 'c':30}
print(d.get('b'))
```

## Iterating A Dictionary
- A **hash** is a transformation of the key into a unique value that allows the interpreter to perform fast lookup.
```Python
for key in dictionary
```

- `dict.items()` Returns a view object that yields (key, value) tuples
- `dict.keys()` Returns a view object that yields dictionary keys.
- `dict.values` Returns a view object that yields dictionary values.

```Python
num_calories = dict(Coke = 90, Coke_zero = 9, Pepsi = 94)

for soda, calories in num_calories.items():
	print(f'{soda}: {calories}'')

for soda in num_calores.keys():
	print(soda)

for calories in num_calories.values():
	print(calories)
```