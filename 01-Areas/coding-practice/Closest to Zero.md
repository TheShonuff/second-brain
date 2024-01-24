---
title: Closest to Zero
Created: 2023-12-07 21:50
tags:
  - codewars
aliases:
---

---
# Closest to Zero

## The Goal
- To analyze records of temperatures to find the closest to zero.

### Rules
- Write a program that prints the temperature closest to 0 among input data. **If two numbers are equally close to zero, positive integer hast to be cosnidered closest to zero**(for instance, if the temperatures are -5 and 5, then display 5).


## Solution
```Python
import sys
import math

n = int(input()) # the number of temperatures to analyse

temps = []

num_1 = None
num_2 = 0
for i in input().split():
# t: a temperature expressed as an integer ranging from -273 to 5526
	t = int(i)

	if num_1 is None:
		num_1 = t
		if abs(t) < abs(num_1):
			num_1 = t
		elif abs(t) == abs(num_1):
			num_2 = t

	if num_1:
		result = num_1
	else:
		result = 0
	if num_2:
		if abs(num_1) == abs(num_2):
			if num_1 > 0:
				result = num_1
			else:
				result = num_2
			else:
				result = num_1

print(result)
```


# Reflection
- This problem was was difficult due to the added complexity of having to choose the positive integer if a negative and positive exists with the positive number has to be choosen. Planning the check for this condition required planning. Even with mapping the problem out on a white board, finding the right conditionals was difficult and had to rerun each test case several times.
