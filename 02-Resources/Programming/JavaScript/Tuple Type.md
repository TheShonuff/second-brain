---
title: Tuple Type
creation date: 2022-11-27 22:41
aliases: []
tags: reading ts filed
---
# Tuple Type

TypeScript adds a new data type that's not included in the vanilla javascript. A Tuple is a fixed-length array. Inorder to use a Tuple we have to define the Tuple in the object type definition. This particular **can not be infered** by TypeScript.
```js
const person: {
	name: string;
	age: number;
	hobbies: string[];
	role: [number, string];
}
```
In this example of the object type definition a Tuple is defined that has 2 elements. A number and a string type.

>[!note] Length is not enforced when pushing elements in to the Tuple 



# Footer
### Source
- 


