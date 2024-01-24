---
tags:
  - algorithms
  - javascript
---
# Binary Search
Is a much faster form of search. Rather than eliminating one element at a time you can eliminate half of the remaining elements at a time.
>[!note] Only works on sorted lists

Binary search algorithm.
$\Huge {Left + Right\over 2}$

Also called **divde and conquer** 

The [[Time Complexity]] is $O(log n)$

### Pseudocode
- This function accepts a sorted array and a value
- Create a left pointed at the start of the array, and a right pointer at the end of the array.
- While the left pointer comes before the right pointer:
	- Create a pointer in the middle
	- If you find the value you want, return the index
	- If the value is too small, move the left pointer up
	- If the value is too large, move the rigth pointer down
- If you never find the value, return -1 

## Example
```js
function binarySearch(arr, val) {
  let start = 0
  let end = arr.length - 1
  let middle = Math.floor((start + end) / 2)
  while (arr[middle] !== val && start <= end) {
    if (val < arr[middle]) {
      end = middle - 1
    } else {
      start = middle + 1
    }
    middle = Math.floor((start + end) / 2)
  }
  if (arr[middle] == val) {
    return middle
  } else {
    return -1
  }
}
```
