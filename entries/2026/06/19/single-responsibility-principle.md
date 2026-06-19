---
source: sources/single-responsibility-principle.md
source_url: https://en.wikipedia.org/wiki/Single-responsibility_principle
---

## Single-Responsibility Principle (SRP)

The Single-Responsibility Principle is one of the five SOLID principles of object-oriented design. Originated by Robert C. Martin, it states that each module or class should be responsible to one, and only one, actor — meaning it should have only one reason to change. The principle is rooted in the older concept of cohesion from structured design.

## Key Concepts

- **Core definition**: "A module should be responsible to one, and only one, actor" — where an actor is a group of stakeholders or users that would require changes to that module.
- **Alternative formulation**: "A class should have only one reason to change" — Martin's original phrasing, later refined due to ambiguity around "reason."
- **Gather/Separate heuristic**: "Gather together the things that change for the same reasons. Separate those things that change for different reasons."
- **Actor-based framing**: Distinct roles (e.g., accountant vs. database administrator) represent separate actors even if performed by the same person. Each module should serve a single role.
- **Responsibility = reason to change**: Martin equates a "responsibility" with a "reason to change," making the unit of decomposition the axis of change, not the unit of functionality.
- **Rooted in cohesion**: SRP builds on the concept of cohesion from structured analysis (DeMarco 1979, Page-Jones 1988) — elements that belong together should be grouped together.

## Commands and Syntax

No commands or configuration syntax — SRP is a design principle, not a tooling concern. Applied through design decisions at the class/module level.

**Design test**: For any class, ask "who are the actors that might request changes to this class?" If the answer includes more than one actor, the class likely violates SRP and should be split.

## Relationships

- **SOLID**: SRP is the "S" in SOLID — the first of five complementary OO design principles.
- **Cohesion**: SRP is a refinement of cohesion from structured design; high cohesion within a module implies adherence to SRP.
- **Separation of Concerns**: SRP can be viewed as the class-level application of the broader separation of concerns principle.
- **Coupling**: Violating SRP increases coupling — changes to one concern risk breaking unrelated concerns in the same module.
- **Information Hiding**: Both principles aim to localize the impact of change; SRP focuses on the axis of change (actor), information hiding on the mechanism of change (implementation detail).
- **GRASP**: The GRASP pattern set includes related responsibility-assignment principles (e.g., Information Expert, Low Coupling, High Cohesion).
- **Chain-of-Responsibility pattern**: A behavioral pattern that can help distribute responsibilities across handlers, complementing SRP at the architectural level.

## Exam-Relevant Points

- SRP says **one actor**, not one function or one method — a class can have multiple methods as long as they all serve the same actor.
- The canonical example: a report module that handles both **compilation** (content) and **printing** (format) violates SRP because content changes and format changes originate from different actors and evolve at different times.
- Martin's refined definition uses **actors/roles**, not "tasks" or "features" — the unit of analysis is who requests the change, not what the code does.
- SRP is derived from the concept of **cohesion** (DeMarco, Page-Jones), not invented from scratch — expect questions linking SRP back to structured design.
- Violating SRP creates **fragility**: changing code for one concern risks breaking unrelated code that shares the same module.
- Key sources: *Agile Software Development, Principles, Patterns, and Practices* (2003) for the original formulation; *Clean Architecture* (2018) for the actor-based refinement.
