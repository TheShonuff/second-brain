---
title: Asymptotic Notation
Created: 2023-11-05 21:13
tags:
  - algorithms
aliases:
---

---
# Asymptotic Notation
- Used to describe the runtime of a program.
- Calculating a programs runtime by looking at how many instructions the computer has to perform based on the size of the program's input: **N**
- With **Asymptotic** expressions we drop the constants -> $5N^2 + 3N +2$ -> $N^2+N$

## Big Theta $\Theta$
- Describes the runtime if the runtime of the program is the same in every case.
```Python
def some_function(list):
	for i in list:
		print(i)
```
>[!note] The program has a runtime of **N** because the program has to print a value **N** times
- The number of instructions the computer has to perform is based on how many iterations the loops will do because if the loops does more iterations, then the computer will perform the instructions.

```Python
def function(n):
	count = 0
	while n != 1:
		count += 1
		n = n/2
	return count
```
>[!note] The program has a runtime of $Log N$

## Big Omega $\Omega$
- Describes the best case scenario


## Big O
- Describes the worst case scenario.


## Adding Runtimes
```
function that takes a positive integer N:
	set a variable i equal to 1
	loop until i is equal to N:
		print i
		increment i

	set a count variable to 0
	Loop while N is not equal to 1:
		Increment count
		n = n/2
	return count
```
>[!note] $\theta(N) + \theta(log N)$
- We only care about the slowest part of the program. $\theta(N)$ is slower than $\theta(log n)$ the result would be $\theta(N)$
