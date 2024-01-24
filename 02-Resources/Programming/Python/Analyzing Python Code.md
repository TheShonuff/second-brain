---
title: Analyzing Python Code
Created: 2023-09-18 20:19
tags:
  - python
  - algorithms
aliases:
---
# Analyzing Python Code
- We can use [[Time Complexity]] and [[Space Complexity]] to analyze code.
- In Python we can bencmake a function by noting the starting time and ending time with respect to the system.
	- The `time` module includes a function called `time`
		- Returns the current system clock time.
		- Calling the function twice, before and after we can calculate the difference to get an exact number of seconds.

```Python
import time

def sumOfN2(n):
	start = time.time()

	theSum = 0
	for i in range(1, n+1):
		theSum = theSum + 1

	end = time.time()

	return thesume, end - start
print("Sum is %d required %10.7f seconds"%SumOfN2(100000))
```
>[!note] times being called and calculated in the return tuple.

>[!tip] The benchmark measurement is useful but not meaningful. Can't fully judge the algorithm alone. 





