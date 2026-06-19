---
source: sources/wiki-Separation_of_concerns.md
source_url: https://en.wikipedia.org/wiki/Separation_of_concerns
---

## Separation of Concerns (SoC)

Separation of concerns is a foundational design principle in computer science holding that a complex problem should be divided into distinct concerns — aspects or issues — that can be analyzed, addressed, or managed individually. Coined by Edsger W. Dijkstra in 1974, the principle reduces cognitive load by allowing a developer to focus on one aspect at a time while temporarily setting others aside. It is broader than modularity alone and applies across software design, project timelines, specification documents, and system architecture.

## Key Concepts

- **Definition**: A concern is any aspect or issue of a system that can be considered independently — correctness, efficiency, security, presentation, data flow, etc.
- **Four dimensions of separation**: temporal (sequencing activities), by quality (correctness vs. efficiency), by view (data flow vs. control flow), and by size (modularity).
- **Modularity is one form of SoC**, not a synonym — SoC also applies to project phases, specification categories, and architectural views.
- **Dijkstra's insight**: "Focusing one's attention upon some aspect does not mean ignoring the other aspects; it is just doing justice to the fact that from this aspect's point of view, the other is irrelevant."
- **Not always perfectly achievable** — Dijkstra acknowledged this — but it is "the only available technique for effective ordering of one's thoughts."
- **Cross-cutting concerns** (security, logging) cut across primary concerns and are difficult to isolate with standard modular decomposition; aspect-oriented programming addresses this.
- **Carlo Ghezzi** promotes SoC as the primary way to tackle inherent complexity in software production.
- **Philippe Kruchten's 4+1 View Model** is a view-based application of SoC to software architecture (logical, process, development, physical views + scenarios).

## Commands and Syntax

No specific commands. SoC is a design principle, not a tool. However, it manifests in concrete architectural patterns:

- **Layered architecture** — each layer addresses one concern (e.g., OSI/Internet protocol stack: application, transport, internet, link)
- **HTML/CSS/JS separation** — content (HTML), presentation (CSS), behavior (JavaScript) as distinct languages
- **Aspect-oriented annotations** — e.g., `@LoggingAspect`, `@Transactional` in frameworks like Spring, which separate cross-cutting concerns from business logic
- **Module systems** — packages, namespaces, and module boundaries that enforce concern isolation at the code level

## Relationships

- **Single Responsibility Principle (SRP)**: SRP is SoC applied at the class/module level — each unit has one reason to change.
- **Modularity / Modular Programming**: The most common embodiment of SoC in code structure; modules encapsulate individual concerns.
- **Coupling and Cohesion**: Good SoC leads to low coupling between modules and high cohesion within them.
- **Abstraction Principle**: SoC enables abstraction by allowing details of one concern to be hidden from others.
- **Aspect-Oriented Programming (AOP)**: A programming paradigm specifically designed to handle cross-cutting concerns that resist standard modular separation.
- **Subject-Oriented Programming**: Allows multiple concern-specific class structures to coexist and compose via correspondence rules.
- **Layered / Tiered Architecture**: Direct architectural application of SoC (presentation, business logic, data access).
- **David Marr's Levels of Analysis**: SoC applied in cognitive science/AI — computational, algorithmic, and implementation levels as separate concerns.

## Exam-Relevant Points

- **Origin**: Coined by Dijkstra in 1974 in "On the Role of Scientific Thought." Know the author and year.
- **Four dimensions**: temporal, quality, view, size — be able to give an example of each.
- **SoC is broader than modularity**: Modularity is separation by size; SoC also covers temporal separation (project phases), quality separation (correctness vs. efficiency), and view separation (4+1 architecture model).
- **Internet protocol stack** is a canonical example of SoC — each layer (application, transport, internet, link) addresses a distinct concern independently.
- **HTML/CSS/JS** is the canonical web example: content, presentation, behavior separated into distinct languages (historically HTML handled both content and style before CSS).
- **Cross-cutting concerns** (security, logging) are the main challenge to SoC — they span multiple modules and motivate aspect-oriented programming.
- **Key benefit**: Reduces complexity by allowing independent analysis, design, and modification of each concern.
- **Ghezzi's position**: SoC is the primary technique for managing inherent software complexity.
- **Kruchten's 4+1 model**: Five architectural views (logical, process, development, physical + scenarios) as a view-based separation of concerns.
