---
title: Python Hash Table Class
Created: 2023-10-10 20:09
tags:
  - python
aliases:
---

---
# Python Hash Table Class
- [Tutorial](https://www.herevego.com/hashing-python/)
- `HashTable()` creates a new empty map. return: an empty map collection
- `put(key,value)` Add a new key-value pair to the map. If the key is already in the map then replace the old value with the new value.
- `get(key)` For a key, return the value stored in the map or None otherwise.

## Implementing a Hash Map Class
- collisions are handled with open addressing
### Example 1
```Python
class HashMap:
	def __init__(self,array_size):
		self.array_size = array_size
		self.array = [None for i in range(self.array_size)]
		
	def hash(self,key, count_collisions=0):
		key_bytes = key.encode()
		hash_code = sum(key_bytes)
		return hash_code + count_collisions
		
	def compressor(self,hash_code):
		return hash_code % self.array_size
		
	def assing(self, key, value):
		index = self.compressor(self.hash(key))
		self.array[index] = value
```

#### Handling Collisions in the Setter
```Python
	def assign(self,key,value):
		array_index = self.compressor(self.hash(key))
		current_array_value = self.array[array_index]
		if current_array_value is None:
			self.array[array_index] = [key,value]
			return
		if current_array_value[0] == key:
			self.array[array_index] = [key,value]
			return

		number_collision = 1
		while current_array_value[0] != Key:
			new_hash_code = self.hash(key, number_collisions)
			new_array_index = self.compressor(new_hash_code)
			current_array_value = self.array[new_array_index]
		if current_array_value is None:
			self.array[new_array_index] = [key,value]
			return
		if current_array_value[0] == key:
			self.array[new_array_index] == [key,value]
			return

		number_collisions += 1
	return
```
#### Define the Getter
```Python
	def retrieve(self,key):
		array_index = self.compressor(self.hash(key))
		return self.array[array_index]
```

#### Handling Collisions in the Getter
```python
	def retreive(self,key):
		array_index = self.compressor(self.hash(key))
		possible_return_value = self.array[array_index]
		if possible_return_value is None:
			return None
			
		if possible_return_value[0] == key:
			return possible_return_value[1]
		retrieval_collisions =1 
		while possible_return_value[0] != key:
			new_hash_code = self.hash(key, retrieval_collisions)
			retrieving_array_index = self.compressor(new_hash_code)
			possible_return_value = self.array[retrieving_array_index]
			if possible_return_value is None:
				return None
			elif possible_return_value[0] == key:
				return possible_return_value[1]
			else:
				retrieval_collisions += 1
		return
```
#### Usage
```Python
hash_map = HashMap(20)
hash_map.assign("gneiss", "metamorphic")
print(hash_map.retrieve("gneiss"))
```

### Example 4
- Code Academy project
```Python
from linked_list import Node, LinkedList
from blossom_lib import flower_definitions

class HashMap:
	def __init__(self,array_size):
	self.array_size = array_size
	self.array = [LinkedList() for i in range(self.array_size)]

def hash(self,key):
	key_bytes = key.encode()
	hash_code = sum(key_bytes)
	return hash_code

def compress(self,hash_code):
	return hash_code % self.array_size

def assign(self, key, value):
	array_index = self.compress(hash(key))
	payload = Node([key,value])
	list_at_array = self.array[array_index]

	for item in list_at_array:
		if item[0] == key:
			item[1] = value
	list_at_array.insert(payload)

def retrieve(self, key):
	array_index = self.compress(hash(key))
	list_at_index = self.array[array_index]
	for item in list_at_index:
		if item[0] == key:
		return item[1]
	else:
		return None

print(flower_definitions)

blossom = HashMap(len(flower_definitions))
for flower in flower_definitions:
	blossom.assign(flower[0], flower[1])
print(blossom.retrieve('daisy'))
```
### Example 3
```Python
class HashTable(object):
    def __init__(self, size):
        self.size = size
        self.slots = [None] * self.size
        self.data = [None] * self.size

    def put(self, key, data):
        hashvalue = self.hashfunction(key, len(self.slots))
        
        if self.slots[hashvalue] == None:
            self.slow[hashvalue] = key
            self.data[hashvalue] = data
        else:
            if self.slots[hashvalue] == key:
                self.data[hashvalue] = data

            else:
                nextslot = self.rehash(hashvalue, len(self.slots))
                while self.slots[hashvalue] != None and self.slots[hashvalue] != key:
                    nextslot = self.rehash(nextslot, len(self.slots))

                if self.slots[nextslot] == None:
                    self.slots[nextslot] = key
                    self.data[nextslot] = data

                else:
                    self.data[nextself] = data

    def hashfunction(self,key,size):
        return key%size

    def rehash(self, oldhash,size):
        return (oldhash+1)%size

    def get(self,key):
        startslot = self.hashfunction(key,len(self.slots))
        data = None
        stop = False
        found = False
        position = startslot
        while self.slots[position] != None and not found and not stop:
            if self.slots[position] == key:
                found = True
                data = self.data[position]
            else:
                position = self.rehash(position,len(self.slots))
            if position == startslot:
                stop = True
        return data

    def __getitem__(self,key):
        return self.get(key)

    def __setitem__(self,key,data):
        self.put(key,data)
    

```



### Example 4 Using Separate Chaining
```Python
class HashTable():
	def __init__(self):
		self.capacity = INITIAL_CAPACITY
		self.size = 0
		self.buckets = [None] + self.capacity

class Node():
	def __init__(self, key, value):
		self.key = key
		self.value = value
		self.next = None
```