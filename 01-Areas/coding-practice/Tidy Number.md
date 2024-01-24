---
title: Tidy Number
creation date: 2023-01-22 00:33
aliases: []
tags: codewars 
---
# Tidy Number

A Tidy number is a number whoe digits are in a non-decreasing order

**Success**:: true

### Solution
```Rust
fn tidy_number(n: u64) -> bool {
    let digits: Vec<_> = n
        .to_string()
        .chars()
        .map(|d| d.to_digit(10).unwrap())
        .collect();
    let mut prev = digits[0];
    let res = true;
    for x in 0..digits.len() {
        if digits[x] >= prev {
        } else {
            return false;
        }
        prev = digits[x];
    }
    res
}
```

**Notes**:: This solution is not idiomatic. I've been out of practice a few days and couldn't figure out the right one-liner for this 7kyu to get the rigth result

### Best Solution
```Rust
fn tidy_number(n: u64) -> bool {
	n.to_string().as_bytes.windows(2).all(|ds| ds[0] <= ds[1])
}
```

```Rust 
fn tidy_number(n: u64) -> bool {
	let mut d = n %10;
	let mut n = n;
	n /= 10;
	while n > 0 {
		if n % 10 > d {
			return false
		}
		d = n % 10;
		n /= 10;
	}
	true
}
```