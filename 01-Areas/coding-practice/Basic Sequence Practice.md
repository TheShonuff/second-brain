---
title: Basic Sequence Practice
creation date: 2023-01-25 23:42
aliases: []
tags: codewars 
---
# Basic Sequence Practice

Complete the function that takes an integer n and reutrn a list/array of length abs(n) + 1 of the arithmetic series explained. When n < 0 return the sequence with negative terms.

**Success**:: true

### Solution
```Rust
fn sum_of_n(n: i32) -> Vec<i32> {
    let length = n.abs() + 1;
    let mut count = 1;
    let mut negative = false;
    if n < 0 {
        count = 0;
        negative = true;
    }
    let mut vec = Vec::new();

    while vec.len() < length as usize {
        let mut acc = 0;
        if negative {
            for x in count..0 {
                acc += x;
            }
        } else {
            for x in 0..count {
                acc += x;
            }
        }

        vec.push(acc);
        if negative {
            count -= 1;
        } else {
            count += 1;
        }
        println!("{}", count);
    }
    vec
}
```

**Notes**:: The problem stumped me on the proper equation to get the numbers to add for each spot in the list/array. I eventually figured that the for loop is the best approach will using the range operator to the current count. My soultion is overcomplicated to compared the best solutions...

The signum method seems to be helpful in solving this problem. The signum returns the sign of the number. Then we can able some math functions to the result of the addition to push the correct signed number to the array/list.

### Best Solution
```Rust
fn sum_of_n(n: i32) -> Vec<i32> {
	(0 .. n.abs() + 1).map(|i| n.signum() * (i.pow(2) + 1) /2).collect()
```

```Rust
fn sum_of_n(n: i32) -> Vec<i32> {
	let mut sum = 0;
	let sign = n.signum();

	()..(n.abs()+1).map(|i| {sum += sign*i; sum}).collect()
```