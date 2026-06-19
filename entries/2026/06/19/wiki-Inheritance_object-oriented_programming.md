---
source: sources/wiki-Inheritance_object-oriented_programming.md
source_url: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
---

## Inheritance in Object-Oriented Programming

Inheritance is the mechanism of basing a class or object upon another, allowing derived classes (subclasses) to acquire properties and behaviors from existing classes (superclasses). It serves two distinct purposes that are often conflated: code reuse (implementation inheritance) and establishing type relationships (interface inheritance/subtyping). The relationships formed through inheritance produce a directed acyclic graph of classes. Originating with Hoare's 1966 work on record subclasses and first implemented in Simula 67, inheritance became a foundational OOP mechanism adopted across Smalltalk, C++, Java, Python, and most modern OO languages.

## Key Concepts

- **Inheritance vs. Subtyping**: Inheritance reuses implementation and establishes a syntactic relationship; subtyping establishes a semantic *is-a* relationship enabling substitutability. In some languages (C++, Java, C#) they coincide; in others they differ.
- **Implementation inheritance** (code inheritance): subclass reuses base class code. **Interface inheritance**: subclass commits to a common API without sharing implementation.
- **Inheritance vs. Composition**: Inheritance = *is-a*; Composition = *has-a*. The **Composite Reuse Principle** and **composition over inheritance** are preferred alternatives when code reuse is the sole goal.
- **Fragile base class problem**: Modifications to a base class can cause unintended behavioral changes in subclasses, breaking encapsulation. This is the central criticism of implementation inheritance.
- **Liskov Substitution Principle (LSP)**: Inheritance does not guarantee behavioral subtyping — a derived class may behave incorrectly when substituted for its parent.
- **Delegation**: The prototype-based equivalent of class-based inheritance (one object delegates to another rather than inheriting from a class).
- **Class hierarchy forms a strict partial order** on the set of classes mathematically.
- In C++, child objects acquire all parent properties **except**: constructors, destructors, overloaded operators, and friend functions.

## Types of Inheritance

- **Single inheritance**: Subclass inherits from exactly one superclass.
- **Multiple inheritance**: Subclass inherits from more than one superclass. Introduces complexity (diamond problem). Implemented in C++ (Stroustrup solved efficient implementation in 1984), Python, Eiffel.
- **Multilevel inheritance**: Chain of derivation (A -> B -> C). B is an intermediate base class; A-B-C is the inheritance path.
- **Hierarchical inheritance**: One superclass has multiple subclasses.
- **Hybrid inheritance**: Combination of the above types.

## Commands and Syntax

**C++ derived class declaration:**
```cpp
class SubClass: visibility SuperClass {
    // subclass members
};
```
Visibility modifier: `private` (default), `protected`, or `public`.

**Java/C# derived class declaration:**
```java
class SubClass extends SuperClass {
    // subclass members
}
```
No visibility modifier; equivalent to C++ public inheritance.

**C++ multilevel inheritance:**
```cpp
class A { ... };
class B : public A { ... };
class C : public B { ... };
```

**Non-subclassable classes:** `final` (Java, C++11+), `sealed` (C#) — prevents further derivation, enables compile-time optimizations (static dispatch instead of vtable lookup).

**Non-overridable methods:** `final` (Java), `sealed` (C#), `frozen` (Eiffel), or `private` access.

**Virtual methods:** Declared `virtual` in C++ for dynamic dispatch; all methods are virtual by default in Java. Non-virtual = static dispatch = faster, allows inlining.

**Visibility of inherited members (C++):**

| Base member | Private derivation | Protected derivation | Public derivation |
|---|---|---|---|
| Private | Not inherited | Not inherited | Not inherited |
| Protected | Private | Protected | Protected |
| Public | Private | Protected | Public |

## Relationships

- **Composition over inheritance**: GoF *Design Patterns* advocates interface inheritance and composition as alternatives to implementation inheritance.
- **Decorator pattern**: Overcomes the static nature of inheritance hierarchies by allowing behavior modification at runtime.
- **Polymorphism**: Inheritance enables polymorphic behavior through virtual methods and dynamic dispatch.
- **Method overriding**: Subclasses replace inherited behavior; governed by language rules (C# requires `virtual`/`abstract`/`override`; Java allows overriding by default).
- **Mixins and Traits**: Alternative composition mechanisms that provide reusable behavior without full inheritance hierarchies.
- **Role-oriented programming**: Introduces a *played-by* relationship combining inheritance and composition properties.
- **Entity-Component-System (ECS)**: Alternative to inheritance that allows runtime definition of entity variations.
- **Diamond problem / Virtual inheritance**: Arises with multiple inheritance when two superclasses share a common ancestor.
- **Circle-ellipse problem**: Classic example of inheritance modeling difficulties and LSP violations.

## Exam-Relevant Points

- Inheritance does **not** guarantee behavioral subtyping — know the distinction between inheritance and subtyping (LSP).
- **Private members are never inherited** in any derivation mode (C++ visibility table).
- `final`/`sealed` classes enable **early binding (static dispatch)** because the compiler knows no subclasses exist — eliminating vtable lookups.
- In C++, default inheritance visibility is **private**; in Java, there is no visibility modifier (effectively public).
- The **fragile base class problem** is the primary argument against implementation inheritance — base class changes break subclasses.
- **C++ private inheritance** models "is implemented in terms of" — provides code reuse without substitutability (not is-a).
- **Three design constraints** of inheritance: Singleness (single inheritance limits dual roles), Static (hierarchy fixed at instantiation), Visibility (superclass data exposed to clients).
- Inheritance creates a **directed acyclic graph** (not a tree when multiple inheritance is used).
- The **yo-yo problem** results from excessively deep inheritance hierarchies — too many thin layers make debugging difficult.
- History: Concept originated with Hoare (1966), first implemented in **Simula 67** by Dahl and Nygaard (1967).
- James Gosling reportedly said he would **not include implementation inheritance** if redesigning Java. Go language decouples inheritance from subtyping entirely.
