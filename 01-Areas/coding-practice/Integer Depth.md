---
title: Integer Depth
creation date: 2023-02-10 00:43
aliases: []
tags: codewars 
---

The **depth** of a integer *n* is defined to be how many multiples of *n* it is necessary to compute before all 10 digits have appeared at least once in some multiple
[Description](https://www.codewars.com/kata/59b401e24f98a813f9000026/solutions/rust)


**Success**:: true

### Solution
```Rust
fn compute_depth(n: u16) -> u8 {
    // multiple n by 1..num until Vec is filled with 0..9
    let mut val = 1;
    let mut step = 0;
    let mut vec:Vec<u32> = Vec::with_capacity(10);

    while vec.len() < 10 {
        let result = n * val;
        // analayze result: explode number IE 10 = 1,0
        let digits: Vec<_> = result
            .to_string()
            .chars()
            .map(|d| d.to_digit(10).unwrap())
            .collect();
        for x in digits.into_iter() {
            if vec.is_empty() {
                vec.push(x);
            } 
            if vec.contains(&x) {
                continue;
            } else {
                vec.push(x);
            }
        }
        
        println!("Vec has: {:?}", vec);
        step += 1;
        val += 1;
    }
   step 
}
```

**Notes**:: I fought the borrow checker at first but somehow a modified version of what I was trying to write made it through without a hitch. Certainly not idiomatic but it's working. Learned how to use the "contains" method in vectors to compare values rather than using another for loop to compare.

### Best Solution
```Rust
fn compute_depth (n: u16) -> u8 {
	if n == 0 {return 0;};
	let mut saw = 0_u16;
	let mut depth = 0_u8;
	while saw != 0b1_111_111_111 {
		let mut m = n * (depth as u16 + 1);
		while m > 0 {
			saw |= 1 << m % 10;
			m /= 10;
		}
		depth += 1
	}
	depth
}
```