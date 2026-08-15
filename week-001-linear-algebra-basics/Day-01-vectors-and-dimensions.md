# Day 01 — Vectors, Notation, and Dimensions

## Learning objectives

By the end of this session, you should be able to identify scalar and vector
objects, read indexed notation, check dimensions before calculating, and explain
what vector addition and scalar multiplication do component by component.

## 1. Scalars and vectors

A **scalar** is a single number. We write scalars as ordinary lowercase letters,
for example $a=3$ or $t=-1.5$.

A vector in ℝⁿ is an ordered list of $n$ real numbers:

```math
x=\begin{bmatrix}x_1\\x_2\\\vdots\\x_n\end{bmatrix}\in\mathbb{R}^n.
```

The statement $x\in\mathbb{R}^n$ specifies the type and dimension of $x$. The
subscript $x_i$ denotes component $i$; it is a scalar. Order matters, so

```math
\begin{bmatrix}1\\2\end{bmatrix}\ne
\begin{bmatrix}2\\1\end{bmatrix}.
```

## 2. Operations and their requirements

If $x,y\in\mathbb{R}^n$, addition is componentwise:

```math
x+y=\begin{bmatrix}x_1+y_1\\\vdots\\x_n+y_n\end{bmatrix}.
```

The vectors must have the same dimension. For a scalar $a\in\mathbb{R}$,

```math
ax=\begin{bmatrix}ax_1\\\vdots\\ax_n\end{bmatrix}.
```

A useful discipline is to check types before arithmetic. If $x\in\mathbb{R}^3$
and $y\in\mathbb{R}^2$, then $x+y$ is undefined; no calculation can repair the
dimension mismatch.

## 3. Special vectors

The zero vector in ℝⁿ is written $0$; its dimension is inferred from context.
The $i$-th standard basis vector $e_i\in\mathbb{R}^n$ has a 1 in position $i$
and zeros elsewhere. For example, in ℝ³,

```math
e_2=\begin{bmatrix}0\\1\\0\end{bmatrix}.
```

Every $x\in\mathbb{R}^n$ can be written as

```math
x=x_1e_1+x_2e_2+\cdots+x_ne_n.
```

## Worked example

Let

```math
x=\begin{bmatrix}2\\-1\\3\end{bmatrix},\qquad
y=\begin{bmatrix}0\\4\\1\end{bmatrix}.
```

Then

```math
2x-y=
\begin{bmatrix}4\\-2\\6\end{bmatrix}-
\begin{bmatrix}0\\4\\1\end{bmatrix}
=\begin{bmatrix}4\\-6\\5\end{bmatrix}.
```

Each intermediate vector is in ℝ³, so the subtraction is well-defined.

## Homework

### Core

1. Let $x=[3,-2,1]^T$ and $y=[-1,4,2]^T$. Compute:
   1. $x+y$
   2. $3x$
   3. $2x-y$
2. State whether each expression is defined. Give its type or explain the exact
   mismatch.
   1. $x+a$, where $x\in\mathbb{R}^3$, $a\in\mathbb{R}$
   2. $ax$, where $x\in\mathbb{R}^3$, $a\in\mathbb{R}$
   3. $x+y$, where $x\in\mathbb{R}^3$, $y\in\mathbb{R}^4$
   4. $x-y$, where $x,y\in\mathbb{R}^3$
3. Write $[5,0,-2]^T$ using $e_1,e_2,e_3$.
4. Find $a,b\in\mathbb{R}$ if
   $a[1,2]^T+b[1,-1]^T=[5,1]^T$. Show the two scalar equations you use.

### Diagnostic challenge

5. Suppose $x,y\in\mathbb{R}^n$ and $x+y=x$. What must $y$ be? Justify the
   conclusion without testing examples.

---

## My work

1. Compute:
   1. $x+y=[2, 2, 3]^T$
   2. $3x=[9, -6, 3]^T$
   3. $2x-y=[7, -8, 0]^T$
2. Defined or not:
   1. Undefined. Dimension mismatch (3 vs 1)
   2. Defined. Scalar times a vector
   3. Undefined. Dimension mismatch (3 vs 4)
   4. Defined. Dimension match
3. $[5, 0, -2]^T=5e_1+0e_2+(-2)e_3$
4. Scalar equations: $a+b=5, 2a-b=1$, then we have $a=2, b=3$
5. $y=0$, it must be a zero vector 

## My reasoning

For Problems 2, 4, and 5, explain why each conclusion follows.

2. Addition operation with 2 vectors must have identical dimension. Multiply a scalar with a vector is defined, it's simply scaling an existing vector. 

4. For 2D vectors, the resulting vector is the sum (can we call it combination?) of two **scaled** vectors, as long as all vectors have the same dimension and they are not in the same line (is it called linear independent?), we can get the result by scaling the two 'component' vectors. I remember there were some terms to describe this but I forgot - the combination of scaled 'component' vectors can fill up the whole space, or a subspace. 
5. A vector stays unchanged after an addition, meaning all values on each of its dimension added nothing, so it shall be added with a zero vector. 



## Confusions and questions

Record unclear notation or steps, even if you obtained the correct answer.

1. The 'i-th standard basis vector' written as $e_i\in \mathbb{R}$ is a convention?  
2. Are the addition of two vectors, multiplication of a number with a vector, called linear combination? 
