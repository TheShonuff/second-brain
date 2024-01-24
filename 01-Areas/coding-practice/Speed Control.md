---
title: Speed Control
creation date: 2022-12-20 10:39
aliases: []
tags: codewars 
---
# Speed Control
In John's car the GPS records every **s** seconds the distance travelled from an origin (distances are measured in an arbitary but consistent unit). 
[Speed Control Kata](https://www.codewars.com/kata/56484848ba95170a8000004d/solutions/rust)

**Success**:: true

### Solution
```Rust
fn gps(s: i32, c: Vec<f64>) -> i32 {
	let mut vec = Vec::new();
	for i in x.windows(2) {
		let time = i[1] - i[0];
		let x = (3600.0 * &time) / (s as f64);
		vec.push(x)
	}
	let mex = vec.iter().cloned().fold(0./0., f64::max);
	max.floor() as i32
}
```

**Notes**:: The initial descripition had me worried that this was going to be harder than it actually was. I knew I had to iterate over the vector in pairs (prev, next) and the method **winddows** was exactly what I needed. Then we simply apply the formula to the difference of the pairs received. Push the result into a vector and then at the end traverse the vector looking for the max result. I did get tripped up get the max result. The **.cloned( )** and **.fold( )** methods were the key.

### Best Solution
```Rust
fn gps(s: i32, x: Vec<f64>) -> i32 {
	x.windows(2).map(|xx| 3600. * (xx[1] - xx[0]) / s as f64).fold(0., f64::max) as i32
}
```