# Day 03 — Projection onto a Subspace

## Learning objectives

You should be able to project onto a subspace with an orthonormal basis, construct the projection matrix, and verify its main algebraic properties.

## 1. From one direction to several

Day 1 projected $b$ onto one line. Day 2 constructed perpendicular unit vectors spanning the same subspace as the original vectors. Today we use those orthonormal vectors to project onto an entire subspace.

For two orthonormal vectors $q_1,q_2$, take the component along each direction and add them:

```math
p=(q_1^Tb)q_1+(q_2^Tb)q_2.
```

Each coefficient is a scalar. Because the directions are perpendicular, adding the component along $q_2$ does not change the component along $q_1$. Matrix notation will let us write this sum compactly.

## 2. The matrix operations we need

### Transpose: rows become columns

The transpose $A^T$ swaps the row and column positions of each entry:

```math
A=\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix},
\qquad
A^T=\begin{bmatrix}1&4\\2&5\\3&6\end{bmatrix}.
```

Thus an $m\times k$ matrix becomes a $k\times m$ matrix. Transposing twice returns the original matrix: $(A^T)^T=A$.

### Matrix times matrix: row times column

You already know how to compute a matrix times a vector. For a matrix $B=[b_1\ \cdots\ b_n]$, do that separately for every column:

```math
AB=[Ab_1\ \cdots\ Ab_n].
```

If $A$ is $m\times k$ and $B$ is $k\times n$, the product is $m\times n$. The inner dimensions must match. Entry $(i,j)$ of $AB$ is row $i$ of $A$ dotted with column $j$ of $B$.

For example,

```math
\begin{bmatrix}1&2\\3&4\end{bmatrix}
\begin{bmatrix}5&0\\1&2\end{bmatrix}
=
\begin{bmatrix}
1(5)+2(1)&1(0)+2(2)\\
3(5)+4(1)&3(0)+4(2)
\end{bmatrix}
=
\begin{bmatrix}7&4\\19&8\end{bmatrix}.
```

This is not entry-by-entry multiplication. Also, $AB$ and $BA$ generally differ, and one may be undefined.

### The identity matrix $I$

The **identity matrix** $I_k$ is a $k\times k$ matrix with ones on the diagonal and zeros elsewhere. For example,

```math
I_2=\begin{bmatrix}1&0\\0&1\end{bmatrix},
\qquad
I_2\begin{bmatrix}x\\y\end{bmatrix}
=\begin{bmatrix}x\\y\end{bmatrix}.
```

Multiplying by a compatible identity matrix leaves a vector or matrix unchanged. For $A\in\mathbb R^{m\times k}$, $I_mA=A$ and $AI_k=A$. When its size is clear, we write just $I$.

### Rules used in today's proofs

For compatible dimensions:

```math
(AB)C=A(BC),\qquad
A(B+C)=AB+AC,\qquad
(AB)^T=B^TA^T.
```

The first rule lets you change parentheses, but not factor order. The last rule reverses the order when transposing a product. Also, $P^2$ means $PP$, not squaring each entry.

## 3. Write the projection as $QQ^Tb$

Put an orthonormal basis into the columns of $Q$:

```math
Q=[q_1\ \cdots\ q_k]\in\mathbb R^{m\times k},
\qquad b\in\mathbb R^m.
```

The columns $q_i$ have $m$ entries. The rows of $Q^T$ are $q_i^T$, so

```math
c=Q^Tb=
\begin{bmatrix}q_1^Tb\\ \vdots\\q_k^Tb\end{bmatrix}\in\mathbb R^k,
\qquad
p=Qc=\sum_{i=1}^k(q_i^Tb)q_i=QQ^Tb\in\mathbb R^m.
```

Here $c$ collects the projection coefficients, and $p$ is the resulting vector in $S=\operatorname{Col}(Q)$. Compute $Q^Tb$ first, then multiply by $Q$.

The $(i,j)$ entry of $Q^TQ$ is $q_i^Tq_j$. Orthonormality makes it $1$ when $i=j$ and $0$ otherwise. Therefore

```math
Q^TQ=I_k.
```

Check the order and dimensions: $Q^TQ$ is $k\times k$, while $QQ^T$ is $m\times m$. You cannot interchange them.

### Why is this a projection?

The residual is $r=b-p$. Using the rules above,

```math
Q^Tr
=Q^T(b-Q(Q^Tb))
=Q^Tb-(Q^TQ)(Q^Tb)
=Q^Tb-I_k(Q^Tb)=0.
```

Each entry says $q_i^Tr=0$, so $r$ is orthogonal to every basis vector, and hence every vector in $S$. Since $p\in S$, this gives the closest point: for any $s\in S$, $b-s=r+(p-s)$ is a sum of perpendicular vectors, so $\lVert b-s\rVert_2^2=\lVert r\rVert_2^2+\lVert p-s\rVert_2^2$. This is Day 1's distance argument applied to a subspace.

## 4. Projection matrix

For a fixed orthonormal basis, we can compute the matrix once:

```math
P=QQ^T\in\mathbb R^{m\times m},
\qquad p=Pb.
```

It satisfies $P^T=P$ (called **symmetric**) and $P^2=P$ (called **idempotent**). The latter says projecting twice has the same result as projecting once.

For the homework proof, substitute $P=QQ^T$ into $PP$ and regroup the factors to expose $Q^TQ$. Keep their order unchanged. Do not assume $QQ^T=I_m$: a projection onto a smaller subspace does not leave every input unchanged.

## Worked example

Let

```math
q_1=\begin{bmatrix}1\\0\\0\end{bmatrix},
\qquad
q_2=\frac{1}{\sqrt2}\begin{bmatrix}0\\1\\1\end{bmatrix},
\qquad
b=\begin{bmatrix}2\\3\\1\end{bmatrix}.
```

**1. Assemble the basis and its transpose.**

```math
Q=\begin{bmatrix}1&0\\0&1/\sqrt2\\0&1/\sqrt2\end{bmatrix},
\qquad
Q^T=\begin{bmatrix}1&0&0\\0&1/\sqrt2&1/\sqrt2\end{bmatrix}.
```

**2. Compute the two coefficients.**

```math
c=Q^Tb
=\begin{bmatrix}2\\(3+1)/\sqrt2\end{bmatrix}
=\begin{bmatrix}2\\2\sqrt2\end{bmatrix}.
```

**3. Combine the basis vectors.**

```math
p=Qc=2q_1+2\sqrt2q_2
=\begin{bmatrix}2\\0\\0\end{bmatrix}
+\begin{bmatrix}0\\2\\2\end{bmatrix}
=\begin{bmatrix}2\\2\\2\end{bmatrix}.
```

**4. Check the residual.** Here $r=b-p=[0,1,-1]^T$. Thus $q_1^Tr=0$ and $q_2^Tr=(1-1)/\sqrt2=0$. The coefficient vector has two entries, while $b,p,r$ all belong to the ambient space $\mathbb R^3$.

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
