---
title: CSV representation of array
creation date: 2023-01-10 00:26
aliases: 
tags:
  - codewars
---
# CSV representation of array

Creat a function that returns the CSV representation of a two-dimensional numeric array.

**Success**:: true

### Solution
```Rust
fn to_csv_text(array: &[Vec<i8>]) -> String {
    let mut result = "".to_owned();
    let condition = array.len() - 1;
    for (i, x) in array.iter().enumerate() {
        let str = x.iter().map(|d| d.to_string()).collect::<Vec<String>>();
        if i != condition {
            let form = format!("{}/n", str.join(","));
            result.push_str(&form);
        } else {
            result.push_str(&str.join(",").to_owned());
        }
    }
    result
}
```

**Notes**:: Back to basics after a humilating failure in math. I struggled getting the right &str and String to .join() together. I haven't seen the "best solutions" yet but I already know this is a way over complication to the problem.

### Best Solution
```Rust
fn to_csv_text(array: &[Vec<i8>]) -> String {
	array
		.iter()
		.map(|row|
			row.iter()
				.map(|x| x.to_string())
				.collect::Vec<_>>()
				.join(",")
		)
		.collect::<Vec<_>>()
		.join("\n");
}
```

### Solution using Itertools
```Rust
fn to_csv_text(array: &[Vec<i8>]) -> String {
    array
        .iter()
        .map(|a| a.iter().map(|b| b.to_string()).join(","))
        .join("\n")
}
```