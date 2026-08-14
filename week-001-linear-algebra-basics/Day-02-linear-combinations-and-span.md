# Day 02 — Linear Combinations and Span

## Learning objectives

You should be able to recognize a linear combination, test whether a target vector
can be formed from given vectors, and explain span as a set of reachable vectors.

## 1. Linear combinations

Given vectors $v_1,\ldots,v_k\in\mathbb{R}^n$, a **linear combination** is

\[
c_1v_1+\cdots+c_kv_k,
\]

where $c_1,\ldots,c_k\in\mathbb{R}$. The coefficients may be positive, negative,
or zero. All $v_i$ must lie in the same vector space so the sum is defined.

Example:

\[
2\begin{bmatrix}1\\0\end{bmatrix}
-3\begin{bmatrix}0\\1\end{bmatrix}
=\begin{bmatrix}2\\-3\end{bmatrix}.
\]

## 2. Span

The **span** of $v_1,\ldots,v_k$ is the set of every linear combination of them:

\[
\operatorname{span}$v_1,\ldots,v_k$
=\{c_1v_1+\cdots+c_kv_k\mid c_i\in\mathbb{R}\}.
\]

Membership is an existence question. To show that $b$ belongs to the span, find
coefficients satisfying

\[
c_1v_1+\cdots+c_kv_k=b.
\]

To show that it does not, derive an inconsistency from the corresponding scalar
equations.

## 3. Dependence as redundancy

Vectors are **linearly dependent** if some nonzero coefficients satisfy

\[
c_1v_1+\cdots+c_kv_k=0.
\]

This means at least one vector is redundant in generating the span. For example,
$[1,1]^T$ and $[2,2]^T$ are dependent because

\[
2\begin{bmatrix}1\\1\end{bmatrix}
-\begin{bmatrix}2\\2\end{bmatrix}=0.
\]

## Worked example

Does $b=[7,1]^T$ lie in the span of $v_1=[1,1]^T$ and
$v_2=[2,-1]^T$? We solve

\[
c_1+2c_2=7,\qquad c_1-c_2=1.
\]

The second equation gives $c_1=1+c_2$. Substitution gives $3c_2=6$, so
$c_2=2$ and $c_1=3$. Therefore $b=3v_1+2v_2$, and membership is proved.

## Homework

### Core

1. Write $[4,-5]^T$ as a linear combination of $e_1,e_2\in\mathbb{R}^2$.
2. Determine whether $b=[3,5]^T$ lies in
   $\operatorname{span}([1,1]^T,[1,-1]^T)$. If so, find the coefficients.
3. Determine whether $b=[1,2]^T$ lies in
   $\operatorname{span}([1,2]^T,[2,4]^T)$. Is the representation unique? Explain.
4. Determine whether $[1,0]^T$ lies in
   $\operatorname{span}([1,1]^T,[2,2]^T)$. Prove your conclusion using equations.
5. Are the vectors $[1,0]^T$, $[0,1]^T$, and $[1,1]^T$ linearly dependent?
   If yes, exhibit nonzero coefficients.

### Diagnostic challenge

6. If $u,v\in\mathbb{R}^2$ are not scalar multiples of each other, explain why
   every $b\in\mathbb{R}^2$ should have a unique representation $b=c_1u+c_2v$.
   A careful intuitive argument is sufficient; a formal proof is optional.

---

## My work

Write your equations and solutions here.

## My reasoning

Explain what each computed coefficient says about span or dependence.

## Confusions and questions

Record any point where solving equations and interpreting span became disconnected.
