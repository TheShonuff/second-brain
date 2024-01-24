---
title: Maximum Subarray Sum
creation date: 2022-12-26 22:31
aliases: []
tags: codewars 
---
# Maximum Subarray Sum
The maximum sum subarray consists in finding the maximum sum of contiguous subsequence in an array or list of integers. 

Every case is when the list is made up of only positive numbers and the maximum sum is the sum of the whole array. If the list is made up of only negative numbers, return 0 instead. Empty list is considered to have zero greatest sum. Note that the empty list or array is also a valid sublist/subarray.

**Success**:: true

### Solution
```Rust
fn max_sequence(seq: &[i32]) -> i32 {
    if seq.len() == 0 {return 0};
    if seq.len() == 1 && seq[0] > 0 {return seq[0]};
    let mut max_num = 0;
    let mut current = 0;
    for (i, x) in seq.iter().enumerate() {
        println!("Start :{},", x);
        let mut length = seq.len();
        while length > i {
            let mut temp = 0;
            for num in (i..length).rev() {
                println!("{}", temp);
                temp += seq[num];
            }
            current = temp;
            if current > max_num{
                max_num = current;
            }
            length -= 1;
            
        }
        if current > max_num {
            max_num = current
        }
        println!("MAX: {}", max_num);
    }
       max_num
}
```

**Notes**:: This one was a real head scratcher. I just couldn't visualize the in's and out's of how to iterate through the array. I managed to get it done with ALOT of print macros. 

### Best Solution
```Rust
fn max_sequence(seq: &[i32]) -> i32 {
	let mut m = 0;
	seq.iter().fold(0, |prev, &v|{
		let p = v.max(prev + v);
		m = m.max(p);
		p
	});
	m
}
```

### Another Solution
```Rust
fn max_sequence(seq: &[i32]) -> i32 {
	let mut max = 0;
	let mut sum = 0;
	seq.iter().for_each(|n| {
		sum += n;
		if sum > max {
			max = sum;
		}
		if sum < 0 {
			sum = 0;
		}
	});
	max
```