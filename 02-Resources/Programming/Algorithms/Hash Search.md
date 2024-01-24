---
title: Hash Search
Created: 2023-10-09 20:10
tags:
  - algorithms
aliases:
---
# Hash Search
- Big O notation of $O(1)$
- Table size should be a [[prime number.]]
- A **hash function** is any function that can be used to map digital data of arbitrary size to digital data of fixed size.
	- Values returned by a has function are called
		- Hash Values
		- Hash Codes
		- Hash Sums
		- Hashes

## Components of Hashing
- Three major components of hashing:
	1. **Key** a string or integer that is the input fed to the hash function that determines an index or location for storage of an item in a data structure.
	2. **Hash Function** receives the input key and returns the index of an element in an array called a [[Hash Table]]. The index is known as a *hash index.* 
	3. **Hash Table** is a data structure that maps keys to values using a special function called a hash function.

- **Load Factor** how full the hash table is: $\Lambda=numOfItems/tableSize$

## Hash Functions
- A **Perfect Hash Function**
	- When we know the items and the collection will never change
	- Can also be achieved by increasing the size of the hash table so that every possible value can be accommodated.
### Division Method
- The most simple and easiesst method to generate a hash value.
- $h(K) = k MOD m$
```Python
def hash(item): return item % 11
```
- While the division method is fast the overall performance will suffer due to **clustering** of consecutive keys.

#### Remainder Method
- A similar concept to the [[#Division Method]] only we mod by the size of the list.
```Python
def hash(item, list)
	size = len(list)
	return key % size
```

### Mid Square Method
- A good hashing method for numerical values.
- Can suffer from collision
- Involves two steps to computer the hash value
	1. Square the value of the key
	2. Extract the middle x digits as the hash value.
```Python
def mid_square_hash(key, hash_table_size):
	square = key * key
	square_string = str(square)

	middle_digits = square_string[(len(square_string) // 2 - hash_table_size // 2):(len(square_string) // 2 + hash_table_size // 2)]

	return int(middle_digits)

```

### Folding Method
- This method involves two steps
	1. Divide the key-value K into a number of parts where each part has the same number of digits except for the last part that can have lesser digits than the other parts.
	2. Add the individual parts.
```Python
def folding_hash(key, hash_table_size):
	chunk_size = len(key) // hash_table_size
	chunks = [key[i:i + chunk_size] for i in range(0, len(key), chunk_size)]

	hash_value = 0
	for chunk in chunks:
		hash_value += int(chunk)
		hash_value %= hash_table_size
	return hash_value
```

### Multiplication Method
- This method involves the following steps:
	1. Choose a constant value A suce that 0 < A < 1
	2. Multiply the key value with A
	3. Extract the fractional part of kA
	4. Multiply the result of the avoe step by the size of the hast table
	5. The resulting hash value is obtained by taking the floor of the result in step 4.

## Collision
- The hashing process generates a small number for a big key, so there is a possiblity that two keys could produce the same value.
- There needs to be a way to handle newly insert key maps to an already occupied space.

### Linear Probing
- Detect if an item is already in the slot.
	- If yes, find the next slot to the right that is empty.
- Tends to cluster a lot of items in adjacent slots. **Clustering**
	- This tends to propagate and casue more collisions.

### Rehashing
- Instead of picking the next empty space, a *skip distance* can be used.
- 

### Quadratic Probing
- Adds a constant to every skip.

### Chaining
- Use linked lists to track key-value pairs that share the same hash.
- Instead of trying to store each item inside the list used for the hash table, you create a list when you insert a item. If you have a conflit at the same slot, you just add the new item (chain) to the end of the list.



