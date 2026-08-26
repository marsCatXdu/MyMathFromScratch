# My Math From Scratch

A customized, mastery-gated mathematics course leading toward Stephen Boyd and Lieven Vandenberghe's *Convex Optimization*.

## Working method

1. Study one `Day-xx` file per session. A “day” is a study session, not a deadline.
2. Attempt every exercise before asking for hints. Record incomplete and failed reasoning.
3. Write directly under **My work**, **My reasoning**, and **Confusions**.
4. Commit with a descriptive prefix:
   - `lesson:` curriculum material
   - `work:` attempted exercises and questions
   - `review:` feedback on submitted work
   - `correction:` revisions after feedback
5. At the end of each week, complete `Week-Review.md`. The next week is designed from the evidence there.

## Learning design

This is an interactive, customized textbook rather than a compressed version of a traditional textbook. The mainline stays minimal: each lesson contains the concepts and methods required for its objectives and homework, while adjacent material is deferred until it becomes necessary or the learner asks about it.

Related information that may be useful but is not required immediately should appear as a clearly labelled quote block:

> **Optional context — not required now.** This note may help connect the current idea to later material, but it is not part of the present progression requirement.

Optional notes do not create extra homework or block progression. If an exercise requires a method, however, that method must be taught in the mainline before the exercise. Questions, confusions, and research interests determine which deferred topics are expanded and preserved in later revisions.

## Git collaboration

The learner and reviewing agent both work directly on `main`. The learner pushes completed work, then asks for review. The agent fetches the latest `main`, reviews only the submitted scope, updates the lesson review and `Progress.md`, validates the exact diff, and commits the result back to `main`.

Do not create branches or pull requests for the normal learning cycle. Use them only if the learner explicitly requests them for a particular task.

## Mastery rule

Move forward when the core exercises can be solved with correct notation and justified steps. A calendar week does not force progression. Unfinished sessions simply roll forward.

## Feedback standard

Reviews check mathematical correctness, justification, notation, dimensional consistency, recurring misconceptions, and whether the work demonstrates understanding rather than pattern matching.

## Course direction

The initial phase builds the linear algebra, calculus, and proof skills needed for convex optimization. Later phases will cover convex sets, convex functions, optimization problems, duality, and algorithms. Only the next week is prepared in detail so the course can adapt to actual progress.

## Mainline map and progress

These are coarse phases rather than equally sized calendar units. Only the current phase is designed in detail; later phases remain adjustable.

**Course position:** `██░░░░░░░░` — Phase 2 of 10 in progress

**Current unit:** `████░` — Week 2: 4 of 5 sessions complete; Day 5 is next

| Phase | Mainline | Status |
|---:|---|---|
| 1 | Linear algebra foundations: vectors, matrices, norms, and linear systems | **Complete** |
| 2 | Linear algebra structure: independence, basis, subspaces, rank, and null spaces | **In progress** |
| 3 | Orthogonality, projections, and least squares | Planned |
| 4 | Eigenvalues, quadratic forms, and positive semidefinite matrices | Planned |
| 5 | Functions, graphs, composition, and affine mappings | Planned |
| 6 | Derivatives, gradients, Jacobians, Hessians, and local approximation | Planned |
| 7 | Convex sets and convex functions | Planned |
| 8 | Convex optimization problems and mathematical modeling | Planned |
| 9 | Lagrangians, duality, and KKT conditions | Planned |
| 10 | Algorithms, selected Boyd problems, and research-relevant applications | Planned |

Proof and inequality skills are developed gradually along this mainline rather than isolated into one large preliminary block.

## Current material

- [Week 1 — Linear algebra foundations](week-001-linear-algebra-basics/README.md)
- [Week 2 — Linear algebra structure](week-002-linear-algebra-structure/README.md)
- [Week 3 preview — Projections and least squares](week-003-projections-and-least-squares/README.md) *(locked until Week 2 is complete)*
