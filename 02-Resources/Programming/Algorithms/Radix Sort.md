---
title: Radix Sort
creation date: 2022-12-10 23:33
aliases: 
tags:
  - cs
  - sorting
  - filed
  - algorithms
---

# Radix Sort
A different way of sorting that works only on numbers. This algorithm never makes a comparison. It exploits the fact that information about the size of a number is encoded in the number of digits.

A few helper functions need to be created.

getDigit(num, place) returns the digit in num at the given place value.

```js
function getDigit(num, i){
	return Math.floor(Math.abs(num) / Math.pow(10,i)) % 10;
}
```

digitCount(num) - returns the number of digits in num
```js
function digitCount(num){
	if(num === 0) return 1;
	return Math.floor(Math.log10(Math.abs(num))) + 1;
}
```

mostDigits(nums) - Given an array of numbers, returns the number of digits in the largest numbers in the list.
```js
function mostDigits(nums){
	let maxDigits = 0;
	for (let i=0; i<nums.length; i++){
		maxDigits = Math.max(maxDigits, digitCount(nums[i]))l	
	}
	return maxDigits
}
```

### Pseudocode
- Define a function that accepts a list of numbers
- Figure out how many digits the largest number has\
- loop from k=0 up to this largest number of digits
- for each iteration of the loop:
	- Create buckets for each digit(0 to 9)
	- pleace each number in the corresponding bucket
- Replace the existing array with values in the buckets, starting with 0 and going up toi 9
- return list at the end.

```js
function radixSort(nums){
	let maxDigitCount = mostDigits(nums);
	for(let k=0; k < maxDigitCount; j++){
		let digitBuckets = Array.from({length:10}, () => []);
		for(let i=0; i< nums.length; i++){
			let digit = getDigit(nums[i],k)
			digitBucket[digit].push(nums[i]);
		}
		nums = [].concat(...digitbuckets);
	}
	return nums;
}
```