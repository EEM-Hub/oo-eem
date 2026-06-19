---
source: sources/wiki-GRASP_object-oriented_design.md
source_url: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
---

## GRASP: General Responsibility Assignment Software Patterns

GRASP is a set of nine fundamental principles for object-oriented design and responsibility assignment, first published by Craig Larman in his 1997 book *Applying UML and Patterns*. These patterns provide a mental toolset for deciding which classes should hold which responsibilities, documenting and standardizing proven programming principles rather than inventing new ones. Larman emphasizes that "the critical design tool for software development is a mind well educated in design principles."

## Key Concepts

- **Information Expert** — Assign responsibility to the class that has the information needed to fulfill it. Look at what data is required, find where it lives, and place the method there.
- **Creator** — Assign class B the responsibility to create object A when B contains/aggregates A, records A, closely uses A, or has A's initializing data.
- **Controller** — Assign system event handling to a non-UI class representing the overall system or a use case. Controllers delegate work; they should not do much themselves. Two variants: *use case controller* (one per use case or group) and *facade controller* (represents the whole system).
- **Indirection** — Introduce an intermediate object to mediate between two components, reducing direct coupling. MVC's controller mediating between model and view is a classic example.
- **Low Coupling** — Minimize dependencies between classes to reduce change impact and increase reuse potential. This is an *evaluative* pattern (a quality to aim for, not a specific structure).
- **High Cohesion** — Keep each class focused on a single, well-defined set of related responsibilities. Generally supports low coupling. Low cohesion leads to classes that are hard to comprehend, reuse, and maintain.
- **Polymorphism** — When behavior varies by type, assign that behavior to the varying types via polymorphic operations rather than using explicit conditional branching.
- **Protected Variations** — Identify points of predicted instability and wrap them with a stable interface, using polymorphism for varying implementations. Related to the Open/Closed Principle.
- **Pure Fabrication** — A class that does not represent a domain concept, invented solely to achieve low coupling, high cohesion, and reuse. Called a "service" in Domain-Driven Design.

## Commands and Syntax

No specific commands or code syntax — GRASP is a set of design heuristics applied during modeling and design. Applied during responsibility assignment when creating class diagrams or writing code:

- **Decision procedure for Information Expert**: (1) State the responsibility, (2) identify what information is needed, (3) find where that information is stored, (4) assign the responsibility there.
- **Decision procedure for Creator**: Check which class satisfies the most Creator criteria (contains, records, closely uses, has init data) and assign creation responsibility to it.
- **Controller selection**: Choose between a use case controller (e.g., `UserController` for Create User and Delete User) or a facade controller (represents the root object or entire system).

## Relationships

- **Low Coupling and High Cohesion** are cross-cutting evaluative patterns that support and are supported by nearly all other GRASP patterns. Information Expert, Creator, Indirection, Pure Fabrication all aim to maintain these qualities.
- **Controller** relates to the Command pattern, Facade pattern, Layers pattern, and Pure Fabrication.
- **Creator** relates to the Factory pattern (Factory is an alternative when Creator criteria don't apply or more complex creation logic is needed).
- **Protected Variations** is closely related to the **Open/Closed Principle** from SOLID.
- **Pure Fabrication** connects to the **Service** concept in Domain-Driven Design and compensates when Information Expert would produce poor cohesion or coupling.
- **Indirection** is the generalized principle behind patterns like MVC, Adapter, Mediator, and Facade.
- GRASP as a whole complements **SOLID** principles — GRASP focuses on responsibility assignment while SOLID focuses on class structure and dependency management.

## Exam-Relevant Points

- There are exactly **nine** GRASP patterns: Information Expert, Creator, Controller, Indirection, Low Coupling, High Cohesion, Polymorphism, Protected Variations, Pure Fabrication.
- GRASP was created by **Craig Larman**, published in *Applying UML and Patterns* (1997, with 2nd ed. 2001 and 3rd ed. 2004).
- **Information Expert** is the most fundamental: assign responsibility where the data lives.
- **Creator** has four specific criteria (contains/aggregates, records, closely uses, has initializing data) — know all four.
- **Controller** is the first object *beyond the UI layer* — it does not do the work itself but delegates.
- **Low Coupling** and **High Cohesion** are *evaluative* patterns (qualities to assess), not constructive patterns (specific structures to build).
- **Pure Fabrication** explicitly does *not* represent a domain concept — it exists purely for design quality. This distinguishes it from domain model classes.
- **Protected Variations** wraps instability points with interfaces — the mechanism is interface + polymorphism.
- **Polymorphism** in GRASP means assigning type-varying behavior to the types themselves, replacing conditional logic with polymorphic dispatch.
- GRASP patterns are not mutually exclusive — multiple patterns often apply simultaneously to a single design decision.
