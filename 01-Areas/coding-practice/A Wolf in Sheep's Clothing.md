---
title: A Wolf in Sheep's Clothing
creation date: 2022-12-13 23:49
aliases: 
tags:
  - codewars
---
# A Wolf in Sheep's Clothing
Wolves have been reintroduced to Great Britain. You are a sheep farmer, and are no plagued by wolves which pretend to be sheep. Fortunately, you are good at spotting them.

Warn the sheep in front of th ewolf that it is about to be eaten. Remember that you are stainding at the **front of the queue** which is the end of the array.

**Success**:: true

### Solution
```Rust
fn warn_the_sheep(queue: &[&str]) = String {
	let mut found = false;
	let mut count = 0;
	for x in 0..queue.len() -1 {
		if queue[x] == "wolf"{
			found = true;
		}
		if found {
			count += 1
		}
	}
	let result = format!("Oi! Sheep number {}! You are about to be eaten by a wolf!", count);
	let result_zerop = "Pls go away and stop eating my sheep";
	if count > 0 {
		result
	} else {
		result_zero.to_string()
	}
}
```

### Best solution
```Rust
fn warn_the_sheep(queue: &[&str]) -> String {
	match queue.iter().rev().position(|&a| a == "wolf").unwrap() {
		0 => format!("Pls go away and stop eating my sheep"),
		n => format!("Oi! Sheep number {}! You are about to be eaten by a wolf!", n)
	}
}
```

**Notes**:: This one had me stumped. If I had reversed the array It would probably been easier as I would just kept a count up until the iterator hit *wolf*. Even though the way I was trying was still not idiomatic. The **Best Solutions** have a iterator and then reverse. The [position iterator](https://doc.rust-lang.org/std/iter/trait.Iterator.html#method.position) is a new one. Takes a closure that returns true or false. It applies that closure to each element. If one returns *true* then returns **Some(index)**.