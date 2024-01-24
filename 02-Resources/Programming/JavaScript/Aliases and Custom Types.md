---
title: Aliases and Custom Types
creation date: 2022-11-27 22:39
aliases: []
tags: reading ts filed
---

# Aliases and Custom Types

Aliases are created with the **type** keyword. If we're using a lot of union types in our project we can create an easy to read and useable **type**.
```js
type Combinable = number | string;
```
We can also provide complex object types.
```js
type User = {name: string; age: number};
const u1: User { name: 'Joe', age: 38 }
```
We can use this in building functions as well. The function taks an object that is of type User. 
```js 
function greet(user: User) {
	console.log('Hi, I am ' + user.name)
}
```



# Footer
### Source
- 


