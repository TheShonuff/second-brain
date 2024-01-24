---
title: Who Likes It?
creation date: 2022-12-22 00:43
aliases: []
tags: codewars strings
---
# Who Likes It?
Implement the function which takes an array containing the names of people that like an item. It must return the display text as show.
[Kata](https://www.codewars.com/kata/5266876b8f4bf2da9b000362/solutions/rust)

**Success**:: true

### Solution
```Rust
fn likes(names: &[&str]) -> String {
	let length = names.len();
	match length {
	0 => format!("no one likes this"),
        1 => format!("{} likes this", names[0]),
        2 => format!("{} and {} like this", names[0], names[1]),
        3 => format!("{}, {} and {} like this", names[0], names[1], names[2]),
        _ => format!(
            "{}, {} and {} others like this",
            names[0],
            names[1],
            names.len() - 2
        ),

	}
}
```

**Notes**:: I knew instantly the match statement was the way to go. Had a little issue getting the match arms to be the return value. I had a placeholder "string".to_owned() sitting at the bottom that was throwing everything off. My solution was very similiar to the "best" solution. The difference was they simply destructed the names array. Other "bes" solutions used names.len() which I could have simpy used without assigning it to length. That was in the midst of my confusion on how to return a value from match.