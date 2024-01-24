---
title: Return Types
creation date: 2022-11-27 21:56
aliases: [TypeScript Function Return Types]
tags: reading ts filed
---

# Return Types
With function we can assign types to the paramaters. We can also assign the types that functions will return 

```js
function add(n1: number, n2: number): number {
    return n1 + n2
}
```

## Void 
When a function does not return a value it has a type void.  Typescript will be able to infer the void type but we can assign it explicitly.
```js
function printResult(num: number): void {
  console.log('Result: ' + num)
}
```


## Undefined 
not a very useful type but a valid type. Undefined would be used on a function that has a return statement but does not return a value

```js
function printResult(num: number): undefined {
  console.log('Result: ' + num)
  return;
}

```

# Footer
### Source
- 


