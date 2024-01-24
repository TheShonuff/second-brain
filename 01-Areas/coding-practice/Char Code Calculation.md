---
title: Char Code Calculation
creation date: 2023-01-01 21:19
aliases: []
tags: codewars 
---
# Char Code Calculation
Given a string, turn each character into its ASCII character code and join them, otgether to create a number. Then replace any incidence of the number 7 with the number 1.

Then return the difference between the sum of digits in total1 and total2


**Success**:: true

### Solution
```Rust
fn calc(s: &str) -> u32 {
    let total1 = s
        .chars()
        .map(|x| (x as u32).to_string())
        .collect::<String>();
    println!("{}", total1);
    let total2 = total1.replace("7", "1");
    println!("{}", total2);
    let x1 = total1.chars().fold(0, |mut acc, x| {
        acc += x as u32;
        acc
    });
    let x2 = total2.chars().fold(0, |mut acc, x| {
        acc += x as u32;
        acc
    });
    x1 - x2
}
```

**Notes**:: I got tripped up and didn't read the last set of instructions clearly. **then return the difference between the sum of the digits**. I was initially dealing when way too many trailing zeros after I had increases the integer memory space to u128.

### Best Solution
```Rust
fn calc(s: &str) -> u32 {
    s.chars()
        .map(|c| (c as u8).to_string().chars().filter(|&c| c == '7').count() as u32)
        .sum::<u32>()
        * 6
}
```