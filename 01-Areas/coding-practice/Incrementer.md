---
title: Incrementer
creation date: 2023-01-12 23:49
aliases: []
tags: codewars 
---
# Incrementer

Given an input of an array of digits, return the array with each digit incremented by its positions in the array: The first digit will be incremented by 1, the second digit incremented by 2, etc. Make sure to start counting your positions from 1( and not 0).

Your result can only contain single digit numbers, so if adding a digit with its position gives you a multiple-digit number, only the last digit of the number should be returned.

**Success**:: true

### Solution
```Rust
fn incrementer(nums: &[u32]) -> Vec<u32> {
    let mut count = 1;
    let mut vec = Vec::new();
    for x in nums {
        let result =  x + count;
        count +=1;
        if result >= 10 {
            vec.push(result % 10)
            
        } else {
            vec.push(result)
        }
    }
    vec
}
```

**Notes**:: A fairly easy kata. The only problem I encounted when I was trying to refactor the problem to be more Rust idiomatic. I could seem to get the fold method to work until I realized it wouldn't fold into a new vector. Then I tried getting map to work but couldn't figure out the correct syntax.

### Best Solution
```Rust
fn incrementer(nums: &[u32]) -> Vec<u32> {
	nums.iter().enumerate().map(|(i,v)| (i as u32 + *v + 1) % 10.collect())
}
```

```Rust
fn incrementer(nums: &[u32]) -> Vec<u32> {
	nums.iter().zip(1..).map(|&x, i)| (x+1) % 10).collect()
```