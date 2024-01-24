---
title: Calculating Complexity
Created: 2023-09-19 20:56
tags:
  - BigO
  - time
  - complexity
  - analysis
  - algorithms
aliases:
---

# Calculating Complexity
- To determine the [[Time Complexity]] of the code, it must be examined line by line.
	- Assignments, bits, and math operators are all *basic operations*
	- Loops and nested loops
	- Recursions and function invocations.

>[!tip] When calculating, ignore the constants

```Python
for i in range(n):
	print('a')
for j in range(n*n):
	print('b')
```
>[!note] `O(n)` + `O(n*n)` = `O(n + n^2)` `O(n^2)`

```Python
for i in range(n):
	for j in range(n):
		print('b')
```
>[!note] `O(n)` x `O(n)` = `O(n*n)` = `O(n^2)` - Outer loops goes n times and inner loops goes n times



## Base of Logarithm in Big O
- It makes no difference what the logarithm base is in Big-O complexity analysis.
	- They are asymptotically the same, or differ by just a constant factor.
		- $O(log2 n)$ = $O(log10 n)$ = $O(log n)$



