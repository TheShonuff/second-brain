---
title: Python Hashing
Created: 2023-10-10 19:49
tags:
  - python
aliases:
---

---
# Python Hashing
- A hash function is any function that can be used to map data of arbitrary size to fixed-size values. [[Hash Search]]
- A [[Dictionaries|Dictionary]] is a kind of hash table.
- Example [[Python Hash Table Class]]


- By default Python uses SipHash.
```Python
hash("Hash me? no, hash you?")
4079283994117275868

hash("hi")
4550891960051040959
```
>[!note] mapped arbitrarily long string to fixed-sized integers.

