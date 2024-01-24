---
title: The unknown Type
creation date: 2022-11-27 22:26
aliases: []
tags: reading ts filed
---

# The unknown Type
similiar to the type **any** but a bit more restrictive. 

If a known type is assigned to an unknown type variable TypeScript will throw an error. Instead a check has to be performed to insure that type is being passed.

```js
let userInput: unknown
let userName: string

userInput = 5
userInput = 'Max'

if (typeof userInput === 'string') {
  userName = userInput
}
```





# Footer
### Source
- 


