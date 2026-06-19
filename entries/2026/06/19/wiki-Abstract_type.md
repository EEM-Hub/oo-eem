---
source: sources/wiki-Abstract_type.md
source_url: https://en.wikipedia.org/wiki/Abstract_type
---

## Abstract Types in Object-Oriented Programming

Abstract types (also known as existential types) are types in a nominative type system that cannot be instantiated directly. They serve as blueprints that define a contract — a set of operations or properties — that concrete subtypes must implement. Abstract types are a foundational mechanism for achieving polymorphism, enforcing protocols, and separating interface from implementation in statically typed OOP languages.

## Key Concepts

- **Abstract type**: A type that cannot be instantiated directly; instantiation occurs only through a concrete subtype.
- **Concrete type**: A type that *can* be instantiated directly — the complement of an abstract type.
- **Abstract method / pure virtual function**: A method declared in an abstract type with no implementation; concrete subtypes must provide the implementation.
- **Incomplete vs. no implementation**: Abstract types may provide *some* implemented methods (incomplete) or *none*. Types with no implementation are variously called **protocols**, **interfaces**, **signatures**, or **class types** depending on the language.
- **Propagation of abstractness**: A child type that inherits from an abstract type but does not implement all abstract methods is itself abstract.
- **Related language features**: Traits, mixins, flavors, roles, and type classes are all mechanisms that can implement or approximate abstract types.
- **In generic programming**, the analogous concept is a **concept** — it specifies syntax and semantics but does not require a subtype relationship (two unrelated types can satisfy the same concept).
- **Design heuristic**: Some authors (Riel, Meyers) argue that all non-leaf classes should be abstract — classes should either be abstract (with subtypes) or concrete leaves (with no subtypes).

## Commands and Syntax

**Java — Creating abstract classes and interfaces:**

```java
// 'abstract' keyword prevents direct instantiation
abstract class Demo {
    // Abstract method — no body, subclass must implement
    public abstract int sum(int x, int y);

    // Concrete method — has implementation, inherited as-is
    public int product(int x, int y) {
        return x * y;
    }
}

// Interface — all methods abstract by default
interface DemoInterface {
    int getLength();  // implicitly abstract

    // 'default' keyword allows concrete methods in interfaces
    default int product(int x, int y) {
        return x * y;
    }
}
```

**Four ways to create/signal an abstract class:**

1. **Explicit keyword** — `abstract class Foo` (Java, C#, D)
2. **Abstract methods** — Include a pure virtual function (C++) or abstract method; class becomes abstract implicitly
3. **Incomplete inheritance** — Inherit from abstract parent without overriding all abstract methods
4. **Dynamic convention** — In Smalltalk/Objective-C, sending `self` a method with no implementation (detected at runtime, not compile time)

## Relationships

- **Template Method Pattern**: Abstract types are essential — the base class defines invariant "template" methods that call abstract "hook" methods overridden by concrete subclasses.
- **Interfaces vs. Abstract Classes**: Interfaces define pure contracts (no state, historically no implementation); abstract classes can mix abstract and concrete members with state.
- **Duck Typing**: In dynamically typed languages, duck typing makes abstract types largely unnecessary since the contract is implicit rather than declared.
- **Subtyping / Inheritance**: Abstract types are the mechanism through which subtype polymorphism is enforced — the abstract type defines the contract, concrete subtypes fulfill it.
- **Generic Programming / Concepts**: Concepts serve a similar role to abstract types but without requiring inheritance; they constrain type parameters by required operations.

## Exam-Relevant Points

- An abstract class **cannot be instantiated** — only its concrete subclasses can be.
- A class with **even one abstract method** is abstract (in C++, a class with at least one pure virtual function).
- A subclass that **does not implement all inherited abstract methods** is itself abstract.
- In Java: `abstract` keyword on class/method; in C++: `= 0` suffix makes a pure virtual function.
- Java interfaces have **all methods abstract by default**; the `default` keyword (Java 8+) allows concrete methods in interfaces.
- Abstract types enforce a **protocol** — a contract that all implementing types must satisfy.
- The distinction between abstract type and **abstract data type (ADT)** — these are different concepts. An abstract type is about instantiation and subtyping; an ADT is about encapsulation and information hiding.
- **"Make non-leaf classes abstract"** (Meyers) is a recognized design heuristic — every class should be either a concrete leaf or an abstract interior node in the hierarchy.
- In dynamically typed languages, abstract method violations are detected **at runtime**, not compile time (e.g., Objective-C's `doesNotRecognizeSelector:` exception).
