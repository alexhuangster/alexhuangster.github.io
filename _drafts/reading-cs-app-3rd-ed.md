---
title: "Reading CS:APP 3rd ED"
categories: Reading Computer
tags: computer-systems
math: true
---

This post contains my reading notes for [*Computer Systems: A Programmer's Perspective*, 3rd Edition](http://csapp.cs.cmu.edu/3e/home.html) (2015) by [Randal E. Bryant](http://www.cs.cmu.edu/~bryant) and [David R. O'Hallaron](http://www.cs.cmu.edu/~droh).

Source code: [https://github.com/alexhuangster/csapp3e](https://github.com/alexhuangster/csapp3e).

{% include toc.html %}

## Preface

> This book is written from a programmer's perspective, describing how application programmers can use their knowledge of a system to write better programs.

## Part I. Program Structure and Execution

### Chapter 2. Representing and Manipulating Information

#### 2.1 Information Storage

##### 2.1.2 Data Sizes 

The *word size* of a computer indicates the size of pointer data. The most important parameter determined by the word size is the maximum size of the *virtual address space*.

##### 2.1.3 Addressing and Byte Ordering

There are two ways to order bytes of objects:

- *Little endian*: the least significant byte comes first.
- *Big endian*: the most significant byte comes first.

In three cases, byte ordering becomes an issue:

1. When binary data are communicated over a network between different machines.
2. When looking at the byte sequences representing integer data. This occurs often when inspecting machine-level programs.
3. When programs are written that circumvent the normal type system. For example, a function to show bytes of an object, 

    ```c
    typedef unsigned char *byte_pointer;

    void show_bytes(byte_pointer start, size_t len) {
        int i;
        for (i = 0; i < len; i++)
            printf(" %.2x", start[i]);
        printf("\n");
    }
    ```

#### 2.2 Integer Representations

##### 2.2.2 Unsigned Encodings

$$
B2U_w(\vec{x})=\sum_{i=0}^{w-1} x_i 2^i
$$

$UMax_w=2^{w}-1$.

##### 2.2.3 Two's-Complement Encodings

$$
B2T_w(\vec{x})=
$$
