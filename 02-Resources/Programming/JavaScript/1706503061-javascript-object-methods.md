---
id: 1706503061-javascript-object-methods
aliases:
  - JavaScript Object Methods
tags: []
---

# JavaScript Object Methods
There are a few helpful methods that can describe an object.

## Keys
`Object.keys()` returns an array of all enumerable property name (keys) and is non-mutating.
```js
const keysArray = Object.keys(object)
```

## Entries
`Object.entries()` returns an array of key-value pairs for each enumerable property of an object.
```js
const entriesArray = Object.entries(object)

//use case
for (const [key, value] of Object.entries(object)){
    console.log(`${key}: ${value}`)
}
```
## Assign
`Object.assign()` copies all enumerable own properties from one or more  source objects to a target object.
```js
const targetObject = Object.assign(target, ...sources)

const robot = {
    model: 'SAL-1000',
    mobile: true,
    sentient: false,
    armor: 'Steel-plated',
    energyLevel: 75
}

const newRobot = Object.assign({}, robot, {laserBlaster:true, voiceRecognition: true})
```

