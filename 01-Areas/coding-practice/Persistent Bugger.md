---
title: Persistent Bugger
creation date: 2022-12-29 23:36
aliases: []
tags: codewars 
---
# Persistent Bugger

Write a function, persistence, that takes in a positive number **num** and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a signle digit.

**Success**:: true

### Solution
```Rust
fn persistence(num: u64) -> u64 {
    let mut digits: Vec<_> = num
        .to_string()
        .chars()
        .map(|d| d.to_digit(10).unwrap())
        .collect();
    println!("Going into the while loop {:?}", digits);
    let mut count = 0;
    while digits.len() > 1 {
        let product = digits.iter().fold(1, |acc, x| (acc as u128) * (*x as u128));
        digits = product
            .to_string()
            .chars()
            .map(|d| d.to_digit(10).unwrap())
            .collect::<Vec<_>>();
        count += 1;
        println!("Digits length is: {}", digits.len());
    }

    println!("{:?}", digits);
    count
}
```

**Notes**:: I had to chase down the error in this one. I got a *multiplication overflow* error which was essentially that the first product was too large of a number to fit in the u32 space. I correct this by getting the product in a u128 space. 

### Best solution
```Rust
pub fn persistence(num: u64) -> u64 {
	let mut n = num;
	let mut count = 0;
	while n > 9 {
		n = prod(n);
		count += 1;
	}
	count
}

fn prod(n: u64) -> u64 {
	let mut n = n;
	let mut prod = 1;
	while n > 0 {
		prod += n%10;
		n /= 10;
	}
	prod
}
```