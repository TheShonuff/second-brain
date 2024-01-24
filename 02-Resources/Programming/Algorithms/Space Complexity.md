---
title: Space Complexity
creation date: 2022-11-27 14:52
aliases: 
tags:
  - reading
  - cs
  - filed
  - algorithms
---

# Space Complexity
How much additional memory do we need to allocate in order to rund code in the algorithm.

Also know as **auxiliary space complexity** refering to the space required by the algorithm, not including space taken up by the inputs.

- Most primitives (booleans, numbers, undefined, null) are constant space
- Strings require O(n) space (wher n is the string length) 
- Reference types are generally O(n), where n is the length(for arrays) or the number of keys (for objects)

```js
function sum(arr){
	let total=0;
	for (let i=0; i< arr.length; i++) {
		total += arr[i];
	}
	return total;
}
```

Here we have one number for total and another number for i. This example would be O(1) space. 

```js 
function double(arr) {
	let newArr = [];
	for (let i = 0; i < arr.length; i++) {
		newArr.push(2 * arr[i]);
	}
	return newArr;
}
```

new array gets longer directly protional to the input n. this example would be an O(n) space. 



