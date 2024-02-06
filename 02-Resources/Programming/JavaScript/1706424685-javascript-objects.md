---
id: 1706424685-javascript-objects
aliases:
  - JavaScript Objects
tags: []
---

# JavaScript Objects
Objects can be assigned just like any JavaScript type. `{}` are used to designate an *object literal*. Data in objects are filled with key-value pairs.

## Accessing Properties
### Dot Notation
The easiest way to access a property is using dot notation.
```js
let spaceship = {
    homePlanet = 'Earth',
    color = 'silver'
}
spaceship.homePlanet;
spaceship.color;
```
### Bracket Notation
The other way to access a key's value is by using bracket notation. Similar to how array's are accessed by the *key* is supplied rather than a index int.

## Property Assignment
Objects are mutable. Dot notation or bracket notation can be used to update properties. Simply assign a new value using `=` to update the value.

>[!note] A property can also be removed using the `delete` operator.

## Methods
When the data stored on a object is a *function*.

>[!note] a property is what an object has. A method is what an object does.

## Nested Objects
A lot of time objects will be nested with objects.
```js
const spaceship = {
    telescope: {
        yearBuilt: 2018,
        model: '91031-XLT',
        focalLength: 2032 
    },
    crew: {
        captain: { 
            name: 'Sandra', 
            degree: 'Computer Engineering', 
            encourageTeam() { console.log('We got this!') } 
         }
    },
    engine: {
        model: 'Nimbus2000'
    },
    nanoelectronics: {
        computer: {
            terabytes: 100,
            monitors: 'HD'
        },
        'back-up': {
           battery: 'Lithium',
           terabytes: 50
        }
    }
};
spaceship.nanoelectronics['back-up'].battery; // Returns 'Lithium'
```
## Pass By Reference
When a variable assigned to an object is passed into a function as an argument. JavaScript primarily uses *pass by value* for primitive types (numbers, strings, booleans, null, undefined, symbols). 
    - Passes a reference (or memory address) to the object itself
    - Changes made within the function affect the original object outside the function.
    - Objects and arrays, due to their mutable nature, behave as *pass by reference*
```js
const spaceship = {
    homePlanet: 'Earth',
    color: 'silver'
}
let paintIt = obj => {
    obj.color = 'glorious gold'
}
paintIt(spaceship);
spaceship.color // Returns 'glorious gold'
```

## Looping Through Objects
The `for...in` syntax allows for looping objects. Iterates through each element of the object.
```js
let spaceship = {
  crew: {
    captain: { 
      name: 'Lily', 
      degree: 'Computer Engineering', 
      cheerTeam() { console.log('You got this!') } 
    },
    'chief officer': { 
      name: 'Dan', 
      degree: 'Aerospace Engineering', 
      agree() { console.log('I agree, captain!') } 
    },
    medic: { 
      name: 'Clementine', 
      degree: 'Physics', 
      announce() { console.log(`Jets on!`) } },
    translator: {
      name: 'Shauna', 
      degree: 'Conservation Science', 
      powerFuel() { console.log('The tank is full!') } 
    }
  }
}; 

// for...in
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
}
```






