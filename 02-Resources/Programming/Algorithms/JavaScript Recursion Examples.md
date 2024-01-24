---
title: JavaScript Recursion Examples
Created: 2023-10-02 19:59
tags:
  - algorithms
aliases:
---
# JavaScript Recursion Examples
## CountDown
```js
function countDown(num){
	if(num <=0 ){
		console.log("All Done")
		return;
	}
	console.log(num);
	num--
	countDown(num);
}
```
The recursion example would like this as an iterative loop.
```js
function countDown(num){
	for(var i = num; i > o; i--){
	console.log(i)
	}
	console.log("All Done")
}
```

## SumRange
```js
function sumRange(num){
	if(num === 1) return 1;
	return num + sumRange(num-1);
}
```

## Factorial
```js
function factorial(num){
	if(num === 1) return 1;
	return num * factorial(num-1)
}
```

## Helper Method Recursion
```js
function collectOddValues(arr){
	let result = [];

	function helper(helperInput){
		if(helperInput.length === 0){
		return;
		}
		if(helperInput[0] % 2 !== 0) {
			result.push(helperInput[0])
		}
		helper(helper.Input.slice(1))
	}
		helper(arr)
		
		return result;
}
```

## Pure Recursion
```js
function collectOddValues(arr){
	let newArr = [];
	if(arr.length === 0){
		return newArr;
	}
	if(arr[0] % 2 !== 0){
		newArr.push(arr[0]);
	}

	newArr = newArr.concat(colledOddValues(arr.slice(1)));
	return newArr;
}
```




