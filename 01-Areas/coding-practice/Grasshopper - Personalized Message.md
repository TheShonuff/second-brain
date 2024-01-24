---
title: Grasshopper - Personalized Message
creation date: 2023-01-11 00:48
aliases: []
tags: codewars 
---
# Grasshopper - Personalized Message
Create a function that gives a personalized greeting. This function takes two parameters: name and owner. 


**Success**:: true

### Solution
```Rust
if name == owner {
       return "Hello boss".to_owned()
   } else {
       return "Hello guest".to_owned()
   }
```

**Notes**:: I initally tried to use a match but couldn't get it to match "owner" turns out all I need to due it match the result of condition test. True or False. 

### Best Solution
```Rust
fn greet(name: &str, owner: &str) -> String {
	match name == owner {
		true => "Hello boss".to_string(),
		false => "Hello guest".to_string(),
	}
}
```
A short way
```Rust
fn greet(name: &str, owner: &str) -> String {
	match name.eq(owner) {
		true =>  "Hello boss",
		false => "Hello guest",
	}
```