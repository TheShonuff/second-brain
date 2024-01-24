---
title: Form The Minimum
creation date: 2023-01-22 23:01
aliases: []
tags: codewars 
---
# Form The Minimum
Given a list of digits return the smallest number that could be formed from these digits, using the digits only once (ignore duplicates).


**Success**:: true

### Solution
```Rust
fn min_value(mut digits: Vec<i32>) -> i32 {
    digits.sort();
    digits.dedup();
    println!("{:?}", digits);
    let res = digits.iter().map(|x| x.to_string()).collect::<String>();
    println!("{}", res);

    res.parse::<i32>().unwrap()
}
```

**Notes**:: Given the the function accepts a mutable vector made this problem easier to solve. I intially had the order of sort and dedup swapped therefore it didn't work because dedup only removes consecutives duplicates. Then I realized that the join operator only works on strings. I therefore had to iterate through the numbers and collect them into a string.

### Best Solution
```Rust
fn min_value(mut digits: Vec<i32>) -> i32 {
	digits.sort();
	digits.dedup();

	digits.into_iter().fold(0,|acc, x| acc * 10 + x)
```
