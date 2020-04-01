---
layout: post
title: 'Arrow Functions I them but...'
categories: es6 react JavaScript TypeScript enzyme jest
subtitle:
tags: [intro]
author: Veronica Preston

---

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
