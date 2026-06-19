---
source: sources/wiki-Object-oriented_programming.md
source_url: https://en.wikipedia.org/wiki/Object-oriented_programming
---

## Object-Oriented Programming: Paradigm Overview and Core Features

Object-oriented programming (OOP) is a programming paradigm based on objects — software entities that encapsulate data and behavior. Programs consist of objects that interact with one another. OOP is not a single fixed definition but a contested set of features; most modern languages are multi-paradigm, supporting OOP alongside other styles. This page covers OOP's history, core features (encapsulation, inheritance, polymorphism, dynamic dispatch), design patterns, and notable criticisms.

## Key Concepts

- **Object**: An entity combining data (fields/attributes/properties) and behavior (methods/functions). Objects are instances of classes (class-based) or linked to prototypes (prototype-based).
- **Encapsulation**: Bundling related data and methods together; controlling visibility via access modifiers (`private`, `public`, `protected`, `internal`). Three related ideas: cohesion, decoupling, and data hiding.
- **Inheritance**: Mechanism for creating new classes/objects from existing ones. Class-based (subclass extends superclass) or prototype-based (object delegates to prototype). Go deliberately omits inheritance, favoring composition.
- **Polymorphism**: Subtype polymorphism — a function operates on an interface, allowing uniform treatment of different concrete types. The runtime dispatches to the correct method implementation.
- **Dynamic Dispatch**: Method selection at runtime rather than compile time. Single dispatch (based on receiver) vs. multiple dispatch (based on multiple argument types). Also called message passing.
- **Open Recursion**: Methods can call other methods on the same object via `this`/`self`, enabling late binding where a superclass method invokes a subclass override.
- **Composition over Inheritance**: Building objects by containing other objects ("has-a") rather than extending parent classes ("is-a"). Endorsed by Go, and widely recommended as less brittle than deep hierarchies.
- **Behavioral Subtyping / Liskov Substitution Principle (LSP)**: A subclass instance should be substitutable wherever the superclass is expected. Undecidable in general; the circle-ellipse problem illustrates its difficulty with mutable objects.
- **Object-Relational Impedance Mismatch**: The structural disconnect between OOP objects and relational database tables, addressed by ORM tools but never perfectly solved.

## Commands and Syntax

No CLI commands per se, but key language-level syntax patterns:

- **Class variables** (shared across all instances) vs. **instance variables** (per-object state)
- **Class methods** (operate on class-level data) vs. **instance methods** (operate on instance data)
- **Access modifiers**: `private`, `public`, `protected` (Java/C#), `internal` (C#/Swift/Kotlin); Python uses `_` convention
- **Constructor**: Special method for object creation
- **Abstract class**: Cannot be instantiated directly; serves only as a superclass
- **Utility class**: Contains only static methods/variables; non-instantiable (enforced via private constructor)

## Relationships

- **Simula** (1961-1967): First language with classes, inheritance, dynamic binding — the origin of class-based OOP
- **Smalltalk** (1970s, Xerox PARC): Alan Kay's vision of OOP as message-passing between cell-like objects; introduced multiple inheritance theory and fully dynamic class modification
- **C++**: Stroustrup built it on Simula experience; class-based, static typing
- **Prototype-based OOP**: JavaScript is the dominant example — single prototype chain, no classes at the language's core (classes are syntactic sugar)
- **Functional Programming**: Contrasting paradigm — names actions before things, vs. OOP naming things before actions (Yegge's critique)
- **Relational Databases**: Fundamental tension with OOP (impedance mismatch); bridged by ORM (ActiveRecord, JPA, etc.) or object databases
- **SOLID Principles**: Design guidelines for OOP; includes Open/Closed Principle and LSP
- **Gang of Four Design Patterns**: 23 canonical patterns organized as Creational (5), Structural (7), Behavioral (11)
- **Design by Contract** (Eiffel/Meyer): OOP quality approach using preconditions, postconditions, and invariants

## Exam-Relevant Points

- **Simula** is generally accepted as the first OOP language; **Alan Kay** coined "object-oriented programming" (1967) and created Smalltalk
- **Three pillars of OOP**: Encapsulation, Inheritance, Polymorphism — but the exact feature set defining OOP is contested
- **Liskov Substitution Principle**: Subclass objects must be substitutable for superclass objects; violated by the circle-ellipse problem; undecidable in general
- **Prototype-based vs. Class-based**: JavaScript uses prototype chains (single prototype link up to null); Self allows multiple or no parents
- **Gang of Four**: 5 Creational, 7 Structural, 11 Behavioral patterns (23 total) from the 1994 book
- **God Object** is an anti-pattern (object that knows/does too much)
- **Composition over inheritance**: Preferred by Go (no inheritance support) and widely recommended; uses "has-a" rather than "is-a"
- **Dynamic dispatch**: Runtime method selection; **multiple dispatch** considers types of multiple arguments
- **Open/Closed Principle**: Classes should be open for extension, closed for modification — but Cardelli argues OOP has poor modularity for class extension
- **Joe Armstrong's critique**: "You wanted a banana but got a gorilla holding the banana and the entire jungle" — OOP carries implicit environment
- **Object-relational impedance mismatch**: Fundamental problem when mapping OOP objects to relational tables; ORM is the most common (imperfect) solution
- **Responsibility-driven design** (classes around behavior/contracts) vs. **data-driven design** (classes around data structure) are two competing OOP design approaches
