---
title: Object Type
creation date: 2022-11-27 22:40
aliases: []
tags: reading ts filed
---

# Object Type

It's often best to let TypeScript infer the the object type as opposed to explictly writing the type within the object using:
```js
const person: object {
	name: "Joe",
	age: 30,
}
```
The Following is also sub-optimal
```js
const person: {
	name: string;
	age: number;
} = {
	name: 'Joe',
	age: 30,
}
```
If we choose this route as long as the object type definition follows the same formate for the object there will be no errors. Including nested objects.



# Footer
### Source
- 


