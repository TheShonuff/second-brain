---
title: Itertools
Created: 2023-10-20 23:35
tags:
  - python
aliases:
---
# Itertools
- Python offers a built-in module that provides the ability to create complex iterator manipulations.

```Python
import itertools
```

- There are three categories of itertool iterators:
	1. **Infinite** will repeate an infinite number of time. They will not raise a *StopIteration* [[Python Exceptions|exception]] and will require some type of stop condition to exit.
	2. **Input-Dependent** terminated by the input iterable(s) sequence length. The smallest length iterable parameter of an input-dependent iterator will terminate the iterator.
	3. **Cominatoric** Combinational, where mathematical functions are performed on the input iterable(s).
>[!note] A full list of functions can be found in the [documentation](https://docs.python.org/3/library/itertools.html)

## Infinite Iterator: Count
```Python
count(start,[step])
```

>[!tip] Do you stop condition check first then perform your functions

```Python
import itertools

for i in itertools.count(start=0, step=2):
	print(i)
	if i >= 20:
		break
```

## Input-Dependent Iterator: Chain
- Great for working with and modifying existing iterators.
- `chain()` method will combine multiple iterables and make the instance iterable.
```Python
chain(*iterables)
```

```Python
import itertools

odd = [5,7,9]
even = {6,8,10}

all_numbers = itertools.chain(odd,even)

for number in all_numbers:
	print(number)
```

## Combinatoric Iterator: Combinations
- Performs a set of statisical or mathematical operations on input iterable.
- `combination()` will produce an iterator of [[Tuple|tuples]] that contain combinations of all elements in the input.
```Python
combination[iterable,I]
```
>[!note] Takes two inputs. An iterable and a value *I* that represents the lenght of each combination tuple

```Python
import itertools
even = [2,4,6]
even_combinations = list(itertools.combinations(even,2))
print(even_combinations)
```
