# Day 02 — Gram–Schmidt and Orthonormal Bases

## Learning objectives

You should be able to distinguish orthogonal from orthonormal vectors and apply Gram–Schmidt to two independent vectors.

## 1. Orthogonal and orthonormal sets

Vectors $q_1,\ldots,q_k$ are **orthonormal** when

```math
q_i^Tq_j=0\quad(i\neq j),
\qquad
q_i^Tq_i=1.
```

If $Q=[q_1\ \cdots\ q_k]$, these conditions can be written compactly as

```math
Q^TQ=I_k.
```

An orthonormal set is linearly independent: if $c_1q_1+\cdots+c_kq_k=0$, multiply by $q_j^T$ to obtain $c_j=0$.

## 2. Gram–Schmidt for two vectors

Let $a_1,a_2$ be linearly independent. First normalize $a_1$:

```math
q_1=\frac{a_1}{\lVert a_1\rVert_2}.
```

Remove from $a_2$ its component along $q_1$:

```math
w_2=a_2-(q_1^Ta_2)q_1.
```

Then normalize the remaining vector:

```math
q_2=\frac{w_2}{\lVert w_2\rVert_2}.
```

The vectors $q_1,q_2$ are orthonormal and span the same subspace as $a_1,a_2$.

## Worked example

Let $a_1=[1,1]^T$ and $a_2=[1,0]^T$. Then

```math
q_1=\frac{1}{\sqrt{2}}\begin{bmatrix}1\\1\end{bmatrix}.
```

Next,

```math
w_2
=a_2-(q_1^Ta_2)q_1
=\begin{bmatrix}1/2\\-1/2\end{bmatrix},
```

so

```math
q_2=\frac{1}{\sqrt{2}}\begin{bmatrix}1\\-1\end{bmatrix}.
```

Direct calculation gives $q_1^Tq_2=0$ and $\lVert q_1\rVert_2=\lVert q_2\rVert_2=1$.

## Homework

### Core

1. Determine whether $[1,0,1]^T$ and $[1,1,-1]^T$ are orthogonal. Normalize both if possible.
2. Apply Gram–Schmidt to $a_1=[1,0,1]^T$ and $a_2=[1,1,0]^T$. Verify both orthogonality and unit length.
3. Apply Gram–Schmidt to $a_1=[1,1]^T$ and $a_2=[2,2]^T$. Explain exactly why the procedure cannot produce a second orthonormal vector.
4. Prove that $w_2=a_2-(q_1^Ta_2)q_1$ is orthogonal to $q_1$.
5. Explain why $\operatorname{span}(q_1,q_2)=\operatorname{span}(a_1,a_2)$ in the two-vector construction. Show both containment directions.

### Optional proof diagnostic

Prove that every orthonormal set is linearly independent by isolating an arbitrary coefficient with an inner product.

---

## My solutions

## My reasoning

Track which vectors are normalized and verify every denominator is nonzero before dividing.

## Confusions and questions

---

## Review

## Corrections I should retain
