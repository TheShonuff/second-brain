---
title: Big O Examples
creation date: 2022-11-27 14:41
aliases: 
tags:
  - cs
  - filed
  - algorithms
---
# Big O Examples
Timing our code. Some examples.

A function that calculates the sum of all number from 1 up to and including some number n.

Using a For Loop
```js
function addUpTo(n) {
	let total = 0;
	for (let i = 1; i <= n; i++) {
		total += 1;
	}
	return total;
}
```

Using a formula
```javascript
function addUpTo(n) {
	return n * (n + 1) / 2;
}
```

Comparing these two solutions to the same problem, what does better mean?
- faster?
- less mememory-intensive?
- readablity? 
It's best to count the number of simple operations the computer has to perform. 

Using the formula solution there are 3 operations in total. Therefore it's a constant 0(1). There is always 3 operations.

The for loop loop solution has  n number of additions and n assignments for the total variable inside the for loop. The i++ has n number of assignments and additions. There are then 2 assignments for total and i. There is also a comparison operator. A way to look at this operation would be as low as 2n or a s high as 5n+2. The number of operations grows roughly proportionally with n.

Therefore the number of operations is bounded by a multiple of n. 0(n)

Another example of nested for loops. 

```js
function printAllPairs(n) {
	for (var i = 0; i < n; i++) {\
		f0r (var j = 0; j < n; j++){
			 console.log(i,j);
		}
	}
}
```

This example has O(n) operation inside of an O(n) operation. Therefore it's O(n^2). 


