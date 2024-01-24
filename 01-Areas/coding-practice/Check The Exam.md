---
title: Check The Exam
creation date: 2022-12-25 20:19
aliases: []
tags: codewars 
---
# Check The Exam
The first input array is the key to the correct answers to an exam. The second one contains a students submitted answers. The Two arrays are not empty and are the same length. Return the socre of this array of answers. Giving +4 for each correct answer, -1 for each incorrect answer, and +0 for each black answer, represented as an empty string.

If the score < 0 return 0

**Success**:: true

### Solution
```Rust
fn check_exam(arr_a: &[&str], arr_b &[&str]) -> i64 {
	let mut score = 0;
	for (i, _x) in arr_b.iter().enumerate() {
		if arr_a[i] == arr_b[i]{
			score += 5
		} else if arr_b[i] = "" {
			score = score
		} else {
			score -= 1
		}
	}
	if score > 0 {
		score
	} else {
		0
	}
}
```

**Notes**:: I got tripped up on the last condition. Subtracting the incorrect answer by 1. I initially misread the description and did count for the "if the score < 0, return 0". I over complicated the else statement with addtional condition.

### Best Solution
```Rust
fn check_exam(arr_a: &[&str], arr_b &[&str]) -> i64 {
	aar_a.iter().zip(arr_b.iter()).fold(0; |pts, ans| {
		match ans {
			(a,b) if a == b => pts + 4,
			(_, b) if b == &"" => pts,
			_ => pts - 1
		}
	}).max(0)
}
```