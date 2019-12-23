---
date: 2019-11-20 12:26:40
layout: post
title: Javascript Data structures and types
subtitle: Javascript - Data structures and types
description: The latest ECMAScript standard defines eight data types
image: /assets/img/uploads/2019-12-23.jpg
optimized_image: /assets/img/uploads/2019-12-23_s.jpg
category: code
tags:
  - blog
  - javascript
author: jasonma
---

## Data types
The latest ECMAScript standard defines eight data types:

- Seven data types that are primitives:
1. Boolean. true and false.
2. null. A special keyword denoting a null value. (Because JavaScript is case-sensitive, null is not the same as Null, NULL, or any other 3. variant.)
4. undefined. A top-level property whose value is not defined.
5. Number. An integer or floating point number. For example: 42 or 3.14159.
6. BigInt. An integer with arbitrary precision. For example: 9007199254740992n.
7. String. A sequence of characters that represent a text value. For example: "Howdy"
8. Symbol (new in ECMAScript 2015). A data type whose instances are unique and immutable.
- and Object

## Type Coercion

### Numbers and the '+' operator
#### In expressions involving numeric and string values with the **+ operator**, JavaScript converts numeric values to strings.
```js
x = 'The answer is ' + 42 // "The answer is 42"
y = 42 + ' is the answer' // "42 is the answer"

```

#### With **all other operators**, JavaScript does not convert numeric values to strings.
```js
'37' - 7 // 30
'37' + 7 // "377"

```

#### when `+` is faced with boolean values it's forced to convert them to numbers
```js
1 + 1 === 2 // => true

```

#### Falsy

- 0
- '' or ""
- null
- undefined
- NaN

```js
const zero = 0;
const emptyString = "";

if(!zero){
    console.log("0 is falsy");
}

if(!emptyString){
    console.log("An empty string is falsy")
}

console.log(NaN || 1); // => 1
console.log(null || 1); // => 1
console.log(undefined || 1); // => 1

```

#### Truthy

Every value that is not **falsy** is considered **truthy**, these include

- strings
- arrays
- objects
- functions

```js
function somethingIsWrong(){
    console.log("Something went horribly wrong")
}

function callback(){
    console.log("Hello From Callback");
}

const string = "Hello world!"
const array = [1,2,3];
const object = {};

if(string){
    console.log(string) // => "Hello world!"
    const functionToCall = callback || somethingIsWrong
    functionToCall() // => "Hello From Callback"
    console.log(array || "That was not meant to happen")
    console.log(object || "This is strange")
}

```



#### Converting strings to numbers
- parseInt()
- parseFloat()

`parseInt` only returns whole numbers, so its use is diminished for decimals

### Beware of type auto converting by checking the types

```js
const number = 21;
const string = "21"

function add100(number){
    console.log(100 + number)
}

add100(number) // => 121
add100(string) // => "10021"

```

##### with type checking

```js
const number = 21;
const string = "21"

function add100(number){
    if(typeof number == "number"){
        console.log(100 + number)
    } else {
        console.log("Need a number, not a "+typeof number);
    }
}

add100(number) // => 121
add100(string) // => "Need a number, not a string"

```

##### for checking if using `class`

```js
class ImportantClass {
    constructor(){
        this.importantValue = 1;
    }

    doImportantStuff(){
        console.log(this.importantValue);
    }
}

function useImportantClass(value){
    if(value instanceof ImportantClass){
        value.doImportantStuff();
    } else {
        console.log("Value needs to be of type ImportantClass, not "+typeof value)
    }
}

const value = new ImportantStuff();

useImportantClass(value); // => 1
useImportantClass("Not important"); // => Value needs to be of type ImportantClass, not string

```











