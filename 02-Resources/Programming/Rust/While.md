---
title: While
creation date: 2022-12-10 19:51
aliases: []
tags: rust filed
---

# While
The **while let** conditional loop allows a while loop to run for as long as a pttern continues to match.

```Rust
let mut stack = Vec::new();

stack.push(1);
stack.push(2);
stack.push(3);

while let Some(top) = stack.pop() {
	println!("{}", top);
}
```

The while loop runs as long *pop* returns *Some*. When *pop* returns *None*, the loop stops.