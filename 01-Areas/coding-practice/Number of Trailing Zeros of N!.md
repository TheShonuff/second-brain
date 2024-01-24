---
title: Number of Trailing Zeros of N!
creation date: 2023-01-03 00:11
aliases: []
tags: codewars 
---
# Number of Trailing Zeros of N!

Write a program that will calculate the number of trailing zeros in a factorial of a given number.

*You're not mean to caluclate the factorial. Find another way to find the number of zeros*


**Success**:: true

### Solution
```Rust
fn zeros(n: u64) -> u64 {
    let mut count: f64 = 0.0;
    let mut num: f64 = 5.0;
    while (n as f64) / num >= 1.0 {
        count += ((n as f64) / num).floor();
        num *= 5.0;
    }
    count as u64
}
```

**Notes**:: This kata was straight math and I kinda cheated by using a for template from Javascript and converted it to a while loop. I initally tried solving the problem by find the factorial and then converting it to a string and then couting the number of zeros. That was fine for the smaller numbers. Then I started getting very large numbers that started causing overflow issues. There is apparently a math forumla to figure the count

We have to understand Prime numbers, numbers that are not a product of 2 smaller numbers, and solve using the prime number 5. We achieve our solution by getting the floor of n / num where num is multiples of 5. 

```Rust
fn zeros(n: u64) -> u64 {
	if n == 0 { 0 }
	else { n / 5 + zeros( n / 5)}
}
```