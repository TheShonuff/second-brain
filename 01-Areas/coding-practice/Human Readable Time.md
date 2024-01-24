---
title: Human Readable Time
creation date: 2022-12-26 01:03
aliases: []
tags: codewars mathematics
---
# Human Readable Time
Write a function, which takes a non-negative integer (seconds) as input and returns the time in a human-readable format HH:MM:SS

**Success**:: true

### Solution
```Rust
fn make_readable(seconds:u32) -> String {
	let hours: f32 = ((seconds as f32)) / 3600;
	let remaining_hours: f32 = (seconds as f32) - (hours.trunc() * 3600);
	let minutes: f32 = remaining_seconds / 60.0;
	let second: f32 = (remaining_seconds as f32) - (minutes.trunc() * 60.0);
	format!("{:0>2}:{:0>2}:{:0>2}", hours.trunc(), minutes.trunc(), seconds.trunc())
}
```

**Notes**:: This took a while to complete and I need the step by step formula to complete. 

### Best Solution
```Rust
fn make_readable(S: u32) -> String {
	let m = s/60;
	let s = s % 60;
	let h = m/60;
	let m = m % 60;
	format!("{:0>2}:{:0>2}:{:0>2}", h,m,s)
}
```