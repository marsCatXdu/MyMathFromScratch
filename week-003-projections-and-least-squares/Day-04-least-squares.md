# Day 04 — Least Squares and Normal Equations

## Learning objectives

You should be able to formulate an inconsistent system as a least-squares problem, derive the normal equations, and interpret the residual geometrically.

## 1. The least-squares problem

When $Ax=b$ has no exact solution, least squares chooses $\hat{x}$ to minimize the squared residual:

```math
\underset{x}{\operatorname{minimize}}
\quad \lVert Ax-b\rVert_2^2.
```

The vector $A\hat{x}$ is the projection of $b$ onto $\operatorname{Col}(A)$. Therefore the residual

```math
r=b-A\hat{x}
```

must be orthogonal to every column of $A$:

```math
A^Tr=0.
```

Substituting the residual gives the **normal equations**:

```math
A^TA\hat{x}=A^Tb.
```

If the columns of $A$ are linearly independent, $A^TA$ is invertible and the least-squares solution is unique.

> **Optional context — not required now.** Computing $(A^TA)^{-1}$ explicitly is usually avoided in numerical software. QR factorization is more stable, but the normal equations are the clearest starting point for the geometry and will be sufficient for this week's hand calculations.

## Worked example

Let

```math
A=\begin{bmatrix}1&0\\1&1\\1&2\end{bmatrix},
\qquad
b=\begin{bmatrix}1\\2\\2\end{bmatrix}.
```

Then

```math
A^TA=\begin{bmatrix}3&3\\3&5\end{bmatrix},
\qquad
A^Tb=\begin{bmatrix}5\\6\end{bmatrix}.
```

Solving the normal equations gives

```math
\hat{x}=\begin{bmatrix}7/6\\1/2\end{bmatrix}.
```

The fitted vector and residual are

```math
A\hat{x}=\begin{bmatrix}7/6\\5/3\\13/6\end{bmatrix},
\qquad
r=b-A\hat{x}=\begin{bmatrix}-1/6\\1/3\\-1/6\end{bmatrix}.
```

Direct multiplication confirms $A^Tr=0$.

## Homework

### Core

1. For


   ```math
   A=\begin{bmatrix}1\\1\\1\end{bmatrix},
   \qquad
   b=\begin{bmatrix}1\\2\\6\end{bmatrix},
   ```

   find the least-squares scalar $\hat{x}$ and verify that the residual is orthogonal to the column of $A$.
2. For


   ```math
   A=\begin{bmatrix}1&0\\1&1\\1&2\end{bmatrix},
   \qquad
   b=\begin{bmatrix}0\\1\\4\end{bmatrix},
   ```

   form and solve the normal equations. Compute $A\hat{x}$ and $r=b-A\hat{x}$.
3. Starting from the condition $A^T(b-A\hat{x})=0$, derive the normal equations and check every matrix dimension.
4. Prove that if the columns of $A$ are independent, then $A^TAz=0$ forces $z=0$. Use $z^TA^TAz=\lVert Az\rVert_2^2$.
5. Error diagnosis: a student concludes that least squares makes $A\hat{x}=b$. State what least squares guarantees instead and identify the condition under which equality does hold.

---

## My solutions

## My reasoning

Keep the residual convention $r=b-A\hat{x}$ consistent and verify $A^Tr=0$.

## Confusions and questions

---

## Review

## Corrections I should retain
