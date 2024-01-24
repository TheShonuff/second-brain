---
title: PHP Map
Created: 2024-01-11 21:24
tags:
  - php
aliases:
---
# PHP Map
- **Associative Arrays** Key value pair data structure.
- Key values are seperated using `=>` 

```PHP
$my_array = ["panda" => "very cute", "lizard" => "cute", "cockroach" => "not very cute"];
```

- Can also be built using the `array()` builtin function

```PHP
$about_me = array("fullname" => "Joe Irvine", "social" => 123456);
```

## Displaying Associative Arrays
- `print_r()` is a useful function for displaying the contents of this data structure.

## Accessing and Adding Elements
- elements can be accessed like most other languages using square brackets and supplying the key value.

## Removing Key=>Value Pairs
- `unset()` takes one argument, the associative array key and remove the key=>value pair.

## Numerical Keys
- Can use integers as keys.
	- order arrays are the same as assocative arrays and are indexed.

>[!warning] while they are technically the same treat as them seperate data structures

# Joining Arrays
- Arrays can be combined using the `+` operator.