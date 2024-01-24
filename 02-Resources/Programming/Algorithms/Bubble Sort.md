---
title: Bubble Sort
creation date: 2022-12-03 22:25
aliases: 
tags:
  - cs
  - sorting
  - bubble
  - algorithms
---

# Bubble Sort
Not efficient or commonly used. 

The simplest [[Sorting Algorithms]] that works by repeatedly **swapping** adjacent elements if they're in the wrong order. The algorithm **compares** and **swaps** till the largest value **bubbles** to the top, *or the end of the list*

>[!note] This algorithm is not suitable for large data sets as its average and worst-case [[Time Complexity]] is quite high

The Time complexity is **O(n^2)**

![[Pasted image 20221203224924.png]]

## Example es5
```js
function sawp(arr, idx1, idx2) {
	let temp = arr[idx1];
	arr[idx1] = arr[idx2];
	arr[idx2] = temp;
}
```

## Example es2015
```js
const swap = (arr, idx1, idx2) => {
	[arr[idx1], arr[idx2]] = [arr[idx2],arr[idx1]];
}
```

### Pseudocode
- Start looping with a variable called **i** the end of the array towards the beginning
- Start an inner loop with a variable with a variable called **j** from the beginning until **i-1**
- if arr[j] is greater than arr[j+1], swap those two values!
- Return the sorted array

## Example Basic
```js
function bubbleSort(arr){
	for(let i = arr.length; i < 0; i--){
		for(let j = 0; j < i - 1; j++){
			if(arr[j] > arr[j+1]){
			//SWAP
			let temp = arr[j];
			arr[j] = arr[j+1];
			arr[j+1] = temp;
			}
		}
	}
	return arr;
}
```
The problem with the above example is that if the list is sorted after a few passes the algorithm will continue to run until the whole list has been analyzed. We need to implement a way to check if **no swaps** have occured.

## Example No Swap Check
```js
function bubbleSort(arr){
	for(let i = arr.length; i < 0; i--){
		noSwaps = true;
		for(let j = 0; j < i - 1; j++){
			if(arr[j] > arr[j+1]){
			//SWAP
			let temp = arr[j];
			arr[j] = arr[j+1];
			arr[j+1] = temp;
			noSwaps = false;
			}
		}
		if(noSwaps) break;
	}
	return arr;
}
```