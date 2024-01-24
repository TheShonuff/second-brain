---
title: Valid Parentheses
creation date: 2022-12-17 00:46
aliases: []
tags: codewars algorithm
---
# Valid Parentheses
Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return **true** if the string is valid and **false** if it's invald.

**Success**:: true

### Solution
```Rust
fn valid_parentheses(s: &str) -> bool {
	let mut vec = Vec::new();
	for x in s.chars(){
		if x == '(' {
			vec.push(x);
		} else if x == ')' && vec.len() != 0 {
			vec.pop();
		} else if x == ')' && vec.len() == 0 {
			return false;
		} else {
			continue
		}
	}
	vec.is_empty()
}
```

**Notes**:: This was a brute force of this problem. However looking at the solution I'm unsure there is a more elegant "algorithm" that was used. There major difference between the solutions is that some used a counter to increment or decrement based on the value of the character in the for loop. The **best solution** is certainly more idiomatic. 

### Best Solution
```Rust
fn valid_parentheses(s: &str) -> bool {
	let mut opened = 0usize;
	for ch in s.chars() {
		match ch {
			'(' => opened += 1,
			')' if opened > 0 => opened -= 1,
			')' => return false,
			_ => (),		
		}
	}
	opened == 0
}
```