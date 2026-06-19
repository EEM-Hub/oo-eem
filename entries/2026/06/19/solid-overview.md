---
source: sources/solid-overview.md
source_url: https://en.wikipedia.org/wiki/SOLID
---

## SOLID Design Principles

SOLID is a mnemonic acronym for five object-oriented design principles that make source code more understandable, flexible, and maintainable. Introduced conceptually by Robert C. Martin in his 2000 paper *Design Principles and Design Patterns* and named by Michael Feathers circa 2004, these principles are foundational to agile and adaptive software development methodologies.

## Key Concepts

- **Single Responsibility Principle (SRP):** A class should have only one reason to change — it should encapsulate exactly one responsibility. Improves maintainability, testability, and isolation of changes.
- **Open-Closed Principle (OCP):** Software entities should be open for extension but closed for modification. New behavior is added by extending, not by altering existing code, reducing regression risk.
- **Liskov Substitution Principle (LSP):** Objects of a derived class must be substitutable for objects of their base class without breaking program correctness. Subclasses must honor the superclass contract. Related to design by contract.
- **Interface Segregation Principle (ISP):** Clients should not be forced to depend on interface methods they do not use. Prefer many small, focused interfaces over one large general-purpose interface.
- **Dependency Inversion Principle (DIP):** Depend on abstractions, not concretions. High-level modules should not depend on low-level modules; both should depend on abstractions.
- SOLID addresses **software rot** — the gradual degradation of software quality over time.
- The principles collectively promote **loose coupling**, **high cohesion**, **extensibility**, and **maintainability**.

## Commands and Syntax

No specific commands. SOLID is a set of design guidelines applied through code structure decisions. Typical application patterns:

- **SRP:** Extract classes until each has a single axis of change.
- **OCP:** Use inheritance, composition, or strategy patterns to extend behavior without modifying existing classes.
- **LSP:** Ensure subclass preconditions are no stronger and postconditions no weaker than the superclass.
- **ISP:** Split fat interfaces into role-specific interfaces (e.g., `Readable`, `Writable` instead of one `ReadWritable`).
- **DIP:** Inject dependencies via constructor or method parameters typed to interfaces/abstractions, not concrete classes.

## Relationships

- **Design by Contract** — LSP is closely related; subclasses must preserve the behavioral contract of the superclass.
- **GRASP Principles** — Complementary set of OO design guidelines (e.g., Information Expert, Creator, Low Coupling).
- **Code Reuse** — SOLID facilitates safe reuse through stable abstractions and substitutable components.
- **Inheritance** — LSP directly governs correct use of inheritance hierarchies.
- **Agile / Adaptive Development** — SOLID underpins these methodologies by enabling code that responds well to changing requirements.
- **Design Patterns** — Many GoF patterns (Strategy, Template Method, Factory, Decorator) are direct applications of one or more SOLID principles.

## Exam-Relevant Points

- Know the full expansion: **S**ingle Responsibility, **O**pen-Closed, **L**iskov Substitution, **I**nterface Segregation, **D**ependency Inversion.
- **Robert C. Martin** articulated the principles (2000); **Michael Feathers** coined the acronym (c. 2004).
- SRP: "never more than one reason for a class to change."
- OCP: "open for extension, closed for modification."
- LSP: derived class objects must be seamlessly substitutable for base class objects — violation breaks polymorphism.
- ISP: prevents clients from depending on methods they don't use — the remedy is splitting interfaces.
- DIP: "depend upon abstractions, not concretes" — this is the principle behind dependency injection.
- LSP is the principle most directly tied to **design by contract**.
- DIP distinguishes between high-level policy and low-level detail — both should depend on abstractions.
- Violating OCP means every new feature risks breaking existing functionality.
- Violating ISP leads to "fat interfaces" that force implementors to provide stub or no-op methods.
