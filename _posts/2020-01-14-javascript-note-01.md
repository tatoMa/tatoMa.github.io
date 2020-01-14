---
date: 2020-01-14 10:48:05
layout: post
title: My notes by learning Javascript 01
subtitle: My notes by learning Javascript 01
description: My notes by learning Javascript 01 
image: /assets/img/uploads/2020-01-14.jpg
optimized_image: /assets/img/uploads/2020-01-14_s.jpg
category: code
tags:
  - blog
  - javascript
author: jasonma
paginate: false
---

# Notes - Frontend Masters - Getting started with js v2

### Types and coercion

#### Primitive Types

```js
var v
typeof v	// 'undefined'

v = '1'
typeof v	// 'string'

v = 2
typeof v	// 'number'

v = true
typeof v	// 'boolean'

v = {}
typeof v	// 'object'

v = Symbol()
typeof v	// 'symbol'
```

```js
typeof doesntExist	// 'undefined'

var v = null
typeof v	// 'object' one js bug for a long time

v = function(){}
typeof v	// 'function'

v= [1,2,3]
typeof v	//  'object'

```

####  NaN
```js
var greeting = 'Hello'

var something = greeting / 2

something	// NaN
typeof NaN	// 'number'
Number.isNaN( something )	//true

// NaN is unordered
NaN < 1;    // false
NaN > 1;    // false
NaN == NaN; // false

// Native JS isNan()
var x;            // undefined
isNaN(x);         // true
isNaN(undefined); // true
isNaN("a");       // true

// Booleans are not NaN
isNaN(true);  	// false
isNaN(false); 	// false
// is because booleans are considered as numerical values
Number(true);  // 1
Number(false); // 0

// Underscore isNan()
var x;              // undefined
_.isNaN(x);         // false
_.isNaN(undefined); // false
_.isNaN("a");       // false
```

####  Coercion( conversion)
```js
num = 10
num + ''	//'10' as number 10 is converted to string

// Number + Number = Number
// Number + String = String
// String + Number = String
// String + String = String

```

####  Falsy and Truthy
###### Falsy
- 0
- -0	//IEEE standard
- 0n //BigInt
- "", '', `` //empty strings
- NaN
- null
- false
- undefined

###### Everything else other than falsy is truthy





