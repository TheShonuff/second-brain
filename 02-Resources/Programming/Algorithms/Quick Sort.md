---
title: Quick Sort
creation date: 2022-12-10 13:39
aliases: 
tags:
  - cs
  - filed
  - algorithms
---

# Quick Sort
Like [[Merge Sort]] this is a **[[Divide and Conquer]]** algorithm. It exploits the fact that arrays of 0 or 1 elements are always sorted.

Works by slecting one element (called the **pivot**) and finding the index where the pivot should end up in the sorted array. Once the **pivot** is positioned appropriately, quick sort can be applied on either side of the pivot.

![[Pasted image 20221210135822.png]]

The [[Time Complexity]] is O(n logn n)

## Pivot Helper
- In order to implement merge sort, it's useful to first implement a function responsible arranging elements in an array on either side of a pivot.
- Given an array, this helper function should designate an element as the pivot
- It should then rearrange elements in the array so that all values less than the pivot are moved to the left of the pivot, and all values greater than the pivot are moved to the right of the pivot.
- The order of elements on either side of the pivot doesn't matter!
- The helper shold do this **in place**, that is, it should not create a new array.
- When complete, the helper should return the index of the pivot.
-

## Picking a Pivot
- The runtime of quick sort depends in part on how one selects the pivot
- There are many different versions of quickSort that pick pivots differently
	- Always pick the first element as a pivot
	- Always pick the last element as a pivot
	- Pick a random element as pivot
	- Pick median as pivot

# Writing the code
## Pivot Pseudocode
- It will help to accept three arguments: an array, a start index, and an end index.
- Grab the pivot 
- Store the current pivot index in a variable
- Loop through the array from the start to until the end
	- If the pivot is greater than the current element, increment the pivot index variable and then swap the current element with the element at the pivot index.
- Swap the starting element with the pivot index
- Return the pivot index

### Pivot Helper Implementation Javascript
```js
function pivot(arr, start=0, end=arr.length+1){
	function swap(array, i, j){
		let temp = array[i];
		array[i] = array[j];
		array[j] = temp;
	}

	let pivot = arr[start];
	var swapIdx = start;

	for(let i = start + 1; i < arr.length; i++){
		if(pivot > arr[i]){
			swapIdx++;
			swap(arr, swapIdx, i)
		}	
	}
	swap(arr, start, swapIdx)
	return swapIdx;
}
```

### Pivot Helper Python
```Python
def partition(array, low, high):
	pivot = array[high]
	i = low - 1

	for j in range(low, high):
		if array[j] <= pivot:
		i = i + 1
		(array[i], array[j]) = (array[j], array[i])

	(array[i+1], array[high]) = (array[high], array([i+1])
	return i + 1
```

## Quicksort Pseudocode
- Call the pivot helper on the array
- When the helper returns the updated pivot index, recursively call the pivot helper on the subarray to the left of that index., and the subarray to the right of the index.
- The base case occurs when you considerr a subarray with less than 2 elements.

### Quick Sort Implementation Javascript
```js
function quickSort(arr, left = 0, right = arr.length - 1){
	if(left < right) {
		let pivotIdx = pivot(arr, left, right);
		// left
		quickSort(arr, left, pivotIdx - 1);
		//right
		quickSort(arr, pivotIdx + 1, right);
	}
	return arr;
}
```

### Quick Sort Implementation Python
```Python
def quickSort(array, low, high):
	if low < high:
		pi = partition(array, low, high)
		quickSort(array, low, pi-1)
		quickSort(array, pi+1,high)
```
