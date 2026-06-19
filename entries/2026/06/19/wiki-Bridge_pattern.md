---
source: sources/wiki-Bridge_pattern.md
source_url: https://en.wikipedia.org/wiki/Bridge_pattern
---

## Bridge Pattern — Decoupling Abstraction from Implementation

The Bridge pattern is a structural GoF design pattern that separates an abstraction from its implementation so the two can vary independently. Instead of a single inheritance hierarchy where subclasses mix abstraction and implementation concerns, Bridge uses composition: the abstraction holds a reference to an implementor object and delegates to it. This allows both hierarchies to evolve without affecting each other.

## Key Concepts

- **Core intent**: Decouple an abstraction from its implementation so both can vary independently at runtime
- **Two separate hierarchies**: One for the abstraction (what the client uses) and one for the implementation (how operations are carried out)
- **Delegation over inheritance**: The abstraction delegates work to an implementor object via composition/aggregation, not through subclassing
- **Runtime binding**: Implementation can be selected or swapped at runtime, unlike compile-time inheritance binding
- **Four participants**:
  - **Abstraction** — defines the high-level interface; holds a reference to an Implementor
  - **RefinedAbstraction** — extends the Abstraction interface
  - **Implementor** — defines the interface for implementation classes
  - **ConcreteImplementor** — provides a concrete implementation of the Implementor interface
- Uses encapsulation, aggregation, and can use inheritance to separate responsibilities
- When only one fixed implementation exists, this degenerates to the **Pimpl idiom** (C++)
- Creates "two layers of abstraction"

## Commands and Syntax

No CLI commands. The pattern is structural — key implementation steps:

1. Define an **Implementor interface** with primitive operations
2. Create **ConcreteImplementor** classes that fulfill that interface
3. Define an **Abstraction** class that holds a reference to an Implementor
4. The Abstraction delegates calls to the Implementor: `this.implementor.operation()`
5. Create **RefinedAbstraction** subclasses to extend the abstraction without touching the implementor hierarchy

Typical structure (pseudocode):
```
class Abstraction {
    Implementor impl;
    operation() { impl.operationImpl(); }
}
```

## Relationships

- **vs. Adapter pattern**: Often confused — Adapter makes incompatible interfaces work together after design; Bridge is designed upfront to let abstraction and implementation vary independently. Bridge is often *implemented using* the object adapter pattern
- **vs. Strategy pattern**: Both use composition to delegate behavior, but Strategy varies a single algorithm while Bridge separates an entire abstraction from its implementation hierarchy
- **vs. Template Method**: Template Method uses inheritance to vary steps; Bridge uses composition to vary the entire implementation
- **Related to Abstract Factory**: Can be used together — Abstract Factory can create the concrete implementors that the Bridge uses
- **Part of GoF Structural patterns**: alongside Adapter, Composite, Decorator, Facade, Flyweight, Proxy

## Exam-Relevant Points

- Bridge is a **structural** pattern (not behavioral or creational)
- The defining phrase is: *"decouple an abstraction from its implementation so that the two can vary independently"*
- Bridge avoids **compile-time binding** between abstraction and implementation — enables **runtime selection**
- The pattern uses **composition/delegation**, not inheritance, as the primary decoupling mechanism
- Bridge solves the problem of **class explosion** when both abstraction and implementation dimensions multiply (M × N subclasses become M + N classes)
- The Abstraction holds a **reference** to the Implementor (aggregation), not an inheritance relationship
- With a single fixed implementation, Bridge reduces to the **Pimpl idiom**
- Bridge is one of the 23 GoF patterns from *Design Patterns: Elements of Reusable Object-Oriented Software* (1994)
- The pattern is useful when **both the class and what it does vary often**
- Key distinction from Adapter: Bridge is designed **upfront** to separate concerns; Adapter is applied **after** to reconcile incompatible interfaces
