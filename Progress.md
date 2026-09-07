# Progress

This file records durable evidence of learning. Update it during each weekly review; do not mark a topic mastered merely because it has been read once.

## Status labels

- **Not studied** — no serious attempt yet.
- **Developing** — basic exercises are possible, but errors or uncertainty remain.
- **Reliable** — can explain the idea and solve unfamiliar basic problems without help.
- **Needs review** — was reliable but later retrieval exposed weakness.

## Topic record

| Topic | Status | Evidence | Last checked |
|---|---|---|---|
| Vector notation and dimensions | Reliable | Week 1 closed-book retrieval correctly identified input/output spaces and the dimensions of $A$, $x$, and $Ax$ after one omitted output dimension was corrected | 2026-08-21 |
| Linear combinations and span | Reliable | Week 1 retrieval correctly stated span through coefficients, connected it to column combinations, described a dependent span geometrically, and justified a vector outside it | 2026-08-21 |
| Matrix-vector multiplication | Reliable | Week 1 retrieval correctly used dimensions, column combinations, component expansion, and the equivalence between $Ax=b$ and column-span membership | 2026-08-21 |
| Inner products and norms | Reliable | Day 4 was correct on the first submitted attempt, including exact norm calculations, normalization, the general squared-distance expansion, the orthogonal Pythagorean identity, and an unfamiliar one-parameter orthogonality problem | 2026-08-21 |
| Linear equations | Reliable | Week 1 retrieval independently solved and verified a new system and correctly used inconsistency to prove non-membership in a column span | 2026-08-21 |
| Linear independence and basis | Reliable | Week 2 Day 1 correctly tested independence, separated independence from span, computed unique coordinates, supplied a nontrivial dependence relation, stated the exact column-space solvability condition, and completed the optional uniqueness proof | 2026-08-22 |
| Subspaces | Reliable | Week 2 Day 2 correctly checked the subspace conditions, represented a one-dimensional subspace as a span, and used valid counterexamples to disprove closure | 2026-08-24 |
| Column space and rank | Reliable | Week 2 synthesis correctly found a column-space basis from original pivot columns and, after correction, distinguished ambient space from rank and connected full row rank with reachability | 2026-09-06 |
| Null space and solution structure | Reliable | Week 2 synthesis correctly found the null-space basis, verified rank-nullity, expressed all solutions as a particular solution plus the null space, classified uniqueness, and proved that exactly two solutions are impossible | 2026-09-06 |
| Projection onto a line | Reliable | Week 3 Day 1 correctly computed projections and residuals, verified orthogonality, retained the ambient space, derived the coefficient, and proved invariance under rescaling the spanning vector | 2026-09-06 |
| Gram–Schmidt and orthonormal bases | Reliable | Week 3 Day 2 correctly normalized vectors, constructed and checked an orthonormal pair, diagnosed a zero residual for dependent inputs, proved residual orthogonality, and completed both span-containment directions after a hint | 2026-09-07 |

## Recurring issues

Record patterns such as dimension errors, unjustified algebraic steps, sign mistakes, or confusion between an object and its numerical representation.

- Type and dimension notation required repeated correction on Day 1; retest the scalar/vector distinction in later work before marking the topic Reliable.
- Day 2 reasoning assigned span membership to coefficient sets instead of resulting vectors; continue checking which mathematical space each object belongs to.
- Formal proof remains tiring and fragile when zero-coordinate cases or uniqueness arguments appear; revisit through short, scaffolded proof exercises rather than repeating the full Day 2 proof immediately.
- Day 3 again blurred a vector with one of its scalar components: $Ax$ belongs to the column span, while $(Ax)_i$ is a scalar. Continue explicit type checks.
- Day 5 initially treated compatible dimensions as evidence of solvability and described pivots by rows rather than variable columns; continue separating definedness, existence, and uniqueness.
- Week 2 synthesis initially inferred the ambient space from the number of basis vectors and omitted the reachability consequence of full row rank. Ambient space and full-rank definitions were added; retest both distinctions in later matrix problems.
- Week 3 Day 1 initially labelled the residual as the projection in an annotation, although the submitted problems consistently distinguished them. Continue naming $p=cu$ and $r=b-p$ explicitly.

- Week 3 Day 2 initially treated one span containment as equality; the correction explicitly established the reverse containment. Continue checking both directions in set-equality proofs. The optional orthonormal-independence proof remains uncompleted.

## Weekly record

| Week | Outcome | Main weakness | Next action |
|---|---|---|---|
| 1 | Complete | All five foundational topics were retained in cumulative problems; minor notation and arithmetic slips were corrected | Begin Phase 2 with linear independence and basis; keep proof tasks short and scaffolded |
| 2 | Complete | Structural calculations and proofs were sound; ambient space and the different consequences of full row versus full column rank required clarification | Begin Week 3 with projection onto a line; retest object spaces when projection matrices appear |
