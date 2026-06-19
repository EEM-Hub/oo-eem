---
source: sources/wiki-Cohesion_computer_science.md
source_url: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
---

## Cohesion in Object-Oriented Design

Cohesion measures the degree to which elements within a module belong together. It quantifies the strength of relationship between a class's methods and data and some unifying purpose served by that class. Cohesion is an ordinal measure described as "high" or "low," where high cohesion correlates with robustness, reliability, reusability, and understandability. The concept was invented by Larry Constantine in the late 1960s as part of Structured Design and formalized in Stevens, Myers & Constantine (1974) and Yourdon & Constantine (1979).

## Key Concepts

- **High cohesion** means a class's methods are similar in purpose and operate on related data; it reduces complexity, improves maintainability, and increases reusability.
- **Cohesion is ordinal, not interval** — the ranked types do not represent steady progression; empirical studies show coincidental and logical cohesion are inferior, communicational and sequential are very good, and functional is superior.
- **Cohesion must be balanced** against unit complexity and coupling — a single-function module has perfect cohesion but may be too narrow and tightly coupled to other modules.
- Cohesion increases when: methods share common functionality, methods perform a small number of related activities, and related methods are grouped together in source files.

## Types of Cohesion (Worst to Best)

1. **Coincidental** — parts grouped arbitrarily with no meaningful relationship (e.g., a "Utilities" class).
2. **Logical** — parts grouped because they are categorized to do the same thing despite different natures (e.g., all input handling routines together).
3. **Temporal** — parts grouped because they execute at the same time (e.g., cleanup code after an exception).
4. **Procedural** — parts grouped because they follow a fixed sequence of execution (e.g., check permissions then open file).
5. **Communicational/Informational** — parts grouped because they operate on the same data (e.g., operations on the same record).
6. **Sequential** — parts grouped because output of one is input to the next, like an assembly line.
7. **Functional** (best practical) — parts grouped because they all contribute to a single well-defined task (e.g., lexical analysis of XML).
8. **Perfect/Atomic** — module cannot be decomposed further; a single irreducible computation.

## Relationships

- **Coupling** is the direct complement: high cohesion correlates with loose coupling, and vice versa. Together they form the twin axes of modular design quality.
- **Single Responsibility Principle (SRP)** is the OO formalization of functional cohesion — a class should have one reason to change.
- **Static code analysis** tools can compute cohesion metrics (e.g., LCOM — Lack of Cohesion of Methods).
- **Module decomposition** decisions are driven by cohesion: split when cohesion is low, merge when splitting creates excessive coupling.

## Exam-Relevant Points

- Know the seven types of cohesion in order from worst (coincidental) to best (functional/perfect) — this ranking is a classic exam question.
- Coincidental and logical cohesion are empirically inferior; communicational and sequential are very good; functional is superior (Constantine, Yourdon, McConnell).
- High cohesion does **not** mean single-method classes — that creates tight coupling. Cohesion must be balanced with coupling and complexity.
- The "Utilities" class is the canonical example of coincidental cohesion (the worst kind).
- Cohesion and coupling were introduced together by Larry Constantine as part of Structured Design (late 1960s), published formally in 1974.
- Cohesion is a **qualitative, ordinal** measure — not a numeric ratio. It is assessed by examining source code against a rubric.
