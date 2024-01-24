---
title: Write Number in Expanded Form
creation date: 2022-12-31 22:35
aliases: []
tags: codewars 
---
# Write Number in Expanded Form
You will be given a number and you will need to return it as a string in expanded form
70304 => 70000 + 300 + 4

**Success**:: true

### Solution
```Rust
fn expanded_form(n: u64) -> String {
    let count = n.to_string().chars().count();
    let mut vec = Vec::new();
    let mut md = 10;
    let mut div = 1;
    for _x in 0..count {
        let val = ((n % md) / div) * div;
        if val != 0 {
            vec.push(val.to_string());
        }
        md *= 10;
        div *= 10;
    }
    let a = vec.iter().rev().map(|x| x.to_owned()).collect::<Vec<String>>();
    a.join(" + ")
}
```

**Notes**:: There is a math forumla found [here](https://www.quora.com/How-do-I-print-digits-in-the-tenth-position-using-C) To get the first or the left most number 
(number % 10) / 1
*Tenth Position*
(number % 100) / 10
*Hundredth Position*
(number %1000) / 100

### Best Solution
```Rust
fn expanded_form(n: u64) -> String {
	let mut expanded_form = Vec::<String>::new();

	for (index, digit) in n.to_string().chars().rev().enumerate() {
		if digit == '0' { continue; }
		expanded_form.push(format!("{}{}", digit, "0".repeat(index)));
	}
	expanded_form.reverse();
	expanded_form.join(" + ")
}
```