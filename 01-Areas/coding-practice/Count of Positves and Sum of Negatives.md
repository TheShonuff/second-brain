---
title: Count of Positves and Sum of Negatives
creation date: 2022-12-17 01:00
aliases: []
tags: codewars 
---
# Count of Positves and Sum of Negatives

Given an array of integers. Return an array, where the first element is the count of positive numbers and the second element is sum of negative nummbers. 0 is neither positive or negative. 

If the input is an empty array or is null, return an empty array.

**Success**:: true

### Solution
```Rust
fn count_positives_sum_negatives(input: Vec<i32>) -> Vec<i32> {
	if input.len() == 0 {return input};
	let p_count = input.iter().filter(|&n| *n > 0).count();
	let neg_sum = input.iter().filter(|&n| *n < 0).sum();
	vec![p_count as i32, neg_sum]
}
```

**Notes**:: This one confused me at first on the proper implementation of the filter or map method. My initial instinct was to go for the map method. Ultimately the filer was more deseriable. The key to get it working was the &n is a reference in the iterable reference of the vector. The comparison had to be dereference. Then we can count or sum the iterable.

### Best Solution
```Rust
fn count_positives_sum_negatives(input: Vec<i32>) -> Vec<i32> {
	if input.is_empty(){
		return vec![]
	}
	input.iter().fold(vec![0,0], |mut acc, &x| {
		if x > 0 {
			acc[0] += 1;
		} else {
			ac[1] += x;
		}
		acc
	})
}
```


