---
title: Horse-Racing Duals
Created: 2023-12-16 23:01
tags:
  - codewars
aliases:
---
# Horse-Racing Duals

## Problem
Casablanca’s hippodrome is organizing a new type of horse racing: duals. During a dual, only two horses will participate in the race. In order for the race to be interesting, it is necessary to try to select two horses with similar strength.  
  
Write a program which, using a given number of strengths, identifies the two closest strengths and shows their difference with an integer (≥ 0).

## Solution
```Python
nums_list = []
n = int(input())
for i in range(n):
	pi = int(input())
	nums_list.append()

nums_list.sort()
current_diff = nums_list[-1]

for index, num in enumerate(nums_list):
	if index < (len(nums_list) - 1):
		if abs(num - nums_list[index+1]) < current_diff:
			current_diff = abs(num - nums_list[index + 1])
	else:
		break
```


## Reflection
- I initially got this problem using a nested for-loop. The third test case had 10,000 horses and the current algorithm wasn't effiecent enough to handle this. The better solution was to use one for-loop and look at the sorted list in pairs.
