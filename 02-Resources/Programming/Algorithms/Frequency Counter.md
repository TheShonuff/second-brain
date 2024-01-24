---
tags:
  - algorithms
---
# Frequency Counter

This pattern uses objects or sets to collect values/frequencies of values

This can often avoid the need for nested loops or O(n^2) operations with arrays or strings.


## Example
Write a function called **same**, which accepts two arrays. The function should return true if every value in the array has it's corresponding value squared in the second array. The frequency values must be the same. 
```js
same([1,2,3], [4,1,9]) = true
same([1,2,3]), [1,9]) = false
same([1,2,1], [4,4,1]) = false
```

### naive solution 
```js 
function same(arr1, arr2){
    if(arr1.length !== arr2.length){
        return false;
    }
    for(let i = 0; i < arr1.length; i++){
        let correctIndex = arr2.indexOf(arr1[i] ** 2)
        if(correctIndex === -1) {
            return false;
        }
        console.log(arr2);
        arr2.splice(correctIndex,1)
    }
    return true;
}

same([1,2,3,2], [9,1,4,4])
```

### Refactored Solution 
2 for loops are better than a nested loop. This algorithm is O(n).
```js
function same(arr1, arr2){
    if(arr1.length !== arr2.length){
        return false;
    }
    let frequencyCounter1 = {}
    let frequencyCounter2 = {}
    for(let val of arr1){
        frequencyCounter1[val] = (frequencyCounter1[val] || 0) + 1
    }
    for(let val of arr2){
        frequencyCounter2[val] = (frequencyCounter2[val] || 0) + 1        
    }
    console.log(frequencyCounter1);
    console.log(frequencyCounter2);
    for(let key in frequencyCounter1){
        if(!(key ** 2 in frequencyCounter2)){
            return false
        }
        if(frequencyCounter2[key ** 2] !== frequencyCounter1[key]){
            return false
        }
    }
    return true
}

same([1,2,3,2,5], [9,1,4,4,11])
```

## Example 2
Given two strings, write a function to determine if the second string is an anagram of the first. An anagram is a word, phrase or name formed by rearranging the letter of another, such as cinema, formed from iceman.
```js
validAnagram('','') = true
validAnagram('aaz','zza') = false
validAnagram('anagram', 'nagaram') = true
```

```js
function validAnagram(first, second) {
	if(first.length !== second.length) {
		return false;
	}
	const lookup = {};

	for(let i = 0l i <first.length; i++){
		let letter = first[i];
		//if letter exists, increment, otherwise set to 1
		lookup[letter] ? lookup[letter] += 1 : lookup[letter]= 1;
	}

	for(let i = 0; i< second.length; i++){
		let letter = second[i]
		// can't find letter or letter is zero then it's not an anagram
		if(!lookup[letter])
			return false;
		} else {
			lookup[letter] -= 1;
		}
	}
	return true;
}
```

# Other Examples
```Rust
use std::collection::HashMap;

let text = "Hello world wonderful world";

let mut map = HashMap::new();

for word in text.split_whitespace() {
	let count = map.entry(word).or_insert(0);
	*count +=1;
}

println!("{:?}", map);
```