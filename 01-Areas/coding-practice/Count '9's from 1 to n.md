---
title: Count '9's from 1 to n
creation date: 2023-01-08 22:22
aliases: []
tags: codewars 
---
# Count '9's from 1 to n
It's 9 time!
I want to count from n to n. How manyu times will I use a '9'?


**Success**:: false

### Solution
```Rust
fn count_nines(n: u64) -> u64 {
	let (mut c, mut p) = (0,1);
	while p <= n {
		let x = n/p;
		if x % 10 == 9 {
			c += n % p + 1;
		}
		c += x / 10 * p;
		p *= 10;
	}
	c
}
```

### Another Solution
```Rust
fn count_nines(mut n: u64) -> u64 {
	let mut result = 0;
	let mut right_digit_num = 0;
	let mut right_nine_count = 0;
	let mut place = 1;
	while n > 0 {
		let digit = n % 10;
		n /10;
		right_nine_count = 10 * right_nine_count + place / 10;
		result += digit * right_nine_count;
		if digit == 9 {
			result += 1 + right_digits_num;
		}
		right_digits_num += digit * place;
		place *= 10;
	}
	result
}
```

**Notes**:: I tried and failed epically at this one. I actually have a working solution but when the numbers get too big it takes forever to calculate the actual number.

```Rust
fn count_range(num: u64) -> u64 {
    let mut count = 0;
    for x in 1..=num {
        let num_string = x.to_string().chars().filter(|&x| x == '9').count();
        count += num_string;
    }

    count as u64
}

```

I've use this working solution to figure out if the outputs were correct. When we started getting into the millions that's when my algorithm fell apart.