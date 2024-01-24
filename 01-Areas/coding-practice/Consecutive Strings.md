---
title: Consecutive Strings
creation date: 2023-02-02 00:59
aliases: []
tags: codewars 
---
# Consecutive Strings

You are given an array / list strarr and an integer K. Your task is to return the first longest string consisting of K consecutive strings taken in the array / list.

**Success**:: true

### Solution
```Rust
fn longest_consec(strarr: Vec<&str>, k: usize) -> String {
    if k <= 0 || strarr.len() == 0 || k > strarr.len() {
        return "".to_owned();
    }
    let mut longest_str = String::new();
    let mut longest_length = 0;
    for x in strarr.windows(k) {
        let joined = x.join("");
        let count = joined.chars().count();
        if count > longest_length {
            longest_length = count;
            longest_str = joined;
        }
    }
    longest_str.to_owned()
}
```

**Notes**:: Spent a couple of days on and off working on this problem. On my first go I thought I had it but it turns out I missed read the problem. The array / list is looked at in  windows the size of the supplied num K. I then though using a hashmap to keep track of the found strings but it turns out the hashmap insertion was cooperating. The best solution for me was to keep track of the largest size and compare with the for loop.

### Best Solution

```Rust
fn longest_consec(strarr: Vec<&str>, k: usize) -> String {
	let mut result = String::new();

	if k > 0 && strarr.len() >= k {
		for index in 0..strarr.len() - k + 1 {
			let s: String =  strarr[index..index + k].join("");
			if s.len() > result.len() {
				result = s;
			}
		}
	}
	result
}
```