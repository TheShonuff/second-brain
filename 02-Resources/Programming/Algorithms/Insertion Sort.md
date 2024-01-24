---
title: Insertion Sort
creation date: 2022-12-04 13:09
aliases: 
tags:
  - cs
  - sorting
  - algorithms
---

# Insertion Sort
A simple sorting algorithm that works similar to the way you would sort playing cards. The array is virtually split into a sorted and unsorted lists. Values from the unsorted part are picked and placed with the correct position of the sorted part.

The [[Time Complexity]] is **O(n^2)**

### Pseudocode
- Start by picking the second element in the array
- Now compare the second element with the one before it and swap if necessary
- Continue to the next element and if it is in the incorrect order, iterate through the sorted portion, *the left side*, to place the element in the correct place.
- Repeat until the list is sorted

```js
function insertionSort(arr){
	for(var i = 1; i < arr.length; i++){
		var currentVal = arr[i];
		for(var j = i - 1; j >= 0 && arr[j] > currentVal; j--){
			arr[j + 1] = arr[j];
		}
		arr[j + 1] = currentVal;
	}
	return arr;
}
```

