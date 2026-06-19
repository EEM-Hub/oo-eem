---
source: sources/wiki-Information_hiding.md
source_url: https://en.wikipedia.org/wiki/Information_hiding
---

## Information Hiding: Segregating Design Decisions to Limit Change Impact

Information hiding is a foundational principle of software design that prescribes isolating design decisions likely to change behind stable interfaces, so that modifications remain local rather than rippling through the entire program. First described by David Parnas in 1972, it provides the intellectual basis for modular decomposition and is a core motivation behind encapsulation in object-oriented programming.

## Key Concepts

- **Information hiding** is the *principle*: segregate volatile design decisions behind stable interfaces so that change is local, not global.
- **Encapsulation** is often used interchangeably but is more precisely the *technique* or *mechanism* that enforces information hiding (e.g., private variables, explicit export policies).
- The distinction matters: encapsulation bundles structure and behavior together; information hiding is the *reason* you do it — to protect against change.
- A module designed with information hiding protects the rest of the program from changes to internal representation (e.g., switching a 3D point from three scalars to an array).
- In OOP, information hiding shifts dependency from uncertain implementations onto well-defined interfaces — clients operate through the interface and need not change when implementation changes.
- Benefits: enables independent component evolution, preserves component integrity (prevents invalid internal state), reduces system complexity, increases robustness by limiting interdependencies.
- Encapsulation is more general than OOP — a relational database encapsulates behind SQL, hiding all internal machinery.
- Grady Booch defined encapsulation as "the process of compartmentalizing the elements of an abstraction that constitute its structure and behavior; encapsulation serves to separate the contractual interface of an abstraction and its implementation."

## Commands and Syntax

No specific commands or code syntax — this is a design principle. The practical application manifests through:

- **Access modifiers**: `private`, `protected`, `public` in languages like Java/C++
- **Explicit export policies**: module systems that declare what is visible externally
- **Interface definitions**: abstract types or protocols that specify the contract without revealing implementation

## Relationships

- **Encapsulation (OOP)** — the primary mechanism for implementing information hiding in object-oriented systems
- **Modularity / Modular Programming** — information hiding provides the *criterion* for decomposing systems into modules (Parnas's original contribution)
- **Law of Demeter** — a specific heuristic that enforces information hiding by restricting which objects a method may interact with
- **Opaque Data Types** — a language-level mechanism for hiding representation details
- **Implementation Inheritance / Virtual Inheritance** — inheritance can either support or violate information hiding depending on whether subclasses depend on superclass internals
- **Scope (programming)** — language rules that control visibility, directly enabling information hiding
- **Interface (computer science)** — the stable contract that information hiding depends on

## Exam-Relevant Points

- **Parnas (1972)** first described information hiding — "On the Criteria To Be Used in Decomposing Systems into Modules" is the seminal paper.
- Information hiding is about hiding **design decisions likely to change**, not just hiding data.
- Encapsulation and information hiding are **not synonyms**: information hiding is the principle, encapsulation is the technique. Some authors (notably Wm. Paul Rogers) argue explicitly that "encapsulation is not information hiding."
- The primary benefit is **localizing the impact of change** — evolutionary modifications stay local rather than global.
- Information hiding applies **at every level of granularity**, not just classes — modules, subsystems, databases, hardware components.
- A well-designed interface lets a component be **replaced entirely** as long as the new component supports the same public interface.
- Encapsulation protects **component integrity** by preventing clients from setting internal state to invalid or inconsistent values.
- Modularity existed before Parnas (Gauthier & Pont, 1970), but Parnas provided the *criterion* — hide what is likely to change — that distinguishes principled modular decomposition from ad hoc code organization.
