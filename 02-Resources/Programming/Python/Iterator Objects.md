---
title: Iterables & Iterators
Created: 2023-10-20 22:48
tags:
  - python
aliases:
---
# Iterator Objects
- A special object that represents a stream of data we can operate on.
- `iter()` is a bulit-in function
- All objects have a `__iter__` property

```Python
sku_list = [7046538, 8289407, 9056375, 2308597]

sku_iterator_object_one = sku_list.__iter__()
sku_iterator_object_two = iter(sku_list)
```
>[!note] `__iter__` and `iter()` produce the same results. An iterator object in memory


- The `__next__()` method retrieves the iterators next value.
- We can also use the `next()` built-in

```Python
sku_list = [7046538, 8289407, 9056375, 2308597]

sku_iterator = iter(sku_list)
next_sku = sku_iterator.__next__()
next_sku = next(sku_iterator)
```

>[!warning] An exception **StopIteration** will raise on the last `__next__()` call

- A [[Python For Loop|for loop]] uses the `iter()` object and calls `next()` for each iteration.

## Custom Iterators
- The `__iter__()` and `__next__()` must be implemented for an object to be an iterator object.
- The implementation of these methods is known as the **iterator protocol**
- Once these methods are implemented you can use a [[Python For Loop|for loop]] to iterate an object.

```Python
class FishInventory:
	def __init__(self, fishList):
		self.available_fish = fishList
	def __iter__(self):
		self.index = 0
		return self
	def __next__(self):
		if self.index < len(self.available_fish):
			fish_status = self.available_fish[self.index] + " is available!"
			self.index += 1
			return fish_status
		else:
			raise StopIteration
```

>[!tip] for the `__iter__` method should return self.

>[!warning] inlcude the `raise StopIteration` to prevent infinite loop

