---
title: "Notes on CSAPP3e"
categories: Computer Reading
tags: computer-systems
math: true
---

These are notes on the book [*Computer Systems: A Programmer's Perspective*, 3rd Edition](https://csapp.cs.cmu.edu/), which was written by [Randal E. Bryant](http://www.cs.cmu.edu/~bryant/) and [David R. O'Hallaron](http://www.cs.cmu.edu/~droh/) and published in 2015.

{% include toc.html %}

## Part I. Program Structure and Execution

### Chapter 2. Representation and Manipulating Information

#### 2.1 Information Storage

The *word size* of a computer is the nominal size of pointer data type (the address of virtual memory). The most important system parameter determined by the word size is the maximum size of the virtual address space. A 32-bit word size machine limits the virtual address space to $2^{32} \approx 4\times10^9$ bytes (4 GB); For a 64-bit machine, it's $2^{64} \approx 1.84\times10^{19}$ bytes (16 [EB](https://zh.wikipedia.org/wiki/%E8%89%BE%E5%AD%97%E8%8A%82)).

There are two conventions for ordering bytes in virtual address space. If the least significant byte comes first, it is *little endian*; If the most significant byte comes first, it is *big endian*.

There are three cases where byte ordering becomes visible.

1. Sending data between machines with different byte orderings.
2. Inspecting machine-level programs.
3. Circumvent the normal type system, which often happens in system-level programming.

Here is a C function that can show the byte ordering of any object.

```c
typedef unsigned char *byte_pointer;

void show_bytes(byte_pointer start, size_t len) {
    size_t i;
    for (i = 0; i < len; i++)
        printf(" %.2x", start[i]);
    printf("\n");
}
```