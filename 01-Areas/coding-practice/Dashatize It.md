---
title: Dashatize It
creation date: 2022-12-21 23:34
aliases: []
tags: codewars 
---
# Dashatize It
Given a variable **n**. If **n** is an integefer return a string with dash '-' marks before and after each odd integer, but do not begin or end the string with a dash mark. If **n** is a negative, then the negative sign should be removed.

If **n**  is negative, then the negative sign should be removed.

**Success**:: true

### Solution
```Rust
fn dashatize(n:i64) -> String {
	let mut num = n;
	if num < 0 {
		num *= -1;
	}
	let mut result = String::new();
	let dash = "-";
	for num_string =  num.to_string();
	for (i,x) in num_string.chars().enumerate() {
		if x == '0' || x == '2' || x == '4' || x == '6' || x == '8' {
			result.push_str(&x.to_string());
		} else {
			let mut check = 0;
			if result.len() != 0 {
				check = result.len() -1;
			}
			if result.len() == 0 || &result[check..] == "-" {
				result.pus_str(&x.to_string());
			} else {
				result.push_str(dash);
				result.push_str(&x.to_string());
			}
			if i != num_string.len() -1 {
				result.push_str(dash)
			}
		}
	}
	result
}
```

**Notes**:: This one had me scratching my head for awhile. I really wanted to go at it with regex but I couldn't figure out the right expression to use for capturing or matching. Turns out the best solution uses a regex expression that I was very close to using.

### Best Solution
```Rust
use regex::*;

fn dashatize(n:i64) -> String {
	Regex::new(r"[02468]+|[13579]").unwrap()
		.find_iter(&n.abs().to_string())
		.map(|m| m.as_str())
		.collect::<Vec<_>>()
		.join("-")
}
```