---
title: Your order, please
creation date: 2022-12-30 01:46
aliases: []
tags: codewars 
---
# Your order, please

Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result. 

**Success**:: true

### Solution
```Rust
fn order(sentence: &str) -> String {
    let split = sentence.split(" ");
    let vec: Vec<&str> = split.collect();
    if vec.len() == 0 {
        return "".to_string();
    }
    let mut result = vec!["J"; vec.len()];
    let mut position = 0;
    for (i, x) in vec.iter().enumerate() {
        for y in x.chars() {
            if char::is_numeric(y) {
                position = y.to_digit(10).unwrap();
                println!("{}", position);
            }
        }
        if position != 0 {
            position -= 1
        }
        result[pos as usize] = x;
    }
    println!("{:?}", result);

    let joined = result.join(" ");
    joined.to_string()
}
```

**Notes**:: This one hurt me. I knew i shouldn't have taken it but I did. I way over complicated this one. but I don't know any better I guess... I got the job done

### Best Solution
```Rust
fn order(sentence: &str) -> String {
	let mut ws: Vec<_> = sentence.split_whitespace().map(String::from).collect();
	ws.sort_by_key(|s| s.chars().find(|c| c.is_digit(10).unwrap())
	ws.join(" ")
}
```