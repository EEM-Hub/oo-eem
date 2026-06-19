---
source: sources/wiki-Object-oriented_design.md
source_url: https://en.wikipedia.org/wiki/Object-oriented_design
---

## Object-Oriented Analysis and Design (OOAD)

OOAD is a software development methodology that applies object-oriented thinking to the analysis and design phases of the software development lifecycle. It produces system models through object-oriented modeling (OOM), split into two complementary disciplines: Object-Oriented Analysis (OOA), which captures *what* the system must do, and Object-Oriented Design (OOD), which specifies *how* it will be built. OOAD strongly favors iterative and incremental approaches (as formulated by the Unified Process) over waterfall, acknowledging that analysis, design, and coding inform each other continuously.

## Key Concepts

- **OOAD = OOA + OOD**: Analysis identifies domain objects and requirements; design maps them to implementation classes and interfaces under real-world constraints.
- **Open-Closed Principle**: Modules should be open for extension (e.g., via subclassing) but closed for modification (stable interfaces that limit unintended coupling).
- **OOA organizes requirements around objects** that integrate both processes and data — unlike traditional methods that model data (ER diagrams) and behavior (flowcharts) separately.
- **Iterative over Waterfall**: OOAD acknowledges that analysis can't be fully understood without design context, and coding can reveal design problems. Changes to earlier stages are normal, not failures.
- **Modularity and Reusability**: The OO paradigm emphasizes encapsulation (public/private methods), reducing common programming errors by hiding internal behaviors.
- **Dependency Injection**: Needed objects are passed in rather than created internally, improving testability and decoupling.
- **Acyclic Dependencies Principle**: The dependency graph of packages/components must form a directed acyclic graph (DAG) — no cycles allowed.
- **Composite Reuse Principle**: Favor polymorphic composition over inheritance (from the Gang of Four).

## Commands and Syntax

No CLI commands per se, but the methodology specifies key modeling artifacts and UML diagram types:

- **OOA Artifacts**: Conceptual model, use cases/use case diagrams, system sequence diagrams (SSD), UI documentation, relational data model
- **OOD Artifacts**: Sequence diagrams (extended with specific objects), class diagrams (attributes, relationships, methods)
- **UML Class Diagram**: Static structure showing classes, attributes, and relationships — can be auto-generated from sequence diagram analysis
- **UML Sequence Diagram**: Shows object interactions over time as horizontal arrows between parallel vertical lifelines

## Relationships

- **Unified Process / RUP**: The iterative framework most commonly used to execute OOAD
- **UML**: The standard visual notation for OOAD artifacts (class, sequence, use case, state machine diagrams)
- **SOLID Principles**: OOAD embodies these — particularly Open-Closed and Dependency Inversion
- **Design Patterns (GoF)**: Used during OOD to solve recurring design problems; the Composite Reuse Principle originates here
- **Domain-Driven Design (DDD)**: A complementary approach that shares OOAD's focus on domain modeling but emphasizes ubiquitous language and bounded contexts
- **GRASP**: A set of OO design principles (General Responsibility Assignment Software Patterns) that guide responsibility assignment during OOD
- **Object-Relational Mapping**: The strategy for mapping OO models to relational databases is an explicit output of the OOD phase
- **Waterfall vs. Iterative**: OOAD can work in either but strongly prefers iterative; the spiral model (Boehm) influenced this preference

## Exam-Relevant Points

- OOA produces: conceptual model, use cases, system sequence diagrams, UI docs, relational data model — all feed into OOD
- OOD activities: define objects/attributes, create class diagrams from conceptual models, apply design patterns, identify persistent objects, design ORM strategy, identify remote objects
- The conceptual model is explicitly **implementation-independent** — no concurrency or storage details
- Composite Reuse Principle = prefer composition over inheritance (know this by name)
- Acyclic Dependencies Principle = no cycles in the package dependency graph (DAG)
- Dependency Injection = pass dependencies in rather than construct them internally
- OOA integrates process and data in objects; traditional analysis separates them (ER diagrams for data, flowcharts for behavior)
- Key references: Jacobsen et al. *Object Oriented Software Engineering* (1992), Meyer *Object-Oriented Software Construction* (1988), Gamma et al. *Design Patterns* (1995), Larman *Applying UML and Patterns*
