# Day 05 — Linear Equations and Synthesis

## Learning objectives

You should be able to express a linear system as $Ax=b$, connect solvability to
column span, solve small systems by elimination, and identify non-unique or
inconsistent cases.

## 1. From scalar equations to $Ax=b$

The system

$$
\begin{aligned}
2x_1+x_2&=5,\\
x_1-x_2&=1
\end{aligned}
$$

can be written as

$$
\underbrace{\begin{bmatrix}2&1\\1&-1\end{bmatrix}}_A
\underbrace{\begin{bmatrix}x_1\\x_2\end{bmatrix}}_x
=
\underbrace{\begin{bmatrix}5\\1\end{bmatrix}}_b.
$$

Because $Ax$ is a combination of the columns of $A$, $Ax=b$ has a solution
exactly when $b$ belongs to the column span of $A$.

## 2. Three possible outcomes

A linear system can have:

- **one solution**;
- **no solution**, because its equations are inconsistent;
- **infinitely many solutions**, because at least one variable remains free.

For linear systems, two distinct solutions imply infinitely many solutions. This
fact will be justified later when null spaces are studied.

## 3. Elimination

Elimination replaces equations with equivalent equations that are easier to solve.
For the example above, subtract half of the first equation from the second, or use
ordinary substitution. Either gives $x_2=1$ and $x_1=2$. Always check the result
in the original equations.

## Worked contrasting cases

The system

$$
x_1+x_2=2,\qquad 2x_1+2x_2=4
$$

has infinitely many solutions: $x_1=t,\ x_2=2-t$.

Changing the second right-hand side to 5 makes the equations inconsistent, because
doubling the first left-hand side would require the right-hand side to be 4.

## Homework

### Core

1. Translate the following system into $Ax=b$, stating the dimensions of all
   three objects:
   $$
   3x_1-2x_2=7,\qquad x_1+4x_2=-1.
   $$
2. Solve the system in Problem 1 and verify the answer in the original equations.
3. Classify each system as having one, none, or infinitely many solutions. Justify.
   1. $x_1+x_2=3,\quad x_1-x_2=1$
   2. $x_1+x_2=3,\quad 2x_1+2x_2=8$
   3. $x_1+x_2=3,\quad 2x_1+2x_2=6$
4. Let
   $$
   A=\begin{bmatrix}1&2\\2&4\end{bmatrix}.
   $$
   Describe which $b=[b_1,b_2]^T$ make $Ax=b$ solvable. Express the condition
   as an equation relating $b_1$ and $b_2$.
5. Explain the relationship among these statements for a given $A$ and $b$:
   - $Ax=b$ has a solution;
   - $b$ is a linear combination of the columns of $A$;
   - $b$ belongs to the span of the columns of $A$.

### Diagnostic synthesis

6. Let
   $$
   A=\begin{bmatrix}1&0\\1&1\\0&1\end{bmatrix},\qquad
   b=\begin{bmatrix}2\\5\\3\end{bmatrix}.
   $$
   Check dimensions, determine whether $Ax=b$ is solvable, and explain the
   result using both scalar equations and column span.

---

## My work

Show the translation, elimination, classification, and verification steps.

## My reasoning

For Problems 3–6, explain the structural reason for the answer.

## Confusions and questions

Identify which connection is weakest: equations ↔ matrix form ↔ column span.
