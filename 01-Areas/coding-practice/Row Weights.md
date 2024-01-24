---
title: Row Weights
creation date: 2022-12-14 01:12
aliases: []
tags: codewars array
---
# Row Weights
Several people are standing in a row divided into two teams. The first person goes into team 1, the second goes into team 2, the third goes into team 1, and so on.

**Success**:: true

### Solution
```Rust
fn row_weights(array: Vec<u32>) -> (u32,u32){
	let mut team1 = Vec::new();
	let mut team2 = Vec::new();

	for (i,x) in array.iter().enumerate(){
		if i % 2 == 0{
			team1.push(x)
		} else {
			team2.push(x)
		}
	}
	let sum1: u32 = team1.iter().copied.sum::<u32>();
	let sum2: u32 = team2.iter().copied.sum::<u32>();

	(sum1,sum2)
}
```

### Best Solution
```Rust 
extern crate itertools;
use itertools::Itertools;

fn row_weights(array: Vec<u32>) -> (u32,u32) {
	(
		array.iter().step(2).sum(),
		array.iter().skip(1).step(2).sum()
	)
}
```

**Notes**:: While the best solution uses an outside crate that I can seem to reproduce. I could have simplified my solution by intead of pushing all the elements into another vecotor I could have simply set up a mutable variable and added each element that matched the conditional. Therefore I could have elminated the additional sum1 and sum2 variables.

```Rust
fn row_weights(array: Vec<u32>) -> (u32,u32){
	let mut team1 = 0;
	let mut team2 = 0;

	for i in 0..array.len(){
		if i % 2 == 0 {
			team1 += array[i]
		} else {
			team2 += array[i]
		}
	}
	(team1,team2)
}
```

