# Day 03 — Matrices and Matrix–Vector Products

## Learning objectives

You should be able to read matrix dimensions, decide whether a product is defined, compute $Ax$, and interpret it as a linear combination of the columns of $A$.

## 1. Matrices and dimensions

An $m\times n$ matrix has $m$ rows and $n$ columns:

```math
A=\begin{bmatrix}
a_{11}&\cdots&a_{1n}\\
\vdots&&\vdots\\
a_{m1}&\cdots&a_{mn}
\end{bmatrix}\in\mathbb{R}^{m\times n}.
```

The entry $a_{ij}$ is in row $i$, column $j$. If $x\in\mathbb{R}^n$, then $Ax\in\mathbb{R}^m$. The inner dimension $n$ must agree.

## 2. Two equivalent views of $Ax$

### Row view

The $i$-th component of $Ax$ is

```math
(Ax)_i=\sum_{j=1}^n a_{ij}x_j.
```

It combines row $i$ with all components of $x$.

### Column view

If $A=[a_1\ a_2\ \cdots\ a_n]$, where each $a_j\in\mathbb{R}^m$, then

```math
Ax=x_1a_1+x_2a_2+\cdots+x_na_n.
```

This connects matrix multiplication directly to linear combinations and span.



> For this part, to me it feels the "column view" is the transformation view: we are applying the transformation on each dimension to the exactly value on that dimension (say a_1 is the transformed point of 1st dimension of vector x). 
>
> On the other hand, the "row view" is more like a way of remembering how to getting the result quickly. 
>
> I do can write the both out by slowly thinking, but maybe I shall remember them so I can quickly link my thoughts with them whenever I need? Add a "cheat sheet" for me to collect things worth to remember so that I can review and even recite more often. 



## 3. Linearity

For compatible vectors $x,y$ and scalar $c$,

```math
A(x+y)=Ax+Ay,\qquad A(cx)=c(Ax).
```

Together these give $A(cx+dy)=cAx+dAy$. This is why a matrix represents a linear transformation.

> This is also intuitive, but I think I shall also remember them so I can recover quickly when I need. 
>
> BTW, I know a matrix means a transformation (from learning with 3b1b), but I didn't get the logic saying "This is why a matrix represents a linear transformation" here. 

## Worked example

Let

```math
A=\begin{bmatrix}1&2\\3&-1\\0&4\end{bmatrix},\qquad
x=\begin{bmatrix}2\\-1\end{bmatrix}.
```

Then $A\in\mathbb{R}^{3\times2}$, $x\in\mathbb{R}^2$, and $Ax\in\mathbb{R}^3$:

```math
Ax=2\begin{bmatrix}1\\3\\0\end{bmatrix}
-\begin{bmatrix}2\\-1\\4\end{bmatrix}
=\begin{bmatrix}0\\7\\-4\end{bmatrix}.
```

> For non-square matrix transformation, we are transforming the vector across different dimension space, right?
>
> The number of columns in transformation matrix means the number of basis vectors in the original space? I don't remember the detail and recovered that from my earlier notes, I forgot the reason behind. 



## Homework

### Core

1. For each product, state whether it is defined and give the output dimension:
   1. $Ax$, $A\in\mathbb{R}^{4\times3}$, $x\in\mathbb{R}^3$
   2. $Ax$, $A\in\mathbb{R}^{4\times3}$, $x\in\mathbb{R}^4$
   3. $BAx$, $A\in\mathbb{R}^{3\times2}$, $B\in\mathbb{R}^{5\times3}$, $x\in\mathbb{R}^2$
2. Compute $Ax$ using both the row and column views for
   ```math
   A=\begin{bmatrix}2&-1\\0&3\end{bmatrix},\qquad
   x=\begin{bmatrix}4\\2\end{bmatrix}.
   ```
3. Let $A=[a_1\ a_2\ a_3]$ and $x=[2,0,-1]^T$. Express $Ax$ using the columns without expanding their components.
4. Construct a $2\times2$ matrix $A$ such that $A[x_1,x_2]^T=[x_1+x_2,\,x_1-x_2]^T$ for every $x$.
5. Verify $A(x+y)=Ax+Ay$ numerically for one nontrivial choice of a $2\times2$ matrix and two vectors. Then explain why one example does not prove the identity.

### Diagnostic challenge

6. If $A\in\mathbb{R}^{m\times n}$, explain why every possible output $Ax$ lies in the span of the columns of $A$.

---

## My work

Show dimension checks before arithmetic.

![image-20260820205939400](./Day-03-matrices-and-matrix-vector-products.assets/image-20260820205939400.png)

![image-20260820210002452](./Day-03-matrices-and-matrix-vector-products.assets/image-20260820210002452.png)



## My reasoning

For Problems 4–6, explain how the matrix columns determine the result.

Each column describes a transformation of the corresponding dimension, all columns combined builds up the transformation of the entire vector x.  



## Confusions and questions

Record whether the row view or column view feels less secure, and why.

I think row view is less secure. They are numerically identical, but column view is its essence, while row view is a calculation result. 

