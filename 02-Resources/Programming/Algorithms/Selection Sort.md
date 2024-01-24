---
title: Selection Sort
creation date: 2022-12-03 23:02
aliases: 
tags:
  - cs
  - sorting/selection
  - filed
  - algorithms
---

# Selection Sort
Similar to [[Bubble Sort]] but *instead of first placing large values into sorted position, it places small values into sorted position*. 

The idea is pretty simple. The first element in a list is set as the minimum value and compared to the next element. If the next element is smaller then it becomes the new minimum value. If it's not smaller then the next element in the list is checked. The process is repeated until the end of the list is reached. At which point the minimum value is then placed at the front of the list. 

The algorithm maintains two subarrays in a given array.
- The subarry which already sorted.
- The remaining subarray was unsorted.

The [[Time Complexity]] is **O(n^2)**

![[Pasted image 20221203230551.png]]

### Pseudocode
- Store the first element as the smallest value you've seen so far
- Compare this item to the next item in the array until you find a smaller number.
- If a smaller number is found, designate that smaller number to be the new "minimum" and continue until the end of the array.
- If the "minimum" is not the value(index) you initially began with, swap the two values.
- Repeat this with the next element until the array is sorted.

## Javascript Example
```js
function selectionSort(arr){
	for(let i = 0; i < arr.length; i++){
		let min = i;
		for(let j = i + 1; j < arr.length; j++){
			if(arr[j] < arr[min]){
				min = j;
			}
		}
		if(i !== min){
			let temp = arr[i]
			arr[i] = arr[min];
			arr[min] = temp;
		}
	}
	return arr;
}
```

## Python Example
```Python
def selectionSort(array, size):
	for index in range(size):
		min_index = index
		for j in range(index + 1, size)
			if array[j] < array[min_index]:
				min_index = j
		(array[index], array[min_index]) = (array[min_index], array[index])
```

### Example 2
```Python
def selectionSort(array):
	for index in range(len(array)):
		min_index = index
		for j in range(index + 1, len(array)):
			if array[j] < array[min_index]:
				min_index = j
		array[index], array[min_index] = array[min_index], array[index]
	return array
```
- Loop through to Traverse all the elemtents in the given array
	- set the minimum index to the first unsorted element
	- Loop through over un-sorted subarray
		- find the minimum element in the unsorted sub-array
		- Assign the min_index to the smallest element
	- swap the minimum element with the elemenet at the min_index to place it at it's current position