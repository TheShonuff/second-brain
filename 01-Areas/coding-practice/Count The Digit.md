---
title: Count The Digit
creation date: 2023-01-01 14:05
aliases: []
tags: codewars 
---
# Count The Digit

Take an integer and a digit as an integer. Square all the number between 0 and n. Count the number of digits d used in the writing of all the square.
[Coun The Digit](https://www.codewars.com/kata/566fc12495810954b1000030/solutions/rust)

**Success**:: true

### Solution
```Rust
fn nb_dig(n: i32, d: i32) -> i32 {
    let res = (0..=n).map(|x| x * x).collect::<Vec<i32>>();
    let count = res.iter().map(|y| y.to_string()).collect::<Vec<String>>();

    let mut counter = 0;

    for x in count {
        if x.contains(&d.to_string()){
            let num = x.matches(&d.to_string()).count();
            counter += num;
        }
    }
    counter as i32
}
```

**Notes**:: I was on the right track for the one liner but I need to fold and not just map then count. 

### Best Solution
```Rust
fn nb_dig1(n: i32, d: i32) -> i32 {
    let ex = d.to_string();
    (0..=n)
        .map(|x| (x * x).to_string())
        .fold(0, |acc, v| acc + v.matches(&ex).count() as i32)
}
```