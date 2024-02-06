---
id: 1706159360-php-class-and-objects
aliases:
  - PHP Class and Objects
tags: []
---

# PHP Class and Objects
A class is created using the `class` keyword followed by the class name and curly brackets. Similar to how JavaScript is written.
    - With the curly we can add *properties*, which define the data each object of the class will contain.
    - Classes should always start with a capital letter. 
```php
<?php
class beverage {
    public $color, $opacity, $temperature;
}
```

## Visibility
The `public` is the default Visibility for properties and methods.
    - members can be accessed within the object **or** outside the it.
The `private` can only be accessed within the object using methods.
    - Will not be accessible in subclasses 
The `protected` enables subclasses to access the properties and methods.



## Instantiating 
Objects are instantiated using the `new` keyword followed by the `class_name()`
    - `$very_good_dog = new Pet();`
    - We don't need to use the dollar sign with the class name.
Objects can have values assigned to their properties using `->`
    - `$very_good_dog->name = "Lassie";`
The `->` can also be used to access the value of properties.
    - `echo $very_good_dog->name;`

## Methods
Defined that same way a functions but within the class curly brackets.
    - Contains a special `$this` variable that refers to the current object.
    - Methods are also called using the `->` operator.
        - `$my_object->classMethod()`
    - When calling variables with `$this` **do not use** the `$` in front of the variable (property)
        - `return "this beverage is ". $this->temperture;`

## Constructor Method
Automatically called when the object is instantiated.
    - defined using the `__construct()`keyword.
    - Constructors can have parameters that correspond to arguments passed in when using the `new` keyword.

## Static members
`static` properties and methods don't change for every instance.
    - Accessing `static` properties and methods is done differently.
        - Using the **scope resolution operator** `::` 
        - `echo ClassName::$property;`
            - Accessing properties requires the `$`.
        - `echo ClassName::method();`

## Inheritance
To create a new class that uses another class the `extends` is used.
    - `class ChildClass extends ParentClass`

## Overriding Methods
Changing how method behave for a subclass from the original parent definition is called *Overriding*.
    - Parts that are meant to be keep can be called using `parent::method_name()`

    
## Getters and Setters
The concept of accessing properties. Like python and other languages method are setup to *set* properties or *get* properties.
