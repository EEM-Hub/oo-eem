---
source: sources/open-closed-principle.md
source_url: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
---

## The Open-Closed Principle (OCP)

The Open-Closed Principle states that software entities should be open for extension but closed for modification. One of the five SOLID principles (the "O"), it has been interpreted in two distinct ways historically: Meyer's inheritance-based approach (1988) and the later polymorphic/abstract-interface approach popularized by Robert C. Martin in the 1990s.

## Key Concepts

- **Core rule**: Extend behavior without modifying existing source code.
- **Open** means available for extension (new fields, functions, behaviors can be added).
- **Closed** means available for use by other modules with a stable, well-defined interface.
- **Meyer's version (1988)**: Uses concrete implementation inheritance. A compiled, library-stored class is closed for use but open via subclassing. Adding a descendant doesn't modify the original or disturb existing clients.
- **Polymorphic version (1990s)**: Uses abstract base classes and interfaces. Multiple implementations can be polymorphically substituted. The interface is closed to modification; new implementations must satisfy it.
- The polymorphic version deliberately separates interface reuse (via inheritance) from implementation reuse — the opposite emphasis from Meyer's original.
- Craig Larman linked OCP to Cockburn's **Protected Variations** pattern and Parnas's **information hiding**, showing OCP as one instance of a broader design strategy.

## Commands and Syntax

No commands. The principle is a design guideline applied through language mechanisms:

- **Meyer's approach**: Define a concrete class; extend via subclass inheritance.
- **Polymorphic approach**: Define an abstract base class or interface; provide concrete implementations that satisfy the contract.

```
# Polymorphic OCP example (conceptual)
abstract class Shape { abstract area(): number }
class Circle extends Shape { area() { ... } }   // new extension, no modification to Shape
class Square extends Shape { area() { ... } }   // another extension
```

## Relationships

- **SOLID**: OCP is the "O"; works alongside SRP, LSP, ISP, and DIP. LSP in particular constrains how subclasses extend behavior without breaking substitutability.
- **Protected Variations (Cockburn)**: OCP is a specific case of this broader pattern — identify predicted variation points and shield stable code behind stable interfaces.
- **Information Hiding (Parnas)**: The intellectual ancestor; OCP operationalizes hiding decisions behind interfaces.
- **Robustness Principle**: Related concern about stability under change, though applied at protocol/API boundaries rather than class design.
- **Strategy / Template Method patterns**: Common implementation vehicles for achieving OCP in practice.

## Exam-Relevant Points

- OCP = "open for extension, closed for modification" — know the exact phrasing.
- Two historical interpretations: Meyer's (concrete inheritance, 1988) vs. polymorphic (abstract interfaces, 1990s) — know the distinction.
- Meyer coined the term in *Object-Oriented Software Construction* (1988).
- Robert C. Martin's 1996 *C++ Report* article is the seminal reference for the polymorphic version.
- The polymorphic version is the modern, widely-adopted interpretation.
- OCP is the "O" in SOLID.
- Larman connected OCP to Protected Variations and information hiding — expect questions linking these concepts.
- Key motivation: changing existing code risks breaking existing clients; extending via new classes/implementations avoids that risk.
