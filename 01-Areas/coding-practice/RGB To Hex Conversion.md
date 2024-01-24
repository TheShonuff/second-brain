---
title: RGB To Hex Conversion
creation date: 2022-12-26 01:57
aliases: []
tags: codewars 
---
# RGB To Hex Conversion
The rgb function is incomplete. Complete it so that passing in RGB decimal values will result in a hexademical representation being returned. Valid decimal values for RGB are 0 - 255. Any values that fall out of that range must be rounded to the closes valid value.

**Success**:: true

### Solution
```Rust
fn rgb(r: i32, g: i32, b: i32) -> String {
	let red = format!("{:X}", r.clamp(0,255));
	let green = format!("{:X}", g.clamp(0,255));
	let blue = format!("{:X}", b.clamp(0,255));
	format("{:0>2}{:0>2}{:0>2}", red, green, blue)
}
```

**Notes**:: Easyish kata

### Best Solution
```Rust
fn rgb(r: i32, g: i32, b: i32) -> String {
	format!("{:02X}{:02X}{:02X}", r.clamp(0,255), g.clamp(0,255), b.clamp(0,255))
}
```