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

The basic philosophy of C is that **programmers know what they are doing**. Based on this, C has no strong type-checking.

## Types, Operators, and Expressions

### Variable Names

> At least the first 31 characters of an internal name are significant. For function names and external variables, the number may be less than 31, because external names may be used by assemblers and loaders over which the language has no control. For external names, the standard guarantees uniqueness only for 6 characters and a single case.

An [easy-to-misunderstand paragraph. There is some [discussion on Stack Overflow](paragraph) about this paragraph. According to an [answer](https://stackoverflow.com/a/12979078/11397411) by [O. Jones](https://stackoverflow.com/users/205608/o-jones), modern compilers and toolchains no longer have different name-length limitations. 

So I know why all names of functions in C standard library are so short.
