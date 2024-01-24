---
title: Bin To Deciaml
creation date: 2022-12-13 11:28
aliases: []
tags: codewars conversion
---
# Bin To Decimal
Complete the function which converts a binary number (given as a string) to a decimal number

**Success**::true

### Solution
```Rust
fn bin_to_decimal(inp: $str)->i32{
	i32::from_str_radix(inp,2).unwrap()
}
```

**Notes**:: An easy string to number conversion that uses [from_str_radix](https://doc.rust-lang.org/std/primitive.i32.html#method.from_str_radix) which convert a string slice in a given base to an integer. The integer we want is an i32 we supply a string that is base 2.