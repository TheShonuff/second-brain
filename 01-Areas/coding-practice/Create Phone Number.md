---
title: Create Phone Number
creation date: 2022-12-28 00:53
aliases: []
tags: codewars 
---
# Create Phone Number
Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

**Success**:: true

### Solution
```Rust
fn create_phone_number(numbers: &[u8]) -> String {
    let num = numbers.iter().map(|x| x.to_string()).collect::<String>();
    let re = Regex::new(r"(\d{3})(\d{3})(\d{4})").unwrap();
    let cap = re.captures(&num).unwrap();
    format!(
        "({}) {}-{}",
        cap.get(1).unwrap().as_str(),
        cap.get(2).unwrap().as_str(),
        cap.get(3).unwrap().as_str()
    )
}
```

**Notes**:: This was a good regex excerise. I'm still learning this unique style. I didn't think I had the engergy to pull this one off today but here is the solution. From the looks of the solutions I'm the only one that actually pulled off a regex solution...