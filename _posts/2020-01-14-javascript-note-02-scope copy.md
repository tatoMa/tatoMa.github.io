---
date: 2020-01-13 10:49:05
layout: post
title: Easy way to understand the scope of Javascript
subtitle: My notes by learning Javascript 02
description: My notes by learning Javascript 02
image: /assets/img/uploads/2020-01-14-2.jpg
optimized_image: /assets/img/uploads/2020-01-14-2_s.jpg
category: code
tags:
  - blog
  - javascript
author: jasonma
paginate: false
---

# Notes 02 - Frontend Masters - Getting started with js v2

### Scope / Closures

```js
var teacher = 'Kyle'

function otherClass() {
	teacher = 'Suzy'
	topic = 'react'
	console.log('Welcome')
}

otherClass()

teacher    // 'Suzy'
topic	// 'react'
```

###### Explaination:
First thing needs to notice is this code doesn't have the **'use strict'** key word to enable the strict mode of Javascript. Therefore, based on the 'loosy mode' of Javascript, it behaves different as the strict mode. 

Line 1 declare a string called teacher and assign its value as 'Kyle'. When runs line 9 it invokes the function called otherClass and tries assign the **teacher** variable to the value of 'Suzy'. First, the JS engine(suck as V8 by Chrome or Spider Monkey by Firefox) will try to find a variable called **teacher** at the same scope (inside of the same level of curly braces), as cannot find anyone called **teacher** so it goes outside one level of it scope which is global. Finally, finds the **teacher** in the global scope and assign it to **'Suzy'**

Line 5 also tries to assign a variable to a new value, but cannot find it not only inside of the same scope but also the global scope. Beware of the **'loosy mode'** of Javascript, it will automatically create a variable when it cannot find but need to assign a value. At the end, a variable called **topic** is created and assign it to **'react'**.





