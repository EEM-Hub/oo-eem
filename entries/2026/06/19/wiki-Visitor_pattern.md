---
source: sources/wiki-Visitor_pattern.md
source_url: https://en.wikipedia.org/wiki/Visitor_pattern
---

It looks like write permissions are being blocked. Here's the summary I've prepared — you can save it as `entries/2026/06/19/wiki-Visitor_pattern.md`:

---

## Visitor Pattern — Separating Algorithms from Object Structures

The Visitor pattern is a behavioral design pattern (one of the Gang of Four's twenty-three patterns) that separates an algorithm from the object structure it operates on. By externalizing operations into visitor objects, new operations can be added to existing object structures without modifying the element classes. It achieves this through double dispatch: elements accept a visitor via an `accept()` method, which then calls back to the visitor's type-specific `visit()` method.

## Key Concepts

- **Core idea**: Decouple operations from the objects they operate on, allowing new operations to be added without changing element classes.
- **Double dispatch**: The pattern simulates double dispatch in single-dispatch languages — the operation executed depends on both the dynamic type of the element and the dynamic type of the visitor.
- **Open/Closed Principle**: The pattern is a direct application of OCP — element classes are closed for modification but open for extension via new visitor implementations.
- **Three participants**:
  - **Visitor**: Declares a `visit` method for each concrete element type. Concrete visitors implement the actual operations.
  - **Element**: Declares an `accept(visitor)` method. Concrete elements implement it by calling `visitor.visit(this)`, passing themselves back to the visitor.
  - **Client**: Constructs the object structure and instantiates visitors, then initiates traversal by calling `accept()` on top-level elements.
- **The `accept`/`visit` handshake**: `element.accept(visitor)` dispatches based on the element's dynamic type; inside `accept`, `visitor.visit(this)` dispatches based on the visitor's dynamic type — achieving double dispatch through two single dispatches.
- **Languages with sum types and pattern matching** (e.g., ML, Rust, Haskell) largely obviate the Visitor pattern because the compiler can enforce exhaustive case handling natively.

## Commands and Syntax

**Typical structure (Java-style)**:

```java
interface Element {
    void accept(Visitor visitor);
}

class ConcreteElementA implements Element {
    public void accept(Visitor visitor) {
        visitor.visitConcreteElementA(this);
    }
}

interface Visitor {
    void visitConcreteElementA(ConcreteElementA e);
    void visitConcreteElementB(ConcreteElementB e);
}

class PrintVisitor implements Visitor {
    public void visitConcreteElementA(ConcreteElementA e) { /* ... */ }
    public void visitConcreteElementB(ConcreteElementB e) { /* ... */ }
}
```

**Composite traversal**: When an element contains children (e.g., `Car` contains `Wheel`, `Body`, `Engine`), its `accept` method iterates over children calling `child.accept(visitor)` before or after calling `visitor.visit(this)`.

**Go variant**: Since Go lacks method overloading, visit methods must have distinct names (`visitWheel`, `visitEngine`, etc.).

**Common Lisp / multiple dispatch**: In languages supporting multiple dispatch, the pattern dissolves into ordinary generic function overloading — no `accept`/`visit` ceremony needed.

## Relationships

- **Open/Closed Principle**: Visitor is a primary mechanism for satisfying OCP.
- **Single Responsibility Principle**: Each visitor encapsulates a single cross-cutting operation.
- **Double Dispatch**: Visitor is the canonical OO technique for simulating double dispatch in single-dispatch languages.
- **Composite Pattern**: Visitor frequently operates over Composite structures; composite elements delegate `accept()` to children.
- **Iterator Pattern**: Visitor can substitute for iteration over containers, though with limitations (no easy break-out, no concurrent traversal).
- **Strategy Pattern**: Both externalize behavior, but Strategy replaces an algorithm within one class while Visitor adds operations across a hierarchy.

## Exam-Relevant Points

- **Visitor separates algorithm from object structure** — the one-line definition.
- **Fundamental trade-off**: Adding new operations is easy (new visitor); adding new element types is hard (every visitor must be updated).
- **Best when**: class hierarchy is stable; new operations are frequently needed.
- **Worst when**: element types change often — forces changes to all visitors.
- **Uses double dispatch**: `accept()` dispatches on element type, then `visit()` dispatches on visitor type.
- **GoF behavioral pattern**: One of the 23 Gang of Four patterns.
- **Public API extensibility**: Ideal for public APIs — clients add operations via visitors without modifying library source.
- **Five conditions favoring Visitor**: (1) many unrelated operations needed, (2) element classes stable, (3) new operations added frequently, (4) algorithm spans multiple classes but should live in one place, (5) algorithm works across independent class hierarchies.
- **Pattern matching languages** make Visitor largely unnecessary — exhaustive matching provides compile-time safety without the ceremony.
