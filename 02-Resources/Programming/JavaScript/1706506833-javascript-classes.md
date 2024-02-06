---
id: 1706506833-javascript-classes
aliases:
  - JavaScript Classes
tags: []
---

# JavaScript Classes
There are a lot of similarities between class and object syntax but one important distinction. There's a `constructor` method which is called every time a new instance of the class is created.

```js
class Dog {
    constructor(name) {
        this.name = name;
        this.behavior = 0;
    }
}

```
>[!note] unlike objects the properties in the constructor are not separated by commas

## Instance
An object that contains the property names and methods of a class, but with unique property values.

```js
const halley = new Dog('Halley')
```

## Methods
Also similar to how objects store methods, we have *get* and *set* methods. The major difference here is that they're *not* separated by commas.

```js
class Dog {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }
    
  get name() {
    return this._name;
  }
  
  get behavior() {
    return this._behavior;
  }
  
  incrementBehavior() {
    this._behavior++;
  }
}
```
## Inheritance
For when multiple classes share properties or methods. A *parent* (superclass) will be the template for multiple *child* classes.

To make this possible the `extends` keyword is used. The `super` keyword in the constructor calls the constructor of the parent class.

>[!warning] You must **always** call `super` on the first line of the `constructor()`. Failure to do so will result in a reference error.

```js
class HospitalEmployee {
    constructor(name){
        this._name = name;
        this._remainingVacationDays = 20;
    }
    get name(){
        return this._name
    }
    get remainingVacationDays(){
        return this._remainingVacationDays
    }
    takeVacationDays(daysOff){
        this._remainingVacationDays -= daysOff
    }
}

class Nurse extends HospitalEmployee {
    constructor(name, certifications){
        super(name)
        this._certifications = certifications
    }
}
```

### Static Methods
Methods defined using the `static` keyword and belong to the class itself and *not* instances of the class.

