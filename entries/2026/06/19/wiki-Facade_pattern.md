---
source: sources/wiki-Facade_pattern.md
source_url: https://en.wikipedia.org/wiki/Facade_pattern
---

## Facade Pattern: Simplified Interface for Complex Subsystems

The Facade pattern is a structural design pattern from the Gang of Four catalog that provides a simplified, unified interface to a complex subsystem of classes. By wrapping multiple interdependent components behind a single object, it reduces coupling between clients and the subsystem, improving usability, readability, and maintainability.

## Key Concepts

- **Core intent**: Provide a single, simplified API that delegates to a set of more complex underlying interfaces
- **One of the 23 GoF design patterns**, classified as a **structural** pattern
- **Problems it solves**: (1) making complex subsystems easier to use, (2) minimizing client dependencies on subsystem internals
- **Facade object** implements a simple interface by delegating to subsystem classes, and may perform additional logic before/after forwarding requests
- **Clients depend only on the Facade**, not on the many subsystem classes directly — this replaces tight coupling with loose coupling
- **Typically involves a single wrapper class** containing members that access the subsystem on behalf of the client while hiding implementation details
- **Distinction from related patterns**:
  - **Adapter**: converts one interface to match what a client expects (interface compatibility)
  - **Decorator**: dynamically adds/alters behavior of an interface at run-time (behavioral extension)
  - **Facade**: provides a simplified interface (complexity reduction)

## Commands and Syntax

No specific commands — this is a design pattern. Implementation involves:

1. Identify the complex subsystem classes and their interfaces
2. Create a Facade class that exposes a simplified API
3. The Facade delegates calls to appropriate subsystem objects internally
4. Clients interact only with the Facade, never directly with subsystem classes

**Structural pattern**: Client → Facade → {Class1, Class2, Class3}

## Relationships

- **Adapter pattern**: use when the wrapper must conform to a specific interface and support polymorphism; Facade does not require interface conformance
- **Decorator pattern**: use when you need to add/alter behavior dynamically; Facade simplifies rather than extends
- **Encapsulation**: Facade is a practical application of encapsulation at the subsystem level
- **Refactoring**: Facade can serve as a stepping stone when refactoring monolithic or tightly-coupled systems toward loose coupling
- **Layered architectures**: Facade provides entry points at each layer level
- Commonly used with hardware register protocols (Modbus, I2C) to abstract indexed-value access

## Exam-Relevant Points

- Facade is a **structural** pattern, not behavioral or creational
- Primary purpose is **simplification**, not interface conversion (Adapter) or behavioral extension (Decorator)
- Know the three-way comparison table: Adapter = converts interface, Decorator = adds responsibility dynamically, Facade = simplifies interface
- Facade **reduces dependencies** on subsystem classes — clients depend only on the Facade
- Facade may perform **additional functionality** before/after forwarding requests (not just pure delegation)
- Use when: system is complex/hard to understand, subsystem abstractions are tightly coupled, or a simple entry point is needed for layered software
- Facade is a **launching point for refactoring** tightly-coupled code toward loose coupling
- From GoF: *Design Patterns: Elements of Reusable Object-Oriented Software* (1994), pp. 185ff
