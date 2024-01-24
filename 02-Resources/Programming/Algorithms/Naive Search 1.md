---
tags:
  - algorithms
---
# Naive Search
Suppose you want to count the number of times a smaller string appears in a loger string. A straightforward approach involves checking pairs of character individually.

### Pseudocode
- Loop over the longer string
- loop over the storer string
- if the character don't match, break out of the inner loop
- if the characters do match, keep going
- if you complete the inner loop and find a match, increment the count of match
- Return the count

## Example 
```js
function naiveSearch(long, short){
	let count = 0;
	for(var i = 0l i < long.length; i++){
		for(var j =  0; j < short.length; j++){
			if(short[j] !== long[i+j]){
				break;
			}
			if(j === short.length - 1) {
			 count++;
			 }
		}
	}
	return count;
}
```