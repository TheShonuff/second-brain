---
title: Count The Divisors of a Number
creation date: 2023-01-01 00:35
aliases: []
tags: codewars 
---
# Count The Divisors of a Number
Count the number of divisors of a positive integer n

**Success**:: true

### Solution
```Rust
fn divisors(n: u32) -> u32 {
    let mut count = 0;
    for x in 1..=n {
        if n  % x == 0 {
            count += 1;
        }
    }
    count
}
```

**Notes**:: This was an easy one. I could have made it more idiomatic using the filter method. 

### Best Solution
```Rust
fn divisors(n: u32) -> u32 {
	(1..=n).filter(|x| n % 2 == 0).count() as u32
}
```