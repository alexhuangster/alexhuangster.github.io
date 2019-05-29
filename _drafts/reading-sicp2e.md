---
title: "Reading SICP2e"
categories: Reading Computer
tags: lisp scheme programming
---

This post contains some notes I took while I was reading [*Structure and Interpretation of Computer Programs*, 2nd Edition](https://mitpress.mit.edu/sites/default/files/sicp/full-text/book/book.html) by [Harold Abelson](http://groups.csail.mit.edu/mac/users/hal/hal.html) and [Gerald Jay Sussman](http://groups.csail.mit.edu/mac/users/gjs/gjs.html) with Julie Sussman.

{% include toc.html %}

## Chapter 1. Building Abstractions with Procedures

### 1.1 The Elements of Programming

Every powerful language has three mechanisms for accomplishing building complex ideas form simple ones: 

- **primitive expressions**, which represent the simplest entities the language is concerned with,
- **means of combination**, by which compound elements are built from simpler ones, and
- **means of abstraction**, by which compound elements can be named and manipulated as units.
  
Primitive expressions introduced in this chapter only include *numbers*.

Scheme provides some *primitive procedures* let you to do combination. These include `+`, `-`, `*`, and `/`.

Two basic means of abstraction are defining *variables* and defining *compound procedures*.

```
(define <name> <value>)
(define (<name> <formal parameters>) <body>)
```

#### The Substitution Model for Procedure Application

> To apply a compound procedure to arguments, evaluate the body of the procedure with each formal parameter replaced by the corresponding argument.

But remember that

> - The purpose of the substitution is to help us think about procedure application, not to provide a description of how the interpreter really works.
> - Over the course of this book, we will present a sequence of increasingly elaborate models of how interpreters work, culminating with a complete implementation of an interpreter and compiler in chapter 5. 

culminate: reach a climax or point of highest development.

There are two orders of evaluation:

- *normal-order*: fully expand and then reduce.
- *applicative-order*: evaluate the arguments and then apply.

Applicative-order evaluation could make the process more efficient and not error-prone.

#### Conditional Expressions and Predicates

Scheme provides two forms of conditional expressions:

```
(cond (<p1> <e1>)
    (<p2> <e2>)
    ...
    (<pn> <en>))

(if <predicate> <consequent> <alternative>)
```

Comparing with `cond`, `if` is restricted and can be replaced by using `cond` to express the same purpose:

```
(cond (<predicate> <consequent>) (else <alternative>))
```

So why do we need the additional `if` since we already have `cond`? I guess the reason is that the syntax of `if` is more compact -- fewer parentheses and no the `else` keyword.
