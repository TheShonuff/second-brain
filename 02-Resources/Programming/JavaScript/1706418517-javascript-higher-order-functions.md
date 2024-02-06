---
id: 1706418517-javascript-higher-order-functions
aliases:
  - Higher-Order Functions
tags:
---

# Higher-Order Functions
Functions that accept other functions as arguments and/or return functions as output.

In JavaScript functions are *first class objects*, functions are treated as values, just like numbers and strings. Which means:
    - Assign them to variables.
    - Pass them as arguments to other functions.
    - Return them from functions.

## Functions as Parameters
When a function is passed as a parameter we **don't invoke the function**. It's pass without using parentheses
```js
const higherOrderFunc =  param => {
    param()
    return `I just invoked ${param.name} as a callback function!`
}
const anotherFunc = () => {
    return "I'm being invoked by the higer-roder function!"
}

higherOrderFunc(anotherFunc);
```
>[!note] anonymous functions can be arguments too!

### Callback
Simply a function passed as an arguments to another function, with the intention that the other function will call the callback function at some later time.

```js
// Defining the callback
function myCallback(result) {
        console.log("The result is:", result)
}

//Pass a callback as an argument
function performAsynctask(callback){
    setTimeout(()=> {
        const result = "Data Fetched!"
        callback(result) // Call the callback function
    }, 2000)
}
```


