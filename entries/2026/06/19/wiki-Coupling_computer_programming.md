---
source: sources/wiki-Coupling_computer_programming.md
source_url: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
---

## Coupling in Software Modules

Coupling is the degree of interdependence between software modules — a measure of how closely connected two routines or modules are and the strength of their relationships. Coined by Larry Constantine in the late 1960s as part of structured design, coupling is not binary but multi-dimensional. Low coupling combined with high cohesion is widely considered a hallmark of well-structured, readable, and maintainable systems.

## Key Concepts

- **Coupling** measures inter-module dependency; **cohesion** measures intra-module relatedness. They are inversely correlated: low coupling typically accompanies high cohesion.
- Coupling ranges from "low" (loose/weak) to "high" (tight/strong).
- **Procedural coupling types** (highest to lowest):
  - **Content coupling** — one module directly uses another's code (e.g., branching into it). Violates information hiding.
  - **Common coupling** — modules share global data. Risks uncontrolled error propagation and side effects.
  - **External coupling** — modules share an externally imposed data format, protocol, or device interface.
  - **Control coupling** — one module controls another's flow by passing a what-to-do flag.
  - **Stamp coupling** — modules share a composite data structure but use only parts of it. Changes to unused fields can still force retesting.
  - **Data coupling** — modules share only elementary data through parameters (the loosest procedural form).
- **OO-specific coupling types**:
  - **Subclass coupling** — child depends on parent, but parent does not depend on child.
  - **Temporal coupling** — actions bundled into one module only because they happen at the same time.
- **Dynamic coupling** — measured at runtime; addresses precision loss of static metrics when dynamic binding or inheritance is heavily used.
- **Semantic coupling** — measures conceptual similarity between entities using comments, identifiers, and techniques like Latent Semantic Indexing.
- **Logical (evolutionary/change) coupling** — detected from release history; identifies modules that tend to change together.
- **Hohpe's eight dimensions of coupling**: Technology, Location, Topology, Data Format & Type, Semantic, Conversation, Order, and Temporal dependency.

## Commands and Syntax

- **Coupling metric formula** (Pressman):
  - `C(module) = 1 - 1 / (di + 2*ci + do + 2*co + gd + 2*gc + w + r)`
  - Where: `di`/`do` = input/output data params, `ci`/`co` = input/output control params, `gd`/`gc` = global data/control variables, `w` = fan-out (modules called), `r` = fan-in (modules calling this one).
  - Range: ~0.67 (low coupling) to 1.0 (high coupling).
  - Example: single input + single output data param + fan-out of 1 → C = 0.67.
  - Example: 5 data + 5 control params each way, 10 global data items, fan-in 3, fan-out 4 → C = 0.98.
- **Coupling increases** between classes A and B if: A has an attribute of type B, A calls services on B, A has a method referencing B (parameter or return type), or A is a subclass of B.

## Relationships

- **Cohesion**: Coupling's complement — high cohesion within modules enables low coupling between them.
- **Information hiding**: Content coupling violates this principle; reducing coupling enforces it.
- **Connascence** (Page-Jones): A finer-grained framework for analyzing coupling. Evaluates dependencies by strength, locality, and degree. Static connascence is detectable at compile time; dynamic connascence at runtime. Connascence of name is weaker (more resilient) than connascence of position or meaning.
- **Dependency injection** and **interface-based programming**: Modern practices to reduce coupling strength.
- **CORBA/COM**: Middleware systems that enable communication between objects without knowledge of each other's implementation, reducing coupling.
- **Functional design**: An approach that limits module responsibilities along functionality to decrease coupling.
- **Inversion of control**: Related architectural principle for managing dependencies.
- **Loose coupling**: The design goal; interacting through simple, stable interfaces without concern for internal implementation.

## Exam-Relevant Points

- Know the six procedural coupling types in order from tightest to loosest: content → common → external → control → stamp → data.
- Tight coupling causes ripple effects, harder reuse/testing, and increased assembly effort.
- Coupling is multi-dimensional (Hohpe identifies 8 dimensions), not a single scalar.
- The coupling metric formula uses control parameters weighted 2x compared to data parameters, reflecting their greater impact on interdependence.
- Connascence differs from coupling by adding locality and degree dimensions; connascence of name is weaker than connascence of position.
- Stamp coupling passes entire data structures when only parts are needed — a common exam scenario illustrating unnecessary dependency.
- Low coupling + high cohesion = the canonical sign of good modular design.
- Larry Constantine originated these metrics in the late 1960s; formalized in Stevens, Myers & Constantine (1974) and Yourdon & Constantine (1979).
