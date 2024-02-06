---
id: 1706332170-javascript-switch
aliases:
  - JavaScript Switch
tags: []
---

# JavaScript Switch
A simple and more readable way to group multiple `else..if` blocks.

```js
let groceryItem = 'papaya'
switch (groceryItem){
    case 'tomato':
      console.log('Tomatoes are $0.49');
      break;
    case 'lime'
      console.log('Lime are $1.49');
      break;
    case 'papaya'
      console.log('Papayas are $1.29');
      break;
    default:
      console.log('Invalid item');
      break;
}
```

>[!tip] The `break` keyword tells the computer to exit the block.

>[!note] The `default` statement is executed if none of the cases are `true`.



