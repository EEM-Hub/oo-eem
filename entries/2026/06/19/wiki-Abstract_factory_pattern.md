---
source: sources/wiki-Abstract_factory_pattern.md
source_url: https://en.wikipedia.org/wiki/Abstract_factory_pattern
---

## Abstract Factory Pattern

The Abstract Factory pattern is a creational design pattern from the Gang of Four (GoF) catalog that provides an interface for creating families of related or dependent objects without specifying their concrete classes. It encapsulates a group of individual factories under a common abstract interface, allowing client code to create objects through that interface without knowing the concrete types being instantiated. This decouples object creation from object usage, enabling runtime substitution of entire product families.

## Key Concepts

- **Core definition**: "An interface for creating families of related or dependent objects without specifying their concrete classes" (GoF, 1994)
- **Client isolation**: The client never knows the concrete type of the objects it receives — it works exclusively through abstract interfaces
- **Family coherence**: All products created by a single concrete factory share a common theme or variant (e.g., `FancyLetter` + `FancyResume` both come from `FancyDocumentCreator`)
- **Object composition over inheritance**: Object creation is implemented in factory methods exposed through the factory interface, relying on composition rather than class-level instantiation
- **Runtime swappability**: Concrete factory implementations can be exchanged at runtime without changing client code
- **Encapsulated construction**: A "factory" is the location in code where concrete objects are actually constructed — this location is isolated from the client
- **The factory returns abstract references**: Returns a pointer or reference to an abstract type, never the concrete type
- **Adding new concrete types** requires modifying only which factory is used — typically one line in one file — rather than changing every instantiation site
- **Trade-offs**: Can introduce unnecessary complexity, extra boilerplate, and systems that are harder to debug and maintain

## Commands and Syntax

**Structural participants:**
- `AbstractFactory` — declares the interface for creating abstract product objects
- `ConcreteFactory` (e.g., `Factory1`) — implements creation operations for concrete products
- `AbstractProduct` (e.g., `ProductA`, `ProductB`) — declares the interface for a product type
- `ConcreteProduct` (e.g., `ProductA1`, `ProductB1`) — the actual object created by the concrete factory
- `Client` — uses only the `AbstractFactory` and `AbstractProduct` interfaces

**Typical method signatures (from the MazeFactory example):**
```cpp
unique_ptr<Maze> makeMaze() const;
shared_ptr<Room> makeRoom(int n) const;
shared_ptr<Wall> makeWall() const;
shared_ptr<Door> makeDoor(shared_ptr<Room> r1, shared_ptr<Room> r2) const;
```

**Usage pattern:**
```cpp
unique_ptr<Maze> createMaze(MazeFactory& factory) {
    auto maze = factory.makeMaze();
    auto r1 = factory.makeRoom(1);
    auto r2 = factory.makeRoom(2);
    auto door = factory.makeDoor(r1, r2);
    // ... configure and return
}
```

The client (`MazeGame`) receives the factory as a parameter. To change the family of objects created, pass a different `MazeFactory` subclass — no other code changes required.

**Two structural variants:**
1. **Classic (1994)**: Abstract classes + inheritance for both factories and products
2. **Modern**: Interfaces/protocols for factories and products; concrete classes implement rather than inherit

## Relationships

- **Factory Method pattern**: Abstract Factory is often implemented using Factory Methods internally; Factory Method creates a single product, Abstract Factory creates families of products
- **Singleton pattern**: Abstract factories are often implemented as singletons — a single global factory object through which all client code routes creation requests
- **Builder pattern**: Both are creational, but Builder constructs complex objects step-by-step while Abstract Factory creates families of related objects in one call per product
- **Concrete class**: The concrete products and concrete factories are the implementation side that clients never see
- **Object creation**: Abstract Factory is one of several patterns addressing the general problem of flexible object creation
- **Software design patterns**: One of 23 GoF patterns; one of five creational patterns alongside Builder, Factory Method, Prototype, and Singleton

## Exam-Relevant Points

- Abstract Factory is a **creational** pattern — one of five in the GoF catalog
- The defining intent is creating **families** of related objects — not just single objects (that's Factory Method)
- Client code depends only on **abstract interfaces**, never on concrete classes
- The pattern relies on **object composition**, not inheritance of the client class
- Changing the product family requires changing only **which factory is instantiated** — typically one line
- The factory returns **abstract type references/pointers**, never concrete types
- Key problems it solves: (1) application independence from object creation, (2) class independence from required object creation, (3) creation of families of related/dependent objects
- **Trade-off**: Enables runtime flexibility and interchangeability at the cost of additional complexity and indirection
- Modern variant uses **interfaces** instead of abstract classes, avoiding inheritance for defining the factory and product contracts
- The pattern **insulates** client code from changes to products or how they are created, even across objects derived from very different abstract interfaces
