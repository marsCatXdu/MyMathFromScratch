# Day 05 — Least-Squares Synthesis

## Learning objectives

You should be able to translate a small fitting problem into matrix form, solve it by least squares, and connect the result to projection, rank, and residual orthogonality.

## 1. Fitting a line

Suppose data points $(t_i,y_i)$ are approximated by

```math
y_i\approx\alpha+\beta t_i.
```

Put the unknown parameters into $x=[\alpha,\beta]^T$. With one row $[1,t_i]$ for each observation, the model becomes

```math
Ax\approx b.
```

The least-squares solution chooses the line whose vector of predicted values $A\hat{x}$ is closest to the observed vector $b$.

## Worked example

For the points $(-1,1)$, $(0,1)$, and $(1,3)$,

```math
A=\begin{bmatrix}1&-1\\1&0\\1&1\end{bmatrix},
\qquad
b=\begin{bmatrix}1\\1\\3\end{bmatrix}.
```

The normal equations are

```math
\begin{bmatrix}3&0\\0&2\end{bmatrix}
\begin{bmatrix}\alpha\\\beta\end{bmatrix}
=\begin{bmatrix}5\\2\end{bmatrix},
```

so $\hat{\alpha}=5/3$ and $\hat{\beta}=1$. The fitted line is

```math
y=\frac{5}{3}+t.
```

The residual is

```math
r=b-A\hat{x}
=\begin{bmatrix}1/3\\-2/3\\1/3\end{bmatrix},
```

and $A^Tr=0$.

## 2. Structural interpretation

For a full-column-rank matrix $A$:

- $A\hat{x}$ is the unique projection of $b$ onto $\operatorname{Col}(A)$;
- $\hat{x}$ is unique because $\mathcal{N}(A)=\{0\}$;
- the residual belongs to the orthogonal complement of $\operatorname{Col}(A)$;
- if $b\in\operatorname{Col}(A)$, the residual is zero and least squares recovers an exact solution.

> **Optional context — not required now.** If $A=QR$ with orthonormal columns in $Q$, then the normal equations reduce to $R\hat{x}=Q^Tb$. This is the practical connection between Gram–Schmidt and least squares.

## Homework

### Core synthesis

Use the data points $(0,1)$, $(1,2)$, $(2,2)$, and $(3,4)$ for Problems 1–4.

1. Construct $A$ and $b$ for the model $y\approx\alpha+\beta t$. State their dimensions.
2. Compute $A^TA$ and $A^Tb$, then solve for $\hat{\alpha}$ and $\hat{\beta}$.
3. Compute the four fitted values and the residual. Verify both equations in $A^Tr=0$.
4. Explain why the fitted-value vector is unique. Distinguish uniqueness of $A\hat{x}$ from uniqueness of $\hat{x}$.
5. Research interpretation: suppose the columns of $A$ contain measured telemetry features and $b$ contains packet delays. Explain what $A\hat{x}$, $r$, $A^Tr=0$, and a dependent column would mean in this model. Do not claim causality from a least-squares fit.
6. Transfer proof: prove that a least-squares residual is zero exactly when $b\in\operatorname{Col}(A)$.

### Optional proof diagnostic

Show that $\mathcal{N}(A^TA)=\mathcal{N}(A)$ by proving both containment directions.

---

## My solutions

## My reasoning

Separate the parameter vector $\hat{x}$, the fitted vector $A\hat{x}$, and the residual $b-A\hat{x}$ throughout the solution.

## Confusions and questions

---

## Review

## Corrections I should retain
