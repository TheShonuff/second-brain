---
id: 1706392237-javascript-loops
aliases:
  - JavaScript Loops
tags: []
---

# JavaScript Loops
Contains the same loops found in most languages with some syntax differences.

## For Loop
Contains three expressions separated by `;`
    - An *initialization* starts the loop and declare the iterator variable
    - *Stopping Condition* what the iterator variable is evaluated against
    - *Iteration statement* used to update the iterator variable
```js
for (let counter = 0; counter < 4; counter++){
    console.log(counter)
}
```

## The While Loop
Maybe easier to setup and configure. The trick is to make sure with the while loop the condition is **always** updating.
    - Will always execute while the condition is **true**

## Do While Statements
Use when you need a loop to run *at least once*. The `do...while` statement says to do a task once and then keep doing it until a specified condition is no longer met.
```js
let countString = ''
let i = 0
do {
    countString = countString + 1
    i++
} while (i < 5); 
console.log(countString)
```

## Break Keyword
This will terminate a loop when the keyword is encountered.
