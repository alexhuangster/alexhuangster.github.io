---
title: "Notes on Dasgupta's Algorithms"
categories: Computer Reading
tags: algorithms
math: true
---

These are notes on the book [*Algorithms*](https://cseweb.ucsd.edu/~dasgupta/book/index.html) which was written by [Sanjoy Dasgupta](https://cseweb.ucsd.edu/~dasgupta/) and published in 2008.

{% include toc.html %}

## Chapter 0. Prologue

### 0.2. Enter Fibonacci

> No other sequence of numbers has been studied as extensively, or applied to more fields: biology, demography, art, architecture, music, to name just a few. And, together with the powers of 2, it is computer science’s favorite sequence.

The Fibonacci sequence is defined as

$$
F_n = 
\begin{cases}
0, & n = 0 \\
1, & n = 1 \\
F_{n-1} + F_{n-2}, & n > 1
\end{cases}
$$

Below is a try to find the growing pattern of $F_n$.

Since $F_{n-1} \geq F_{n-2}$, we have $2F_{n-2} \leq F_{n} \leq 2F_{n-1}$. First, pay attention to the right side inequality, it is easy to get that $F_{n} \leq 2^{n-2}F_{2} = 2^{n-2} < 2^{n}$. Next, we consider that left side inequality, there are two cases:

1. If $n$ is odd, we get that 
   
   $$
   \begin{align}
   F_{n} &\geq 2F_{n-2} \geq 2^{2}F_{n-2\times2} \geq 2^{3}F_{n-2\times3} \geq \cdots \\
         &\geq 2^{(n-3)/2}F_{3} \\
         &= 2^{(n-3)/2}\times2 \\
         &= 2^{0.5n-0.5}
   \end{align}
   $$

2. If $n$ is even, the inference is similar to the above, and finally we get that
   
   $$
   F_{n} \geq 2^{(n-2)/2}F_{2} = 2^{0.5n-1}
   $$

Can we cut off the constants in the exponents so that let these inequalities look more simple and beautiful? Yes, we can. The answer is to adjust the range of $n$, since we are only interested in taking $n$ larger values.

1. Considering the odd case.

    $$
    F_{n} \geq 2^{(n-5)/2}F_{5} = 2^{0.5n-2.5}\times5 \approx 2^{0.5n} \times 0.88...
    $$

    Oops!

    $$
    F_{n} \geq 2^{(n-7)/2}F_{7} = 2^{0.5n-3.5}\times13 \approx 2^{0.5n} \times 1.14... > 2^{0.5n}
    $$
    
    OK! We know that all odd integers $n \geq 7$, we have $F_{n} \geq 2^{0.5n}$.

2. Considering the even case.

    $$
    F_{n} \geq 2^{(n-4)/2}F_{4} = 2^{0.5n-2}\times3 = 2^{0.5n} \times 0.75
    $$

    Oops!

    $$
    F_{n} \geq 2^{(n-6)/2}F_{6} = 2^{0.5n-3}\times8 = 2^{0.5n}
    $$

    OK! We know that all even integers $n \geq 6$, we have $F_{n} \geq 2^{0.5n}$.

In summary, for all integers $n \geq 6$, we have $F_{n} \geq 2^{0.5n}$. $\blacksquare$

The next question is: Can we find a constant $c$ so that $F_n = \Theta(2^{cn})$? 

We are very confident that the constant is existed, since we have proved that for all $n \geq 6$, $2^{0.5n} \leq F_{n} \leq 2^n$ is held.

We suppose it is existed, then $F_n \leq 2^{cn}$ is held for large $n$. Mathematical induction could be used to prove this inequality, i.e. the inference below should be held.

$$
F_n = F_{n-1} + F_{n-2} \leq 2^{c(n-1)} + 2^{c(n-2)} \Rightarrow F_n \leq 2^{cn}
$$

It is equivalent to calculate the solution to $2^{c(n-1)} + 2^{c(n-2)} \leq 2^{cn}$.

The inference of the case $F_n \geq 2^{cn}$ is similar, so finally we just need to solve $2^{c(n-1)} + 2^{c(n-2)} = 2^{cn}$.

Let $x = 2^c$,

$$
x^2 - x - 1 = 0 \Rightarrow x=\frac{1 + \sqrt{5}}{2} \Rightarrow c = \log_{2}(\frac{1 + \sqrt{5}}{2}) \approx 0.6942419136306174
$$

## Exercises

### 0.4

> Is there a faster way to compute the nth Fibonacci number than by `fib2` (page 4)? One idea involves matrices.
>
> We start by writing the equations $F_1=F_1$ and $F_2 = F_0 + F_1$ in matrix notation:
> 
> $$
> \begin{pmatrix}
> F_1\\ 
> F_2
> \end{pmatrix} =
> \begin{pmatrix}
> 0 & 1\\ 
> 1 & 1
> \end{pmatrix} \cdot
> \begin{pmatrix}
> F_0\\ 
> F_1
> \end{pmatrix}
> $$
>
> Similarly,
> 
> $$
> \begin{pmatrix}
> F_2\\ 
> F_3
> \end{pmatrix} =
> \begin{pmatrix}
> 0 & 1\\ 
> 1 & 1
> \end{pmatrix} \cdot
> \begin{pmatrix}
> F_1\\ 
> F_2
> \end{pmatrix} = 
> \begin{pmatrix}
> 0 & 1\\ 
> 1 & 1
> \end{pmatrix}^2 \cdot
> \begin{pmatrix}
> F_0\\ 
> F_1
> \end{pmatrix}
> $$
>
> and in general
>
> $$
> \begin{pmatrix}
> F_n\\ 
> F_{n+1}
> \end{pmatrix} =
> \begin{pmatrix}
> 0 & 1\\ 
> 1 & 1
> \end{pmatrix}^n \cdot
> \begin{pmatrix}
> F_0\\ 
> F_1
> \end{pmatrix}
> $$
> 
> So, in order to compute $F_n$, it suffices to raise this $2\times2$ matrix, call it $X$, to the nth power.
>
> (a) Show that two $2\times2$ matrices can be multiplied using 4 additions and 8 multiplications.

Just directly expand the calculation of matrix multiplication, the answer would be shown.

> But how many matrix multiplications does it take to compute $X^n$?
> 
> (b) Show that $O(\log n)$ matrix multiplications suffice for computing $X^n$. (Hint: Think about computing $X^8$.)

$$
X^8 = X^4 \cdot X^4 \\
X^4 = X^2 \cdot X^2 \\
X^2 = X \cdot X
$$

So for calculating $X^8$, you just need to do 3 matrix multiplications.

Suppose $n = 2^{e_1} + 2^{e_2} + \cdots + 2^{e_t}$, where $e_1 > e_2 > \cdots > e_t \geq 0$, then for computing $X^n$, we just need to do $e_1$ matrix multiplications if $n$ is even, and $e_1 + 1$ times if $n$ is odd. So we get $O(\log n)$ matrix multiplications.

> Thus the number of arithmetic operations needed by our matrix-based algorithm, call it `fib3`, is just $O(\log n)$, as compared to $O(n)$ for `fib2`. Have we broken another exponential barrier?
> 
> The catch is that our new algorithm involves multiplication, not just addition; and multiplications of large numbers are slower than additions. We have already seen that, when the complexity of arithmetic operations is taken into account, the running time of `fib2` becomes $O(n^2)$.
> 
> (c) Show that all intermediate results of `fib3` are $O(n)$ bits long.
> 