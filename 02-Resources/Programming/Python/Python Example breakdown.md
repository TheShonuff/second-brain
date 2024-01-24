---
title: Python Example breakdown
Created: 2023-09-23 20:29
tags:
  - python
aliases:
---

---
# Python Example breakdown
```Python
a = 5
b = 6
c = 10

for in in range(n):
	for j in range(n):
		x = i * i
		y = j * j
		z = i * j
for k in range(n):
	w = a * k + 45
	v = b * b
d =33
```

- The first term in the contant $3$
	- representing the three assignment statements at the beginnning. (a,b,c)
- The second term is **$3n^2$**
	- There are three statement that are performed $n^2$ times due to the nested statement.
- The third term is $2n$
	- There are two statement iterated n times.
- The fourth term in the constant $1$
	- This is the final statement in the block.
- $T(n) = 3 +3n^2 + 2n + 1 = 3n^2 + 2n + 4$
- This fragment of code is $O(n^2)$


## Linear Search breakdown
```Python
def linearSearch(L, x):
	for e in L:
		if e == x:
			return True
	return False
```
- The number of steps it will take to run **linearSearch** in the worst case $1 + 2 * n$
- The number of seps it will take for the best case is $1$


## Program 1 breakdown
```Python
def program1(x):
    total = 0
    for i in range(1000):
        total += i

    while x > 0:
        x -= 1
        total += x

    return total
```
- What is the number of steps it will take to run Program 1 in the best case $3003$
- The number of steps it will take to run Program 1 in the worst case $3003+5*n$

## Program 2 breakdown
```Python
def program2(x):
    total = 0
    for i in range(1000):
        total = i

    while x > 0:
        x = x//2
        total += x

    return total
```
- The number of steps to run in the best case $2003$
- The number of steps to run in the worst case $2008+5*log2(n)$

## Program 3 breakdown
```Python
def program3(L):
    totalSum = 0
    highestFound = None
    for x in L:
        totalSum += x

    for x in L:
        if highestFound == None:
            highestFound = x
        elif x > highestFound:
            highestFound = x

    return (totalSum, highestFound)
```
- The number of steps to run the best case $3$
- The number of steps to run in the worst case $7*n+2$

## Fact Iteration breakdown
```Python
def fact_iter(n):
"""assumes n an int >= 0"""
	answer = 1
	while n > 1:
		answer *= n
		n -= 1
	return answer
```
- The number of steps $1+5n+1$
- Worst case asymptotic complexity $O(n)$

## Exponential Complexity breakdown
```Python
def genSubsets(L):
   res = []
   if len(L) == 0:
       return [[]]
   smaller = genSubsets(L[:-1])
   extra = L[-1:]
   new = []
   
   for small in smaller:
       new.append(small+extra)
   return smaller+new
```
- $2^(n-1) + 2^(n-2)+...+2^1+1$
- Asymptotic complexity $O(2^n)$
