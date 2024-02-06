---
id: 1706334466-javascript-functions
aliases:
  - JavaScript Functions
tags: []
---

# JavaScript Functions
The most common way to create a function is with the `function` keyword.
    - Default parameters can be assigned in the function declaration 
    - By default the resulting value of a function is *undefined*.
        - Use the `return` keyword to return a value.


>[!warning] JavaScript allows *hoisting* which is the ability to call a function before it's defined. **This is still back practice**

## Anonymous Function
A function with no name. These are often stored in a `const` variable.
```js
const calculateArea = function(width, height){
    const area = width * height;
    return area;
}
```
The function can simply be called with `calculateArea(20,40)`
>[!note] Anonymous functions cannot be hoisted

## Arrow Functions
ES6 introduced an even shorter way to write Anonymous Functions.
```js
const rectangleArea = (width, height) => {
    let area = width * height
    return area
}
```
### Concise Body Arrow Functions
Functions that take only a single parameter do not need that parameter to be enclosed in parentheses. However, if a function takes zero or multiple parameters, parentheses are required.
    - Zero Parameters `const functionName = () => {}`
    - One Parameter `const functionName = param => {}`
    - Two or More `const functionName = (param1, param2) => {}`

A function body composed of a single-line block does not need curly brackets and does not need the `return keyword`
```js
const sumNumbers = number => number + number
```
```js
const sumNumber = number => {
    const sum = number + number
    return sum
}
