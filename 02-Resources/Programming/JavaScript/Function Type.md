---
title: Function Type
creation date: 2022-11-27 22:10
aliases: [TypeScript Function Types]
tags: reading ts filed
---

# Function Type
When initalizing a variable we can assign it the type **Function**

Function types can describe a Function type. The following example states that the defined function type can be any function that accepts 2 number parameters.

```js
let combineValues: (a: number, b: number) => number;
```

## Callbacks 

```js
function addAndHandle(n1: number, n2: number, callBack: (num: number) => void) {
  const result = n1 + n2
  callBack(result)
}
```


# Footer
### Source
- 


