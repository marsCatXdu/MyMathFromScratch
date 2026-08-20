# Mathematics Cheat Sheet

Use this as a retrieval cue. Try to reconstruct the meaning of each formula before checking the explanation.

## Objects and dimensions

- Scalar: $c\in\mathbb{R}$.
- Vector: $x\in\mathbb{R}^n$ has $n$ scalar components.
- Matrix: $A\in\mathbb{R}^{m\times n}$ has $m$ rows and $n$ columns.
- Matrix–vector map: $A:\mathbb{R}^n\to\mathbb{R}^m$, so $x\in\mathbb{R}^n$ gives $Ax\in\mathbb{R}^m$.

## Vectors

```math
x=x_1e_1+\cdots+x_ne_n.
```

- $e_i\in\mathbb{R}^n$ is the $i$-th standard basis vector.
- Vector addition requires equal dimensions.
- Scalar multiplication changes magnitude and possibly direction but not dimension.

## Linear combinations, span, and dependence

```math
c_1v_1+\cdots+c_kv_k
```

- The coefficients $c_i$ are scalars; the result is a vector.
- $\operatorname{span}(v_1,\ldots,v_k)$ is the set of all resulting vectors obtainable by varying the coefficients.
- Span membership asks whether suitable coefficients exist.
- Linear dependence means some coefficients, not all zero, satisfy $c_1v_1+\cdots+c_kv_k=0$.

## Matrix–vector multiplication

If $A=[a_1\ \cdots\ a_n]$ with columns $a_j\in\mathbb{R}^m$, then

```math
Ax=x_1a_1+\cdots+x_na_n.
```

- Column view: $a_j=Ae_j$ is where the $j$-th input basis vector is sent.
- Row view: $(Ax)_i=\sum_{j=1}^n a_{ij}x_j$ computes output component $i$.
- Every output satisfies $Ax\in\operatorname{span}(a_1,\ldots,a_n)$.
- $Ax$ is a vector; $(Ax)_i$ is one scalar component.

## Linearity

```math
A(cx+dy)=cAx+dAy.
```

- Additivity: $A(x+y)=Ax+Ay$.
- Homogeneity: $A(cx)=cAx$.
- A transformation is linear precisely when it preserves linear combinations.
