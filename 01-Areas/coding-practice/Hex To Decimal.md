---
title: Hex To Decimal
creation date: 2022-12-13 11:34
aliases: []
tags: codewars conversion
---
# Hex To Decimal
Complete the function which convert hex number (given as a string) to a decimal number.

**Success**:: true


### Solution
```Rust
fn hex_to_dec(hex_string: &str)-> u32 {
	u32::from_str_radix(hex_string, 16).unwrap()
}
```


**Notes**:: An easy string to number conversion that uses [from_str_radix](https://doc.rust-lang.org/std/primitive.i32.html#method.from_str_radix) which convert a string slice in a given base to an integer. The integer we want is an u32 we supply a string that is base 16.