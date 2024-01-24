---
title: Square Every Digit
creation date: 2022-12-13 11:40
aliases: []
tags: codewars mathematics
---
# Square Every Digit
In this kata, you are asked to square every digit of a number an concatenate them.
For example, if we run 9119 through the function, 811181 will come out, becasue 9^2 is 81 and 1^2 is 1.
**Note**: The function accepts an integer and returns an integer

**Success**:: true


### Solution
```Rust 
fn square_digits(num: u64) -> u64 {
	let digits: Vec<_> = num.to_string().chars().map(|d| d.to_digits(10).unwrap()).collect()
	let mut s = String::new();
	for num in digits {
		let result = num * num
	    s = format!("{}{}", s, result as u64)
	}
	s.trim().parse().unwrap()
}
```

### Best Solution 
```Rust 
fn square_digits(num: u64) -> u64 {
	num
		.to_string()
		.chars()
		.map(|i| i.to_digits(10).expect("Char isnt digit").pow(2).to_string())
		.collect()::<String>()
		.parse()
		.expect("Result is not u64 parsable")
}
```

**Notes**:: This problem required going back and looking at how iterators function correctly. In my solution we have to conver the supplied number to a Vec from an iteratorable. Then we iterator over the created vector. Then format the string and returned the trimmed and parsed option that gets unwraped. 