# Day 03 — Projection onto a Subspace

## Learning objectives

You should be able to project onto a subspace with an orthonormal basis, construct the projection matrix, and verify its main algebraic properties.

## 1. Projection using an orthonormal basis

Let $Q\in\mathbb{R}^{m\times k}$ have orthonormal columns $q_1,\ldots,q_k$, so $Q^TQ=I_k$. The projection of $b\in\mathbb{R}^m$ onto $S=\operatorname{Col}(Q)$ is

```math
p=QQ^Tb.
```

The coefficient vector is $Q^Tb$, and the residual $r=b-p$ is orthogonal to every column of $Q$ because

```math
Q^Tr
=Q^T(b-QQ^Tb)
=Q^Tb-Q^Tb
=0.
```

## 2. Projection matrix

The matrix

```math
P=QQ^T\in\mathbb{R}^{m\times m}
```

projects every vector in $\mathbb{R}^m$ onto $S$. It satisfies

```math
P^T=P,
\qquad
P^2=P.
```

The identity $P^2=P$ means that projecting an already projected vector changes nothing.

## Worked example

Let

```math
q_1=\begin{bmatrix}1\\0\\0\end{bmatrix},
\qquad
q_2=\frac{1}{\sqrt{2}}\begin{bmatrix}0\\1\\1\end{bmatrix},
\qquad
b=\begin{bmatrix}2\\3\\1\end{bmatrix}.
```

The coordinates are $q_1^Tb=2$ and $q_2^Tb=2\sqrt{2}$, so

```math
p=2q_1+2\sqrt{2}q_2
=\begin{bmatrix}2\\2\\2\end{bmatrix}.
```

The residual is $r=[0,1,-1]^T$, and $q_1^Tr=q_2^Tr=0$.

## Homework

### Core

1. Using the $q_1,q_2$ from the worked example, project $b=[1,2,4]^T$ onto $S=\operatorname{span}(q_1,q_2)$. Verify that the residual is orthogonal to both basis vectors.
2. Construct the projection matrix $P=QQ^T$ for the worked-example subspace. Compute $Pb$ and check that it matches the worked projection.
3. Prove algebraically that $P^2=P$ using $Q^TQ=I$.
4. If $b\in\operatorname{Col}(Q)$, prove that $QQ^Tb=b$.
5. Error diagnosis: a student applies $QQ^Tb$ when the columns of $Q$ are independent but not orthonormal. Explain which step in the residual calculation fails.

### Optional proof diagnostic

Prove that $P^T=P$ and explain why both $P^T=P$ and $P^2=P$ are dimensionally valid equations.

---

## My solutions

## My reasoning

Check $Q^TQ=I$ before using $QQ^Tb$.

## Confusions and questions

---

## Review

## Corrections I should retain
