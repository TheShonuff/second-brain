---
title: Sum of Sequence
creation date: 2022-12-14 00:10
aliases: []
tags: codewars mathematics
---
# Sum of Sequence
Your task is to make a function, which returns the sum of a sequence of integers. The sequence is defined by 3 non-negative values: **Begin, end, step(inclusive)**. If **begin** value is greate than the **end**, function should return 0.

**Success**:: true

### Solution
```Rust
fn sequence_sum(start: u32, end: u32, step: u32) -> u32 {
	if start > end{
		return 0;
	}
	let mut current = start;
	let mut result: u32 = start;
	while current < end {
		if current +  step > end {
			return result
		} else {
			current = current + step;
			result += result;
		}
	}
	result
}
```

### Best Solution
```Rust
fn sequence_sum(start: u32, end: u32, step: u32) -> u32 {
	(start..=end)
		.step_by(step as usize)
		.sum()
}
```

**Notes**:: Really over complicated this one and definetly NOT idiomatic. The best solution  creates a rang from start to end. The [step_by( )](https://doc.rust-lang.org/std/iter/struct.StepBy.html) iterator is for stepping iterators by a custom amount. Then we use the **.sum( )** method to collect the results.