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
2. State whether each expression is defined. Give its type or explain the exact mismatch.
   1. $x+a$, where $x\in\mathbb{R}^3$, $a\in\mathbb{R}$
   2. $ax$, where $x\in\mathbb{R}^3$, $a\in\mathbb{R}$
   3. $x+y$, where $x\in\mathbb{R}^3$, $y\in\mathbb{R}^4$
   4. $x-y$, where $x,y\in\mathbb{R}^3$
3. Write $[5,0,-2]^T$ using $e_1,e_2,e_3$.
4. Find $a,b\in\mathbb{R}$ if $a[1,2]^T+b[1,-1]^T=[5,1]^T$. Show the two scalar equations you use.

### Diagnostic challenge

5. Suppose $x,y\in\mathbb{R}^n$ and $x+y=x$. What must $y$ be? Justify the conclusion without testing examples.

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

---

## Review

### Assessment

**Developing.** The computations in Problems 1, 3, and 4 are correct, and the
conclusion in Problem 5 is correct. The main weakness is distinguishing an
object's type from its dimension and stating conclusions with precise notation.

### Problem feedback

1. All three computations are correct.
2. The defined/undefined conclusions are correct, but two details need revision:
   - In 2.1, $a\in\mathbb{R}$ is a scalar, not a vector of dimension 1. Thus
     $x+a$ has a **type mismatch**, not a dimension mismatch between 3 and 1.
     Ordinary vector addition requires both operands to be vectors in the same
     vector space.
   - For each defined expression, the requested output type is missing. In 2.2
     and 2.4, the result lies in $\mathbb{R}^3$.
3. Correct. Including $0e_2$ is valid and makes every coordinate visible.
4. The scalar equations and solution $a=2$, $b=3$ are correct. The expression
   $a[1,2]^T+b[1,-1]^T$ is a **linear combination**. The two given vectors are
   not scalar multiples, so they are **linearly independent**; in
   $\mathbb{R}^2$, their linear combinations fill, or **span**, all of
   $\mathbb{R}^2$. Independence explains why the representation is unique, but
   it is not needed merely to write and solve the two scalar equations.
5. The conclusion is correct, but the justification should be explicit. From
   $x_i+y_i=x_i$ for every component $i$, subtract $x_i$ to obtain $y_i=0$ for
   every $i$. Therefore $y$ is the zero vector in $\mathbb{R}^n$.

### Answers to your questions

1. $e_i$ is the conventional name for the $i$-th standard basis vector, but the
   complete statement is $e_i\in\mathbb{R}^n$, not $e_i\in\mathbb{R}$. The
   subscript $i$ identifies the position containing 1; the other components are
   zero.
2. Yes. A linear combination is any sum of scalar multiples
   $c_1v_1+\cdots+c_kv_k$. Thus $x+y=1x+1y$ is a linear combination of $x$ and
   $y$, and $ax$ is a linear combination containing one vector.

## Corrections I should retain

Before beginning Day 2, add your corrections below without deleting the original answers:

1. Rewrite all four parts of Problem 2, distinguishing scalar/vector **type** from vector **dimension** and stating the result space when defined.
2. Rewrite the proof for Problem 5 componentwise in your own words.
3. Write the third standard basis vector of $\mathbb{R}^4$ explicitly and state its type.

----

## Corrections

Problem 2:

1. Undefined. Dimension mismatch. Vector addition requires two operands in the same dimension. 
2. Defined. Result type is a vector in $\mathbb{R}^3$. It's scaling a vector with a scalar. 
3.  Undefined. Dimension mismatch. Vector addition requires two operands in the same dimension. 
4. Defined. Result type is a vector in $\mathbb{R}^3$. 

Problem 5: $y$ must be a $n$-dimension zero vector.  $\forall x\in\mathbb{R}^n$ , for each of its component $x_i$, only $x_i + 0=x_i$.  



The third standard basis vector of $\mathbb{R}^4$ : $e_3\in \mathbb{R}^4, e_3=[0, 0, 1, 0]^T$. Its type is a 4-dimension vector. 

### Correction review — 2026-08-15

1. **Problem 2:** Parts 2.2, 2.3, and 2.4 are now correct. Part 2.1 is not yet corrected: $x$ is a vector and $a$ is a scalar, so the failure occurs before dimensions can be compared. Calling it a dimension mismatch repeats the original type error.
2. **Problem 5:** The conclusion remains correct, but the proof does not yet use the given equation. The statement “only $x_i+0=x_i$” assumes the component added to $x_i$ is already zero. Start from $x_i+y_i=x_i$ and state the algebraic operation applied to both sides to determine $y_i$. The quantifier $\forall x\in\mathbb{R}^n$ is unnecessary because the problem concerns the given $x$ and $y$.
3. **Standard basis vector:** Correct. Prefer “a vector in $\mathbb{R}^4$” or “a four-dimensional vector” for the type description.

**Decision:** Remain at **Developing**. Revise only Problem 2.1 and the Problem 5 proof; after those two corrections, begin Day 2.

### Corrections 2:

Problem 2.1: Undefined. for $a\in \mathbb{R}$, it's a scalar, not a vector. The vector addition is not defined for a vector and a scalar operands. 

Problem 5:
$$
x, y\in \mathbb{R}^n, \\
x+y=x, \\
\text{substract }x \text{on both sides, therefore}: y=0, \text{where } y\in \mathbb{R}^n
$$

### Final correction review — 2026-08-15

1. **Problem 2.1:** Accepted. You now identify $x$ as a vector and $a$ as a scalar and correctly explain that ordinary vector addition is not defined between those operand types.
2. **Problem 5:** Accepted. Subtracting the vector $x$ from both sides is valid and gives $y=0$. Writing “$0\in\mathbb{R}^n$ is the zero vector” would state the result's type more directly, but no further correction is required.

**Decision:** The Day 1 corrections are complete. The topic remains **Developing** because the corrected distinctions were learned with feedback and still need independent retrieval evidence. Begin Day 2.
