---
title: Convert string to camel case
creation date: 2022-12-30 23:41
aliases: []
tags: codewars 
---
# Convert string to camel case

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word has capitalized(know as Upper Camel Case, also referred to as Pascal case). The next words should always be capitalized.

**Success**:: true

### Solution
```Rust
fn to_camel_case(text: &str) -> String {
    if text == "" {
        return "".to_string();
    }
    let mut vec = Vec::new();
    if text.contains("-") {
        vec = text.split("-").collect();
    } else {
        vec = text.split("_").collect();
    }
    let mut change = Vec::new();
    for (i, x) in vec.iter().enumerate() {
        if i != 0 {
            change.push(cap_first_letter(x));
        } else {
            change.push(x.to_string());
        }
    }
    change.join(" ").to_string()
}
fn cap_first_letter(s: &str) -> String {
    s[0..1].to_uppercase() + &s[1..]
}
```

**Notes**:: This one was a smidge easier than expect but not idiomatic. For one I didn't realize i could put 2 statements in the split so I used an if statement with contains to check the supplied text if the text was delimited with - or _ . 

### Best Solution
```Rust
fn to_camel_case(text: &str) -> String {
	text.split(&['-', '_'])
		.enumerate()
		.map(|(i,w)| match i {
			0 => w.to_string(),
			_ => w[..1].to_uppercase() + &w[1..],
		})
		.collect()
}
```