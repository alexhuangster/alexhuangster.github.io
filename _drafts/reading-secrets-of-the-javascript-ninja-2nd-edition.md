---
title: "Reading Secrets of the JavaScript Ninja, 2nd Edition"
categories: Reading Computer
tags: javascript
---

This post contains some notes I took while I was reading [*Secrets of the JavaScript Ninja*, 2nd Edition](https://www.manning.com/books/secrets-of-the-javascript-ninja-second-edition) by [John Resig](https://johnresig.com/), [Bear Bibeault](https://twitter.com/bear_bibeault), and Josip Maras.

{% include toc.html %}

## Part I. Warming up

### Chapter 1. JavaScript is everywhere

> What are Babel and Traceur, and why are they important to today’s JavaScript developers?

[Babel](https://babeljs.io/) is a JavaScript compiler. In detail, Babel is a toolchain that is mainly used to convert ECMAScript 2015+ code into a backwards compatible version of JavaScript in current and older browsers or environments. So you can use next generation JavaScript, today.

[Traceur](https://github.com/google/traceur-compiler) is also a JavaScript compiler which let you write future JavaScript in today.

> What are the core parts of any web browser’s JavaScript API used by web applications?

[DOM](https://en.wikipedia.org/wiki/Document_Object_Model) and [BOM](https://en.wikipedia.org/wiki/Browser_Object_Model)?

#### The JavaScript language

Some JavaScript concepts differ fundamentally from those of most other languages:

- *Functions are first-class objects*: Functions in JavaScript can be created through literals, referenced by variables, passed around as function arguments, and even returned as function return values.
- *Function closures*: A function is a closure when it actively maintains (“closes over”) the external variables used in its body.
- *Scopes*: Until recently, JavaScript didn’t have block-level variables.
- *Prototype-based object orientation*.

In addition to these fundamental concepts, other JavaScript features can help programmers to write more elegant and more efficient code:

- *Generators*
- *Promises*
- *Proxies*
- *Advanced array methods*
- *Maps*
- *Regular expressions*
- *Modules*
