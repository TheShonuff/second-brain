---
tags:
  - algorithms
---
# Linear Search
Defined as a sequential search algorithm that starts at one end and goes through each element of a list until the desired element is found.

A linear search has a [[Time Complexity]] of **O(n)**

![[Pasted image 20221203150837.png]]

>[!note] Used on unsorted lists

### Pseudocode
- This function accepts an array and a value
- Loop through the array and check if the current array element is equal to the value
- If it is, return the index at whichi the element is found
- If not found return -1 or similiar

## Example 
```js
function linearSearch(arr, value) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === value) {
      return i
    }
  }
  return -1
}
```
