---
title: Time Complexity
creation date: 2022-11-26 14:13
aliases: 
tags:
  - reading
  - cs
  - filed
  - algorithms
---

# Time Complexity
- When trying to characterize an algorithms efficiency in terms of execution time, independent of any particualr program or computer, *it's important to quantify the number of operations or steps that the algorithm will require.*

It's a standard way of analyzing and comparing different algorithms. We'll need to grok [[Logarithmic Functions]] and [[Factorial Function]]

![[Pasted image 20221126145125.png]]

How does this all relate? Refer to [[Big O Examples|examples]] of how these programs are analyzed. 
![[Pasted image 20231105213917 1.png]]
## n-Notation 
- n is a function of n
- Output is a function of input
> [!note] N-notation is **not** an analysis of how long an alogrithm will take to run, but an analysis of how the algorithm wiill scale with more and more input data.

# Big O Definition 
- Order of magnitued function.
- *Counts the number of operations*
- Steps for BIG O analysis
	- Figure out what the input is and what n represents
	- Express the maximum number of operations in terms of n
	- Eliminate all excluding the highest order items.
	- Remove all constant factors.
	- [[Python Example breakdown]]

Algorithm is **0(F(n))** if the the number of simple operations the computer eventually has to do less than a constant times f(n), as n increases.

>[!tip] Chacterizes performance in terms of worst case or average case.

**0(n)** => *f(n)* could be linear (f(n)=n) *function with input n = n output runtime*
**0(n^2)** => *f(n)* could be quadratic (f(n)=n^2) *nested for loop*
**0(n)** could be constant (f(n)=1) *basic equations*

## Common Order of Magnitued Cases
| Symbol     | Description                                                                       |
| ---------- | --------------------------------------------------------------------------------- |
| O(1)       | Constant running time                                                             |
| O(log n)   | Logarithmic running time                                                          |
| O(n)       | linear running time                                                               |
| O(n log n) | Log-linear running time                                                           |
| O(n^c)     | Polynomial running time (c is constant)                                           |
| O(c^n)     | Exponential running time (c is a constant being raised to a power based on input) |
| O(n^2)     | Quadratic                                                                         |
| O(n^3)     | Cubic                                                                                  |

![[Pasted image 20230918204842.png]]
### Shorthands
- **Constant**
	- Arithmetic operations are **constant**
	- Variable assignments are **constant**
	- Primitives are **constant**
	- Accessing an element in an array by index is **constant**
	- Loops are the length of loop times complexity in a loop.
----
- **Logarithmic** 
	- Search algorithms are **logarithmic** 
	- Efficent sort algorithms are **logarithmic** 
	- Recusion algorithms are **logarithmic** (exponential)

### Constant Time: $O(1)$
- When there is no dependence on the input size.
- The program will always do the same thing regardless of input
- Complexity is always constant.

### Liner Time: $O(n)$
- when the running time of an algorithm increase lineraly with the length of the input.
- when a function runs for or iterates over an input size of n.
- *For loops in a range are a good example.*

### Logarithm Time: $O(log n)$
- When the size of the input decreases in each step by a certain factor.
	- As the input size grows, the numer of operations that need to be executed grows comparartively much slower.
- **Binary search is an example of logarithmic time complexity.**
- *seen in search algorithms*

### Quadratic Time (Polynomial): $O(n^2)$
- The performace is directly related to the squared size of the input data collection.
- **Nested for loops is an example of quadratic time complexity.**
- **Examples**: Selection sort

### Exponential Time: $O(2^n)$
- Which each addition to the input, the growth rate doubles.
- *recursive functions*

### Factorial Time: $O(N!)$





When we are trying to determine the Big O of a certain program or algorithm we take the worst case scenario. If a program has an n^2 operation and a n operation. It's assigned a big O notations of O(n^2)

![[Pasted image 20221127134036.png]]





