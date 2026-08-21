# MyMathFromScratch Agent Instructions

## 1. Project purpose

`MyMathFromScratch` is a long-term, customized mathematics course for a PhD student who wants to study Stephen Boyd and Lieven Vandenberghe's *Convex Optimization* but currently has weak mathematical foundations and difficulty starting from the textbook directly.

Repository: <https://github.com/marsCatXdu/MyMathFromScratch>

The project is expected to run slowly, potentially for a year. Calendar speed is secondary. The governing principle is **mastery-gated progression**: later material must depend on demonstrated understanding in submitted work, not merely on elapsed weeks or completed reading.

## 2. Learner requirements

The learner wants:

- A customized textbook written in accessible but mathematically correct language.
- Material divided into weekly folders and daily study sessions.
- Explanations, worked examples, and homework in each session.
- Space in the same files to record solutions, reasoning, failed attempts, and questions.
- Detailed review of mathematical correctness, notation, dimensional consistency, missing justification, and recurring misconceptions.
- Future lessons and homework adjusted using evidence from completed work.
- A durable, traceable learning history in Git.

The learner prefers concise, high-information writing. Avoid excessive motivational language, analogies, rhetorical padding, and long lists of obvious points. Do not hide mathematical weaknesses behind praise. Feedback should be calm, precise, critical, and constructive.

## 3. Pedagogical constraints

### Mastery before schedule

A `Day-xx` file represents one study session, not necessarily one calendar day. A weekly folder may take longer than seven days. Unfinished work rolls forward without forcing progression.

Do not generate many future weeks in advance. Prepare only the next appropriate unit after reviewing the latest evidence. A fixed long-range syllabus can exist at high level, but detailed lessons must remain adaptive.

### Diagnose reasoning, not answer accuracy alone

The learner should preserve intermediate reasoning and failed attempts. Reviews must distinguish among:

- conceptual misunderstanding;
- notation or dimension errors;
- algebraic mistakes;
- unjustified steps;
- correct execution without reliable understanding;
- genuine mastery transferable to unfamiliar problems.

Do not expose complete solutions before a serious attempt unless the learner explicitly asks. Prefer a graded intervention: identify the first invalid step, give a small hint, or ask a targeted question before supplying a full solution.

### Mathematical rigor

Keep notation internally consistent and render mathematics using Markdown-compatible LaTeX. Define every new symbol. Check dimensions explicitly when introducing vectors, matrices, gradients, Hessians, or quadratic forms. Worked examples should show why each step is valid, but should not become mechanically verbose.

Do not hard-wrap Markdown prose. Keep each paragraph and each list item on one physical source line; use line breaks only for structural Markdown, tables, and fenced math or code.

Exercises should include routine computation, interpretation, error diagnosis, and at least one transfer problem. Difficulty should diagnose the current boundary of understanding rather than merely increase arithmetic workload.

### Retention

Every fourth instructional week should include cumulative retrieval practice. Topics marked mastered must occasionally be retested; reading or solving one familiar exercise is insufficient evidence of durable mastery.

## 4. Repository structure

The intended structure is:

```text
MyMathFromScratch/
├── README.md
├── Progress.md
├── week-001-linear-algebra-basics/
│   ├── README.md
│   ├── Day-01-vectors-and-dimensions.md
│   ├── Day-02-linear-combinations-and-span.md
│   ├── Day-03-matrices-and-matrix-vector-products.md
│   ├── Day-04-inner-products-and-norms.md
│   ├── Day-05-linear-equations-and-synthesis.md
│   └── Week-Review.md
└── week-002-.../
```

Each daily lesson should normally contain:

```markdown
# Day XX — Topic

## Learning objectives
## Textbook
## Worked examples
## Homework

---

## My solutions
## My reasoning
## Confusions and questions

---

## Review
## Corrections I should retain
```

Do not overwrite the learner's original attempts. Add review comments in the designated review section or make clearly attributable edits. Preserve failed reasoning because it is diagnostic evidence.

## 5. Current state

Week 1 has already been created and pushed to `main`. It deliberately limits scope to foundational linear algebra:

1. vectors, notation, and dimensions;
2. linear combinations and span;
3. matrices and matrix-vector products;
4. inner products and norms;
5. linear equations and synthesis.

Days 1–4 have been completed and reviewed. Days 1–3 remain **Developing** pending later retrieval; Day 4 is **Reliable** based on a fully correct first attempt including its diagnostic challenge. Day 5 and the Week 1 review remain. Do not design Week 2 in detail until the Week 1 review provides evidence.

`main` contains the Week 1 material and its GitHub-compatible math-formatting corrections. Always fetch the current remote state instead of assuming the local checkout is current.

## 6. Required interaction cycle

For each learning cycle:

1. Fetch the latest learner commits and inspect the changed lesson files.
2. Read the complete attempted solutions, reasoning, and questions before commenting.
3. Review each substantive claim and calculation.
4. Add feedback that identifies the exact error, its cause, and the minimum correction needed.
5. Update `Progress.md` only when evidence justifies a status change.
6. Decide whether the learner should correct current work, do targeted reinforcement, or progress.
7. After the weekly review is complete, create only the next justified lesson set.

When evidence is ambiguous, assign a short diagnostic exercise instead of assuming mastery or failure.

## 7. Progress criteria

Use the existing status meanings:

- **Not studied**: no serious attempt.
- **Developing**: basic exercises are possible, but errors or uncertainty remain.
- **Reliable**: the learner can explain the concept and solve an unfamiliar basic problem without help.
- **Needs review**: previously reliable knowledge failed later retrieval.

Status changes require evidence in the repository. Record concise evidence and the date in `Progress.md`. Also track recurring patterns, such as dimension errors, sign mistakes, confusion between geometric objects and coordinate representations, or unjustified algebraic transformations.

## 8. Long-term content direction

The eventual objective is to read and solve substantial parts of *Convex Optimization*. The preparatory path will probably require:

- linear algebra;
- functions, graphs, and notation;
- single-variable and multivariable calculus;
- gradients, Jacobians, and Hessians;
- basic proof and inequality skills;
- quadratic forms, eigenvalues, and positive semidefinite matrices;
- then convex sets, convex functions, optimization problems, duality, and algorithms.

This is a provisional dependency map, not a fixed timetable. Change order and depth when learner evidence warrants it. Do not compress eigenvalues, PSD matrices, multivariable calculus, and convexity into a single week.

## 9. Git workflow

Use a simple direct-to-`main` workflow. Do not create a branch or pull request during the normal learner/reviewer cycle. Create one only when the learner explicitly requests it for a particular task.

- Fetch the latest `origin/main` before starting work and ensure the local branch can be updated safely.
- Treat the learner's latest pushed commit as the review base; never rewrite or discard it.
- Commit prefixes:
  - `lesson:` new or revised curriculum;
  - `work:` learner attempts and questions;
  - `review:` feedback on submitted work;
  - `correction:` learner revisions after feedback.
- Keep learner work separate from review commits when practical.
- Before committing and pushing, verify Markdown links, LaTeX delimiters, file naming, and the exact diff.
- Push completed, validated changes directly to `origin/main`.

Never rewrite or discard learner commits merely to make history cleaner.

## 10. Immediate task for Codex

First, fetch the repository and work from the latest `main`. Day 5 is the next lesson to complete; do not generate Week 2 yet.

When new work is pushed, review only the submitted scope, add precise feedback, update `Progress.md`, validate the exact diff, and commit the review directly to `main`. The first major curriculum decision should follow the completed Week 1 review.

## 11. Definition of success

The repository should become an auditable record of increasing mathematical competence. Success is demonstrated when the learner can independently explain concepts, maintain correct notation and dimensions, justify steps, and solve unfamiliar problems that rely on earlier material. File count, nominal week number, and reading completion are weak proxies and should not drive progression.
