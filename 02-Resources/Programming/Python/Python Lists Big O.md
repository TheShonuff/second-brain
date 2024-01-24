---
title: Python Lists Big O
Created: 2023-09-23 21:11
tags:
  - python
aliases:
---

---
# Python Lists Big O

>[!note] Refer to [[Time Complexity]] for additional information.

- Two common operations are indexing and assigning to an index position.
	- Operations like these are indpendent of the size of the list are $O(1)$
- Another common task is to grow a list.
	- The append method is $O(1)$ 
	- The concatenation is $O(k)$ where **K** is the size of the list being concatenated


| Operation        | Big O |
| ---------------- | ----- |
| Index []         |    $O(1)$   |
| index assignment |     $O(1)$   |
| append           | $O(1)$       |
| pop()            | $O(1)$       |
| pop(i)           |      $O(n)$  |
| insert(i,item)   |     $O(n)$   |
| del operator     |       $O(n)$ |
| iteration        |       $O(n)$|
| contains(in)     |      $O(n)$ |
| get slice        |  $O(k)$     |
| del slice        |     $O(n)$  |
| set slice        |  $O(n + k)$     |
| reverse          |    $O(n)$   |
| concatenate      |   $O(k)$    |
| sort             |  $O(n log n)$     |
| multiply                 |   $O(nk)$    |

### Test script for speeds.

```Python
def test1():
	l = []
	for i in range(1000):
		l = l + [i]

def test2():
	l =[]
	for i in range(10000):
		l.appned(i)
		
def test3():
	l =[i for i in range(1000)]

def test4():
	l = list(range(1000))
```

```Python
t1 = Timer("test1()", "from __main__ import test1")
print("concat ",t1.timeit(number=1000), "milliseconds")

t2 = Timer("test2()", "from __main__ import test2")
print("append ",t2.timeit(number=1000), "milliseconds")

t3 = Timer("test3()", "from __main__ import test3")
print("comprehension ",t3.timeit(number=1000), "milliseconds")

t4 = Timer("test4()", "from __main__ import test4")
print("list range ",t4.timeit(number=1000), "milliseconds")
```

