---
title: "Notes on The C Programming Language, 2nd Edition"
categories: Reading Computer
tags: c
---

Here are some notes I took when I was reading [*The C Programming Language*, 2nd Edition](https://www.amazon.com/Programming-Language-2nd-Brian-Kernighan/dp/0131103628) (1988) written by [Kernighan](https://www.cs.princeton.edu/~bwk/) and [Ritchie](https://www.bell-labs.com/usr/dmr/www/) -- the famous [K&R](https://en.wikipedia.org/wiki/K%26R).

{% include toc.html %}

## Introduction

Some points to show the "low-level" aspects of C:

- No operations to deal directly with composite objects such as character strings, sets, lists, or arrays.
- No operations that manipulate an entire array or string, although structures may be copied as a unit.
- No any storage allocation facility other than static definition and the stack discipline provided by the local variables of functions; there is no heap or garbage collection.
- No input/output facilities; there are no READ or WRITE statements, and no built-in file access methods.