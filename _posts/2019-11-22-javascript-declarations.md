---
date: 2019-11-22 12:26:40
layout: post
title: Javascript Declarations
subtitle: LJavascript Declarations
description: When declare by using var and led with no initial assigned value, undefined will be assigned them. But the different is var will always hoisted but let will not.
image: /assets/img/uploads/2019-11-20-Javascript.jpg
optimized_image: /assets/img/uploads/2019-11-20-Javascript_s.jpg
category: code
tags:
  - blog
  - javascript
author: jasonma
---

## Variables
When declare by using var and led with no initial assigned value, undefined will be assigned them. But the different is var will always hoisted but let will not.

```js
var a;
console.log('The value of a is ' + a); // The value of a is undefined

console.log('The value of b is ' + b); // The value of b is undefined
var b;

console.log('The value of c is ' + c); // Uncaught ReferenceError: c is not defined

let x;
console.log('The value of x is ' + x); // The value of x is undefined

console.log('The value of y is ' + y); // Uncaught ReferenceError: y is not defined
let y; 
```


### undefined
Using undefined if you want to ensure that the value of a variable is not assigned. 
```js
var input;
if (input === undefined) {
  console.log('true');
} else {
  console.log('false');
}

```

#### The undefined value converts to NaN when used in numeric context.
```js
var a;
a + 2;  // Evaluates to NaN

```

#### the null value behaves as 0 in numeric contexts and as false in boolean contexts.
```js
var n = null;
console.log(n * 32); // Will log 0 to the console

```

## Variable scope
When you declare a variable outside of any function, it is called a global variable, because it is available to any other code in the current document. When you declare a variable within a function, it is called a local variable, because it is available only within that function.

### The different of scopes between var and let

```js
if (true) {
  var x = 5;
}
console.log(x);  // x is 5

if (true) {
  let y = 5;
}
console.log(y);  // ReferenceError: y is not defined

```
It is because the scope of x is the global context but the scope of y is the immediate if statement block.

## Variable hoisting

### hoisting for var and IIFE
```
/**
 * Example 1
 */
console.log(x === undefined); // true
var x = 3;

/**
 * Example 2
 */
// will return a value of undefined
var myvar = 'my value';
 
(function() {
  console.log(myvar); // undefined
  var myvar = 'local value';
})();

```

#### Explaniation of hoisting
These all examples are as same as above
```js
/**
 * Example 1
 */
var x;
console.log(x === undefined); // true
x = 3;
 
/**
 * Example 2
 */
var myvar = 'my value';
 
(function() {
  var myvar;
  console.log(myvar); // undefined
  myvar = 'local value';
})();

```
Because of hoisting, all var statements in a function should be placed as near to the top of the function as possible.

#### In ECMAScript 2015, let and const are hoisted but not initialized.
```js
console.log(x); // ReferenceError
let x = 3;

```
Referencing the variable in the block before the variable declaration results in a ReferenceError, because the variable is in a "temporal dead zone" from the start of the block until the declaration is processed.
`

## Function hoisting
Only function declarations are hoisted—but not the function expressions.
```js
/* Function declaration */

foo(); // "bar"

function foo() {
  console.log('bar');
}


/* Function expression */

baz(); // TypeError: baz is not a function

var baz = function() {
  console.log('bar2');
};

```

## Global variables
Global variables are in fact properties of the global object.

In web pages, the global object is `window`, so you can set and access global variables using the window.variable syntax.

## Constants
const is the keyword to define a constant which cannot reassigned in Javascript. However, the properties of objects assigned to constants are not protected.
```js
const MY_OBJECT = {'key': 'value'};
MY_OBJECT.key = 'otherValue';

```
Also, the contents of an array are not protected, so the following statement is executed without problems.

```js
const MY_ARRAY = ['HTML','CSS'];
MY_ARRAY.push('JAVASCRIPT');
console.log(MY_ARRAY); //logs ['HTML','CSS','JAVASCRIPT'];
```











