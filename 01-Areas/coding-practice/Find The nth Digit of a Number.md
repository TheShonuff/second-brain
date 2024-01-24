---
title: Find The nth Digit of a Number
creation date: 2022-12-15 11:00
aliases: []
tags: codewars mathematics
---
# Find The nth Digit of a Number
Complete the function that takes two numbers as input, **num** and **nth** and return the **nth** digit of **num** ( counting from right to left).

**Success**:: false

### Solution
```Rust
fn find_digit(num: i32, nth: i32) -> i32 {
	if nth <= 0 {
		return -1
	}
	let mut res = num;
	for x in 1..nth {
		res = res / 10;	
	}
	res.abs() % 10
}
```

### Solution 2
```Rust
fn find_digit(num: i32, nth: i32) -> i32 {
	if nth <= 0 { return -1;}
	(num.abs()) / 10_i32.pow(nth as u32 -1)) % 10
}
```

**Notes**:: I failed at this one for a very long time. The *solution 2* was what I was trying to implement. Somewhere along the way I missed the conditional to return 0 which may have screwed some of my calculations up. I managed to work out **.pow(nth as u32 -1)** though the way I set it up I kept getting an overflow error. In the end so close but so far away.

### Failed with
```Rust 
fn find_digit(num: i32, nth: i32) -> i32 {
	let value = num.unsigned_abs() as u32;
	let pow = nth -1
	let result: u32 = value / 10_u32.pow(pow as u32) % 10;
	result as i32
}
```