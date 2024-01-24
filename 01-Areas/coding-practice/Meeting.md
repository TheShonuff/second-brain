---
title: undefined
creation date: 2023-01-01 00:19
aliases: []
tags: codewars 
---
# Meeting
Write a function that makes a lits of names uppercase and sort by alpahetical order by last name.


**Success**:: true

### Solution
```Rust
fn meeting(s: &str) -> String {
    let mut res:Vec<String> = s.split(";").map(|x| x.to_string()).collect();
    let mut vec = Vec::new();
    for x in res {
        let split = x.rsplit(":").map(|x| x.to_string().to_uppercase()).collect::<Vec<String>>();
        vec.push(split);
    }
    vec.sort();
    let  mut final = Vec::new();
    for (i,x) in vec.iter().enumerate() {
        let s = format!("({}, {})", vec[i][0], vec[i][1]);
        final.push(s);
    }
    final.join("")
}
```

**Notes**:: This was certainly not idiotmatic but I managed the solution in a short amount of time. The key to an idiomatic result was [flat_map](https://doc.rust-lang.org/std/iter/trait.Iterator.html#method.flat_map) which returns an iterator for each element. I was initially trying to replicate the same effect with just using map and failed. Therefore I created an additionally vec to store my second split.

[Solutions](https://www.codewars.com/kata/59df2f8f08c6cec835000012/solutions/rust)
### Best Solution
```Rust
use itertools::Itertools;

pub fn meeting(s: $str) -> String {
	s.to_uppercase()
		.split(';')
		.flat_map(|person_string| person_string.split(':'))
		.tuples()
		.map(|first, last| format!("({}, {})", last, first))
		.sorted()
		.collect()
}
```