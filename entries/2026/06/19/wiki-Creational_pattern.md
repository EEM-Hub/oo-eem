---
source: sources/wiki-Creational_pattern.md
source_url: https://en.wikipedia.org/wiki/Creational_pattern
---

## Creational Design Patterns

Creational patterns are a category of software design patterns that deal with object creation mechanisms. They abstract the instantiation process, making a system independent of how its objects are created, composed, and represented. They encapsulate two things: knowledge of which concrete classes the system uses, and how instances of those classes are created and combined.

## Key Concepts

- **Two subcategories**: Object-creational patterns (defer creation to another object) and class-creational patterns (defer creation to subclasses)
- **Core encapsulation goals**: Hide which concrete classes are used; hide how instances are created and combined
- **Flexibility over hard-coding**: Creational patterns replace hard-coded object creation with flexible, composable mechanisms that promote reuse and reduce coupling
- **Favor composition over inheritance**: Modern software engineering emphasizes composing small behaviors rather than inheriting large ones; creational patterns support this shift
- **Basic structure**: A **Creator** declares the object interface and returns objects; a **ConcreteCreator** implements the object's interface

## When to Apply

- A system should be independent of how its products are created
- A set of related objects is designed to be used together
- Class library implementations must be hidden, exposing only interfaces
- Different representations of complex objects must be constructable
- A class wants its subclass to determine the object it creates
- Class instantiation is specified at run-time
- Only a single instance must exist (Singleton)
- Instances should be extensible without modification

## The Creational Patterns

- **Abstract Factory** — Request objects from a factory rather than creating them directly
- **Factory Method** — Centralize creation of a specific type, choosing among several implementations
- **Builder** — Separate construction of a complex object from its representation so the same process can create different representations
- **Prototype** — Clone a prototypical instance to produce new objects when the type is determined at runtime
- **Singleton** — Restrict instantiation of a class to exactly one object
- **Dependency Injection** — Accept required objects from an injector rather than creating them directly
- **Lazy Initialization** — Delay creation of an object or calculation of a value until first needed
- **Object Pool** — Recycle objects no longer in use to avoid expensive acquisition and release of resources

## Relationships

- One of three main categories alongside **Structural Patterns** (composition of classes/objects) and **Behavioral Patterns** (communication between objects)
- Closely related to **Constructors** in OO languages — creational patterns extend or replace direct constructor calls
- **Concurrency Patterns** form a separate, orthogonal category
- Factory Method and Abstract Factory are the most commonly combined creational patterns (a factory often uses factory methods internally)
- Builder and Prototype can serve as alternatives when object construction is complex
- Dependency Injection is related to but distinct from Factory patterns — it inverts the direction of dependency resolution

## Exam-Relevant Points

- Know the two subcategories: **object-creational** (delegates to another object) vs. **class-creational** (delegates to subclasses)
- Factory Method is class-creational; Abstract Factory, Builder, Prototype, and Singleton are object-creational
- The GoF book (Gamma, Helm, Johnson, Vlissides 1995) defines five canonical creational patterns: Abstract Factory, Builder, Factory Method, Prototype, Singleton
- Lazy Initialization, Object Pool, and Dependency Injection are commonly listed creational patterns but are **not** part of the original GoF catalog
- Key motivation: remove explicit references to concrete classes from code that instantiates them — create independence for objects and classes
- Creational patterns increase flexibility in **what** gets created, **who** creates it, **how** it gets created, and **when** creation happens
