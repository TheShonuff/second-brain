---
title: Rust Hash Maps
creation date: 2022-12-10 20:27
aliases: []
tags: reading rust filed
---

# Rust Hash Maps
Uses key value pairs that's simliar to other programming langaues which may be refered to as: Objects, hash, map, dictionary or associative array.

> [!note] Like [[Vectors]] data is stored on the [[The Stack and the Heap|heap]]

## Creating a New Hash Map
```Rust
use std::collections::HashMap;

let mut scores = HashMap::new()

scores.insert(String::from("Blue"), 10);
scores.insert(String::from("Yellow"), 50);
```
This **HashMap** has keys of type [[Rust Strings|String]] and the values of type i32.

> [!tip] All keys must have the same type and all values have the same type.

## Accessing Values in a Hash Map
A value is accessed by providing the key to the get method.
```Rust
let team_name = String::from("Blue");
let score = scores.get(&team_name).copied().unwrap_or(0);
```
The **get** method reutrns an [[Option Type|Option]]. If there is no value for they key in the hash map **get** will return *None*. The program handles the option by called **copied** then unwrap_or to set score to zero if scores doesn't have an entry for the key.

### Iterating 
Can be iterated over like [[Vectors]] using a for loop.
```Rust
for(key, value) in &scores {
	println!("{}:{}", key, value);
}
```

## Hash Maps and Ownership
For types that implement the Copy trait, like i32, the values are copied into the hash map. Owned values like [[Rust Strings|Strings]], the value will be moved and the hash map will be the owner of those values.

### Updating a Hash Map
Each unique key can have only one value associated with it at a time. 

If a key is inserted with a value into a hash map and then insert the same key with a different value, the value associated with that key will be replaced.

Hash maps have a special API called **entry**.
- Takes the key you want check as a parameter. 
- The return value is an [[Enums|enum]] called **Entry** that represents a value that might or might not exist.

```Rust 
use std::collections::HashMap;

let mut scores = HashMap::new();
scores.insert(String::from("Blue")).or_insert(50);

scores.entry(String::from("Yellow")).or_insert(50);
scores.entry(String::from("Blue")).or_insert(50);

println!("{:?}}, scores");
```
The second call to entry **will not** change the Hash Map becasue Blue already has a value 10.

### Updating a Value Based on the Old Value
```Rust
use std::collection::HashMap;

let text = "Hello world wonderful world";

let mut map = HashMap::new();

for word in text.split_whitespace() {
	let count = map.entry(word).or_insert(0);
	*count +=1;
}

println!("{:?}", map);
```

