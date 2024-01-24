---
title: Number of People in the Bus
creation date: 2022-12-16 01:01
aliases: []
tags: codewars 
---
# Number of People in the Bus
There is a bus moving in the city, and it takes and drops some people in each bus stop. You are provided with a list(or array) of integer pairs. Elemens of each pair represent number of people get into the bus(the first item) and the number people getting off the bus(the second item) at a bus stop.

Return the number of people who are still on the bus after the last bus stop.

**Success**:: true

### Solution
```Rust
fn number(bus_stops:&[(i32,i32)]) -> i32 {
	let mut number: i32 = 0;
	for x in bus_stops.inter() {
		numer += x.0;
		number -= x.1;
	}
	number
}
```

**Notes**:: An easier problem that involved iterating over the array of tuples. Then using each part of the tuple to add or subtract people from the running total in the variable number. I tired to implement the **.map( )** method in the refactor but wasn't able to get it working and submitted the working solution

### Best Solution
```Rust
fn number(bus_stops:&[(i32,i32)]) -> i32 {
	bus_stops.iter().fold(0,|acc,x| acc + x.0 - x.1)
}
```

### Solution with .map( )
```Rust
fn number(bus_stops:&[(i32,i32)]) -> i32 {
	bus_stops
		.into_iter()
		.map(|n| n.0 - n.1)
		.sum()
}
```
