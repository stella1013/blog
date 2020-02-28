---
layout: post
title:  "Arrow Functions I love them but..."
date:   2020-02-27 15:45:31 -0500
categories: es6 react JavaScript TypeScript enzyme jest
---
As much as I love es6 arrow functions are short sweet and less binding to this worries than their prior to es6 function counterpart. I have found myself using them less as I encorporate more Shallow Unit Tests.

**Problem:**
Function is undefined while Shallow Testing.

**Why:**
Class Methods created using es6's Arrow Functions aren't included in an Class Object's prototype.

**Solution:**
Bind method to class

```js
  constructor(props:any){
  super(props);
  this.selectBuildTypeHandler = this.selectBuildTypeHandler.bind(this);
 }
```
