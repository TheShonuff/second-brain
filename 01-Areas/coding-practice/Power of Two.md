---
title: Power of Two
creation date: 2022-12-16 00:06
aliases: []
tags: codewars mathematics
---
# Power of Two
Complete the function **power_of_two** that determines if a given non-negative integer is a [power of two](https://en.wikipedia.org/wiki/Power_of_two) 

>[!quote] A power of two is a number of the form $2^n$ where **n** is an integer, i.e. the result of exponentiation with number two as the base and integer **n** as the exponent

**Success**:: true

### Solution
```Rust
fn power_oftwo(x: u64) -> bool {
	let num = x as f64;
	let result = num.log2();
	if result.fract() == 0.0 {
		true
	} else {
		false
	}
}
```

### Refactor
```Rust
fn power_of_two(x: u64) -> {
	let num = (x as f64).log2();
	match num.fract() {
		0.0 => true,
		_ => false
	}
}
```

**Notes**:: I picked up on that a logarithm is the best way to solve this solution. Once I put a few number through the log function I realized that to return true we need a whole integer without a decimal. **.fract( )** returns the the fractional part of a number. Therefore if there is no fraction we can assume it's a whole number. The refactored solution contains a warning that *floating-point types cannot be used in patterns*. While the refactored solution is more idiomatic it is not good practice.

### Best Solution
```Rust
fn power_of_two(x: u64) -> bool {
	x.is_power_of_two()
}
```

**Notes**:: The **is_power_of_two( )** returns true if and only if self == 2^k for some k. [is_power_of_two](https://doc.rust-lang.org/std/primitive.u64.html#method.is_power_of_two)
