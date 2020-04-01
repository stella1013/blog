---
layout: post
title: map-polyfill
---

**Abstraction:**
It's the way to write Javascript so that you dont need to know the inner workings of a method to use it. You trust that it works. And it just does. I'm going to break down a popular method used to traverse and return arrays. the map() Higher Order Function.

**Starting:**
Before starting lets set up our array and also what functions we want to perform on each element of the array.

```js
const myArray = [22, 9, 60, 12, 4, 56];
const dup = (x: number) => 2 * x;
```

We want to create/initialize a function that accepts n arguments.
these arguments are:

```js
function manualMap(callBackfn:(...args:any)=>any, arr:any[]):any[]{
```

The first thing we will do is set up some initial variables.

```js
let fn: () => any;
var arrayData: any[];
var arrayIndex: number;
```

Then we want to check to make sure we have everything we need.

```js
if (callBackfn == null) {
	throw new TypeError('fn is null or not defined');
}
var obj = arr; //Object(arr); ///orig Object(this). do I pass array?
var len = arr.length >>> 0; ///obj.length >>> 0; /// why bitwise operators
if (typeof callBackfn !== 'function') {
	throw new TypeError(callBackfn + ' is not a function');
}
if (arguments.length > 1) {
	fn = arguments[1]; //callBackfn assigns our operating function
}
```

Then till the end let's loop and perform an operation using our supplied function till the end.

```js
    arrayData = new Array(len);
    arrayIndex = 0;

    while(arrayIndex < len) {
        var kValue;
        var mappedValue;

    if(arrayIndex in obj) {
        kValue = obj[arrayIndex];
        mappedValue = callBackfn.call(fn);
        arrayData[arrayIndex] = mappedValue;
    }

    arrayIndex++
```

Then when it has reached the end. We will return our new array.

```js
return arrayData;
```
**How does this stack up in performance to map**
show perfomance here.

**Find it in the mdn docs**