---
title: Rock Paper Scissors
creation date: 2023-02-02 00:05
aliases: []
tags: codewars 
---

Let's play! You have to return which player won! In case of a draw return Draw!
[Problem](https://www.codewars.com/kata/5672a98bdbdd995fad00000f/solutions/rust)

**Success**:: true

### Solution
```Rust
fn rps(p1: &str, p2: &str) -> &'static str {
    if p1 == p2 {
        return "Draw!";
    } 
    // rocks beats scissors
    if p1 == "scissors" &&  p2 == "paper" {
        return "Player 1 won!";
    } 
    if p1 == "rock" && p2 == "paper" {
        return "Player 2 won!";
    }
    if p1 == "paper" && p2 == "rock" {
        return "Player 1 won!";
    }
    if p1 == "scissors" && p2 == "rock" {
        return "Player 2 won!";
    }
    if p1 == "paper" && p2 == "scissors" {
        return "Player 2 won!";
    } else {
        return "Player 1 won!";
    }
    
    // paper beats rocks 
    // scissor beats paper 
}
```

**Notes**:: My solution is not idiomatic and way over complicates the problem compared to how the "best practice" solutions were written. I am out of practice a couple of days but I see how using the match statement was the right way to approach this problem.

### Best Solution
```Rust
fn rps(p1: &str, p2: &str) -> &'static str {
	if (p1 == p2) {
		return "Draw!";
	}
	match (p1, p2) {
	("scissors", "paper") | ("paper", "rock") | ("rock", "scissors") +> "Player 1 won!", 
	_ => "Player 2 won!",
	}
}
```

### Another Solution
```Rust
fn rps(p1: &str, p2: &str) -> &'static str {
	match (p1,p2) {
		("scissors", "paper") => "Player 1 won!",
		("scissors", "rock") => "Player 2 won!",
		("rock", "scissors") => "Player 1 won!",
		("rock", "paper") => "Player 2 won!",
		("paper", "rock") => "Player 1 won!",
		("paper", "scissors") => "Player 2 won!",
		_=> "Draw!",
	}
}
```