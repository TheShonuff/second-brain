---
title: Divde and Conquer
creation date: 2022-12-10 13:41
aliases: 
tags:
  - cs
  - filed
  - algorithms
---

# Divide and Conquer
This technique can be divided into three parts.
1. **Divide**: This involves dividing the problem into smaller sub-problems.
2. **Conquer** Solve sub-problems by calling [[Recursion|recursively]] until solved.
3. **Combine**: Combine the sub-problems toi get the final solution of the whole problem.

>[!note] **Divide and Conquer** requires at there be two or more sub-problems.

## Algorithms
1. [[Quick Sort]]
2. [[Merge Sort]]
3. 

This pattern involves dividing a data set into smaller chunks and then repeating a process with a subset of data.

This pattern can tremendously decrease time complexity

## Example
Given a **sorted** array of integers, write a function called search, that accepts a value and returns the index where the value passed to the function is located. if the value is not found return -1
```js
search([1,2,3,4,5,6],4) = 3
search([1,2,3,4,5,6],6) = 5
search([1,2,3,4,5,6],11) = -1
```

### Naive Solution
```js
function search(arr, val){
	for(let i=0; i<arr.length; i++){
		if(arr[i] === val){
			return i;
		}
	}
	return -1
}
```

### Refactor
```js
function search(array, val){
	let min = 0;
	let max = array.length -1;
	while(min <= max) {
		let middle = Math.floor((min + max) /2 );
		let currentElement = array[middle];
		if(array[middle] < val){
			min = middle +1;
		} else if(array[middle] > val){
			max = middle -1l
		} else {
			return middle;
		}
	}
	return -1;
}
```