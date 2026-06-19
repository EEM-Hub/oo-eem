---
source: sources/wiki-Design_Patterns.md
source_url: https://en.wikipedia.org/wiki/Design_Patterns
---

## Design Patterns: Elements of Reusable Object-Oriented Software (Gang of Four)

This is the seminal 1994 book by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides — collectively known as the "Gang of Four" (GoF). It catalogs 23 classic software design patterns organized into three categories (creational, structural, behavioral) and establishes foundational object-oriented design principles. Over 500,000 copies sold in 14 languages; it received the 2005 ACM SIGPLAN Programming Languages Achievement Award.

## Key Concepts

- **"Program to an interface, not an implementation"** — clients should depend on abstract interfaces, not concrete classes, enabling dynamic binding and polymorphism.
- **Composition over inheritance** — favor object composition ("black-box reuse") over class inheritance ("white-box reuse") because inheritance breaks encapsulation by exposing parent implementation details to subclasses.
- **Inheritance as white-box reuse** — parent internals are visible to subclasses; changes to parent force subclass changes. Use inheritance mainly when adding small amounts of new functionality to existing components.
- **Composition as black-box reuse** — objects with well-defined interfaces are composed at runtime; no internal details need be visible.
- **Delegation** — an extreme form of composition where a sender passes itself to a delegate; relationships established at runtime, not compile-time. Can always replace inheritance.
- **Aggregation vs. acquaintance** — aggregation implies shared lifetimes ("has-a" / "part-of"); acquaintance (association) implies loose coupling ("knows-of" / "uses"). Acquaintance is weaker and often more desirable for maintainability.
- **Parameterized types (generics/templates)** — allow types to be defined without specifying all dependent types; powerful but "dynamic, highly parameterized software is harder to understand and build."
- **Toolkit vs. framework** — a toolkit is an OO subroutine library; a framework is a set of cooperating classes forming a reusable design. Frameworks are the hardest to design.

## Commands and Syntax

No commands per se — the book provides pattern templates. Each of the 23 patterns is documented with intent, motivation, applicability, structure (class diagrams), participants, collaborations, consequences, implementation notes, sample code (C++ and Smalltalk), known uses, and related patterns.

### The 23 GoF Patterns

**Creational (5):**
- **Abstract Factory** — groups object factories with a common theme
- **Builder** — separates construction from representation for complex objects
- **Factory Method** — creates objects without specifying the exact class
- **Prototype** — creates objects by cloning an existing instance
- **Singleton** — restricts a class to one instance

**Structural (7):**
- **Adapter** — wraps an interface to make incompatible classes work together
- **Bridge** — decouples abstraction from implementation for independent variation
- **Composite** — composes objects into tree structures for uniform treatment
- **Decorator** — dynamically adds/overrides behavior on an existing object
- **Facade** — provides a simplified interface to a complex subsystem
- **Flyweight** — shares state to support large numbers of fine-grained objects
- **Proxy** — provides a surrogate to control access, reduce cost, or reduce complexity

**Behavioral (11):**
- **Chain of Responsibility** — passes requests along a chain of handlers
- **Command** — encapsulates actions and parameters as objects
- **Interpreter** — implements a specialized language
- **Iterator** — sequential access without exposing underlying representation
- **Mediator** — centralizes complex communication between objects (loose coupling)
- **Memento** — captures and restores object state (undo)
- **Observer** — publish/subscribe notification of state changes
- **State** — alters behavior when internal state changes
- **Strategy** — selects an algorithm at runtime from a family of algorithms
- **Template Method** — defines an algorithm skeleton; subclasses fill in steps
- **Visitor** — separates an algorithm from the object structure it operates on

## Relationships

- **Christopher Alexander's pattern language** — the GoF adapted Alexander's architectural pattern concept to software.
- **GRASP principles** — General Responsibility Assignment Software Patterns provide complementary guidance on responsibility assignment in OO design.
- **Enterprise Integration Patterns** — extends the pattern catalog concept to messaging and integration.
- **Aspect-Oriented Programming** — Hannemann and Kiczales showed AspectJ simplifies or eliminates code-level dependencies in 17 of the 23 patterns.
- **Dynamic languages (Lisp, Dylan)** — Peter Norvig demonstrated that 16 of 23 patterns are simplified or eliminated by features in dynamic languages, supporting Paul Graham's criticism that patterns compensate for language limitations.
- **Later proposed patterns** — the authors themselves suggested adding extension object/interface, dependency injection, type object, and null object; Gamma wanted to remove Singleton.
- **Anti-patterns** — the pattern concept spawned the complementary concept of anti-patterns (recurring poor solutions).

## Exam-Relevant Points

- The book defines exactly **23 patterns** in **3 categories**: 5 creational, 7 structural, 11 behavioral.
- The four authors are collectively called the **"Gang of Four" (GoF)**.
- The two core design principles are: **"program to an interface, not an implementation"** and **"favor object composition over class inheritance."**
- Inheritance is called **white-box reuse** (internals visible); composition is called **black-box reuse** (internals hidden).
- **"Inheritance breaks encapsulation"** — subclasses are coupled to parent implementation details.
- Delegation can **always** replace inheritance but adds runtime complexity.
- Aggregation implies **shared lifetimes**; acquaintance (association) implies **loose coupling** and is generally preferred.
- Peter Norvig showed **16 of 23** patterns are simplified or eliminated in dynamic languages.
- The book uses **C++ and Smalltalk** for code examples.
- Published **1994**, examples originate from work beginning at **OOPSLA 1990**.
- In a 2009 retrospective, the authors would have **added** dependency injection, extension object, type object, and null object; Gamma wanted to **remove Singleton** but lacked consensus.
