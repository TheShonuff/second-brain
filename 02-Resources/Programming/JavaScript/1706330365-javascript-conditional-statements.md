---
id: 1706330365-javascript-conditional-statements
aliases:
  - JavaScript Conditional Statements
  - javascript ternary
tags:
  - ternary
  - javascript
---
# JavaScript Conditional Statements
All conditions follow the same format `if(condition){do something}`
- Conditions can be grouped using *logical operators*.
    - `&&` the *and* operator
    - `||` the *or* operator
    - `!` the *not* operator
- Chaining conditions use the `else if(condition){do something}` syntax

## Truthy and Falsy
Sometimes values will need to be check if variables exist. If a variable has non-false value it will be considered **true**
- The list of falsy values
    - `0`
    - `""` empty strings
    - `null` 
    - `undefined` undeclared value
    - `NaN` or Not a Number

### Short-circuit evaluation
JavaScript assigns the truth value to a variable if you use the `||` operator in the assignment.
```js
let username = ''
let defaultName = username || 'Stranger'
console.log(defaultName)
```
>[!note] The code will assign the `defaultName` to Stranger because `username` is falsy.

## Ternary Operator
A short hand operator for the `if...else` statement. Operates in the similar fashion to **short-circuit evaluations**
- `condition ? truthy : falsy`
    - The condition evaluates to `true`, the first expression executes
    - If the condition evaluates to `false`, second expression executes
    

