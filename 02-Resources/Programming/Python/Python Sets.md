---
title: Python Set
Created: 2023-09-29 21:20
tags:
  - python
aliases:
---

---
# Python Sets
- Offical [Documentation](https://docs.python.org/2/library/sets.html)
- A collection of unordered and unique values. 
- Cannont contain duplicates.
- Does not support indexing, slicing or other sequence behavior.
- Can contain multiple data types
- Store multiple values in curly braces
- Can be created using the `set()` constructor

>[!tip] A set is unordered. Printing a set will not return the order you set

## Creating a Set
- Can be created by
	- passing an iterable object into its constructor
	- using set comprehension

```Python
country_set = set(("USA", "Ukraine", "Nigeria", "Ghana"))
country_set2 = {"USA", "Ukraine", "Nigeria", "Ghana"}
```

```Python
item = ["country", "punk", "rock", "techno", "pop", "latin"]

music_genres = {category for category in items if category[0] == 'p'}
print(music_genres)
```
>[!note] Set created using set comprehension


## Adding to a Set
- `add()` will add a signle element
- `update()` will add multiple elements

## Removing From a Set
- `remove()` will delete one element.
	- will raise a *KeyError* if not present
- `discard()` will delete one element and does not raise an exception.

## Frozenset
- Can only be created using a constructor.
- You cannot modify the elements inside 
```Python
empty_frozen_music_genres = frozenset()
frozen_music_genres = frozenset(['country', 'punk', 'rap', 'techno', 'pop', 'latin'])
```

## Finding Elements in a Set
- Items cannot be accessed by a spcific index.
- Use the **in** keyword to search a set.