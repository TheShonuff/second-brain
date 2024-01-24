---
title: Merge Sort
creation date: 2022-12-06 23:35
aliases: 
tags:
  - cs
  - filed
  - algorithms
---

# Merge Sort
A combination of two things - merging and sorting. This algorithm exploits the fact that arrays are of 0 or 1 elements are always sorted. Working by decomposing an array into smaller arrays of 0 or 1 elements.

Based on the **Divide and Conquer** paradigm. The array is initally split into two equal halves and then they are combined in a sorted manner.

## Merging Array's
- In order to implement merge sort, it's useful to first implement a function responsbile for merging two sorted arrays.
- Given two arrays which are sorted, this helper function should create a new array which is also sorted and consists of all of the elements in the two input arrays.
- This function should run in O(n+m) time and O(n+m) space and **should not** modify the parameters passed to it
![merge](https://media.geeksforgeeks.org/wp-content/uploads/20220722205737/MergeSortTutorial.png)

### merge Pseudocode
- Create an empty array, take a look at the smallest values in each input array
- While there are still values we haven't looked at..
	- If the value in the first array is smaller than the value in the second array, push the value in the first array into our results and move on to the next value in the first array
	- If the value in the first array is larger than the value in the second array, push the value in the second array into our results and move on to the next value in the second array
	- Once we exhaust one array, push in all remaining vlaues from the other array.
```js
function merge(arr1, arr2){
	let results = [];
	let i = 0;
	let j = 0;
	while(i < arr1.length && j < arr2.length){
		if(arr2[j] > arr1[i]){
			results.push(arr1[i]);
			i++;
		} else {
			results.push(arr2[j]);
			j++;
		}
	}
	while(i < arr1.length){
		results.push(arr1[i])
		i++
	}
	while(j < arr2.length){
		results.push(arr2[j])
		j++	
	}
	
	return results = [];
}
```
[Link to video](https://www.udemy.com/course/js-algorithms-and-data-structures-masterclass/learn/lecture/11072006#questions)

### mergeSort Pseudocode
- Break up the array into halves until you have arrays that are empty or have one element
- Once you have smaller sorted arrays, merge those arrays with other sorted arrays until you are back at the full length of the array
- Once the array has been merged back together, return the merged and sorted array.
```js
function mergeSort(arr){
	if(arr.length <= 1) return arr;
	let mid = Math.floor(arr.length/2);
	let left = mergeSort(arr.slice(0,mid));
	let right = mergeSort(arr.slice(mid));
	return merge(left, right);
}
```