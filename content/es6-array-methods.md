+++
title = "ES6: Array methods"
slug = "es6-array-methods"
layout = "page.html"
date = 2020-09-02
draft = false
[taxonomies]
tags = ["javascript", "es6"]
+++

**Arrays** are one of the fundamental data structures supported in most programming environments out-of-the box (you can even use an array in ASSEMBLY). Often times, a collection of built-in array methods are provided by the language itself. This is a compilation of those in modern JavaScript (ES6).

## **map()**

Returns a new array based on an existing array where the function passed is executed for each element on the array.
- Original array is not mutated.
- The size of the returend array is always if the same size as the original array.

```js
let myArray = [1, 3, 5, 7, 9]
myArray.map(el => el + 1)
//=> [ 2, 4, 6, 8, 10 ]
```
## **filter()**

Returns a new array based on truth condition on callback function passed to it.

- Original array is not mutated.
- The size of the returend array is a subset of the original array.

```js
let myArray = [1, 3, 5, 7, 9]
myArray.filter(el => el > 0)
//=> [ 1, 3, 5, 7, 9 ]
myArray.filter(el => el > 4)
//=> [ 5, 7, 9 ]
myArray.filter(el => el > 10)
//=> []
```
## **find()**

Returns the first value from the array that returns `true` for the conditional defined and stops iteration.

- Retuns one value - value can be any data type (primitive or objects).

```js
let myArray = [1, 3, 5, 7, 9]
myArray.find(el => el === 5)
//=> 5

let peopleArray = [{id: 1}, {id: 4}, {id: 7}]
peopleArray.find(el => el.id === 4)
//=> {id: 4}
```

## **includes()**

Checks the reference we're passing is equal to any of the elements inside by their memory reference

- Takes 2 arguments
    > arg1 - any element that we want - checks if the argument exists in the array

    > arg2 - the array index in which we want to start searching (inclusive of the index) [optional]

- Works differently for primitive data types (6: string, boolean, null, undefined, number, symbol) and objects (arrays, objects)


```js
// --- USE1 - primitive data types
array = [1,2,3,4,5]
array.includes(1) // true
array.includes(3, 2) // true
array.includes(3, 3) // false

// --- USE2 - objects
let newArray = [{id: 1}, {id: 4}, {id: 7}]
newArray.includes({id: 2})
//=> false
```

## **reduce()**

Returns 1 value by performing some operation on all elements of an array

Persists the outcome of iterating over our elements in each subsequent iteration

- Takes 2 arguments
    > arg1 - function with 2 parameters (accumulator, currentElement)

    > arg2 - initial value of the accumulator

```js
array = [1,2,3,4,5]
array.reduce((accumulator, currentElement) => accumulator + currentElement, 0)
//=> 15
let myArray = [1, 3, 5, 7, 9]
myArray.map(el => el + 1)
//=> [ 2, 4, 6, 8, 10 ]
```