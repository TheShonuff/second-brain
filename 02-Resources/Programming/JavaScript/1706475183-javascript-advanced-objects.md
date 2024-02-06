---
id: 1706475183-javascript-advanced-objects
aliases:
  - JavaScript Advanced Objects
tags: []
---

# JavaScript Advanced Objects
The `this` keyword references the *calling object* which provides access to the calling objects properties.

>[!warning] avoid using arrow functions when working with the `this` keyword.

## Privacy
In JavaScript there are no `Public` or `Private` keywords when working with object properties. Instead a naming convention is used to indicate the privacy level of property. Any property with a `_` underscore in front **should not be altered**. 

## Getters
A method that returns the internal properties of an object. The keyword `get` is followed by the function.
    - Can perform an action on the data when getting a property.
    - Can return different values using conditionals
    - Can access the properties of the calling object using `this`
```js
const person = {
  _firstName: 'John',
  _lastName: 'Doe',
  get fullName() {
    if (this._firstName && this._lastName){
      return `${this._firstName} ${this._lastName}`;
    } else {
      return 'Missing a first name or a last name.';
    }
  }
}

// To call the getter method: 
person.fullName; // 'John Doe'
```
### Why we don't need parenthesis for getters
The *get* syntax binds an object property to a function that will be called when that property is looked up. You are not calling the function, you look at the property.

## Setters
A method that can reassign values of existing properties within an object. The `set` keyword is used.
```js
const person = {
  _age: 37,
  set age(newAge){
    if (typeof newAge === 'number'){
      this._age = newAge;
    } else {
      console.log('You must assign a number to age');
    }
  }
};
person.age = 40
console.log(person._age) // Prints 40
```
As with getters, these are not called with `()` but look like you're setting a property regularly. The main advantage to using a *Setter* is that checks can be performed *before* the property is updated.


## Factory Functions
A function that returns an object and can be reused to make multiple object instances. It's an alternative to using *constructors*
    - Unlike constructors they don't use the `new` keyword
    - There is no `this` binding
    - Can create any object type.
```js
const robotFactory = (model, mobile) => {
    return {
        model: model,
        mobile: mobile,
        beep(){
            console.log('Beep Boop')
        }
    }
}
const tinCan = robotFactory('P-500', true)
```
### Destructuring
A short hand way of assigning property values called *property value shorthand*.
```js
const robotFactory = (model, mobile) => {
    return {
        model,
        mobile
    }
}
```
## Destructured Assignment
Simplifies the extraction of values from from arrays and objects.
```js
const vampire = {
    name: 'Dracula',
    residence: 'Transylvania',
    preferences: {
        day: 'stay inside',
        night: 'satisfy appetite'
    }
}
const residence = vampire.residence //old way
const { residence } = vampire //destructed way
```

