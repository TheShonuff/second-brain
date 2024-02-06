---
id: 1706420111-javascript-iterators
aliases:
  - JavaScript Iterators
tags: []
---

# JavaScript Iterators
Methods called on arrays to manipulate elements and return values.

## forEach Method
Executes the same code for each element of an array.
    - Takes an argument of callback function.
    - Loops through the array and executes the callback function for each element.
    - The return value for `.forEach()` will always be `undefined`.

>[!note] arrow functions a popular way to pass callbacks

```js
groceries.forEach(groceryItem => console.log(groceryItem));
```

## Map Method
Takes an argument of a callback function and returns a new array. Work similar to `.forEach()` but returns a new array.
```js
const numbers = [1,2,3,4,5]
const bigNumbers = numbers.map(number => { return number * 10})
```

## Filter Method
Returns a *new* array after filtering out certain elements from the original array. The callback function for return `true` or `false` depending on the element passed to it. 

Elements that cause the callback function to return `true` are added to the new array.

```js
const words =['chair', 'music', 'pillow', 'brick', 'pen', 'door']
const shortWords = words.filter(word => { return word.length < 6 })
```

## Find Index Method
When the location of an element in an array needs to be know `.findIndex()`. Returns the index of the first element that evaluates to `true` in the callback function.
```js
const jumbledNums = [123,25,78,5,9]
const lessThanTen = jumbledNums.findIndex(num => {
    return num < 10;
})
```
## Reduce Method
Returns a single value after iterating through the elements of an array.
```js
const numbers = [1,2,4,10]
const sumedNums = numbers.reduce((accumulator, currentValues) => {
    return accumulator + currentValue
})
```
>[!note] The `.reduce()` can also take an optional second parameter to set the initial value for the `accumulator`


