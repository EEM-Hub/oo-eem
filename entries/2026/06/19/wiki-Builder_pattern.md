---
source: sources/wiki-Builder_pattern.md
source_url: https://en.wikipedia.org/wiki/Builder_pattern
---

## Builder Pattern (Creational)

The Builder pattern separates the construction of a complex object from its representation, allowing the same construction process to create different representations. It is one of the 23 GoF design patterns, classified as a creational pattern. It solves the problem of a class needing to create different representations of a complex object without being committed to a particular one.

## Key Concepts

- **Core intent**: Separate construction of a complex object from its representation so the same process can create different representations
- **Problem it solves**: Creating and assembling parts of a complex object directly within a class is inflexible — it locks the class to one representation and prevents changing it independently
- **Solution**: Encapsulate creating and assembling parts in a separate `Builder` object; the class delegates to the Builder instead of constructing directly
- **Four participants**:
  - **Director** — orchestrates the construction steps using the Builder interface
  - **Builder** (abstract interface) — declares the interface for creating parts of the product
  - **ConcreteBuilder** — implements the Builder interface; constructs and assembles the product's parts
  - **Product** — the complex object being constructed

## Commands and Syntax

The pattern follows this structural flow:

1. Client creates a ConcreteBuilder and passes it to the Director
2. Director calls build methods on the Builder interface in a defined sequence
3. Client retrieves the finished product from the Builder

```
// Pseudocode structure
Director director = new Director(new ConcreteBuilder());
director.Construct();        // Director drives step-by-step construction
Product result = director.GetResult();
```

Key methods in the Builder interface typically include `buildPartA()`, `buildPartB()`, and `getResult()`.

## Relationships

- **Creational pattern family**: Sits alongside Abstract Factory, Factory Method, Prototype, and Singleton
- **vs. Abstract Factory**: Abstract Factory creates families of related objects; Builder constructs one complex object step-by-step
- **vs. Factory Method**: Factory Method uses inheritance (subclass decides); Builder uses composition (Director delegates to a Builder object)
- **Separation of Concerns**: The pattern is a direct application of this principle — construction logic is separated from representation logic
- **Related to Currying**: Both involve incremental construction/configuration before producing a final result
- **Complements Composite**: Builders are often used to construct Composite trees

## Exam-Relevant Points

- Builder is a **creational** pattern from the GoF book (Gamma, Helm, Johnson, Vlissides, 1994, p. 97)
- The **Director** does not create products directly — it uses the Builder interface, making it independent of concrete classes
- A **distinct ConcreteBuilder** is required for each type of product — this is a key disadvantage
- **Advantages**: variation in internal representation, encapsulation of construction/representation code, control over construction steps
- **Disadvantages**: one ConcreteBuilder per product type, builders must be mutable, may complicate dependency injection, can defer compile-time errors to runtime in null-safe languages
- The Director controls the **stepwise** creation process — the order of construction steps matters
- The Client retrieves the result from the **Builder** (not from the Director in the classic formulation, though some implementations route it through the Director)
