---
title: Never Type
creation date: 2022-11-27 22:33
aliases: []
tags: reading ts filed
---

# Never Type
Never is another type a function can return. This return type never returns a value. 

When writing a function that will return never, TypeScript will infer the function as a void function. It's good practice to add the :never to the function. 

```js 
function generateError(message: string, code: number): never {
  throw { message: message, errorCode: code }
}
```


# Footer
### Source
- 


