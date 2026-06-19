---
source: https://en.wikipedia.org/wiki/Dependency_inversion_principle
fetched: 2026-06-17
---

# Dependency Inversion Principle

In object-oriented design, the **dependency inversion principle** is a specific methodology for loosely coupled software modules. When this principle is applied, conventional dependency relationships from high-level, policy-setting modules to low-level, dependency modules get reversed, making high-level modules independent of low-level implementation details. The principle states:

1. "High-level modules should not import anything from low-level modules. Both should depend on abstractions (e.g., interfaces)."
2. "Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions."

By requiring that *both* high-level and low-level objects depend on the same abstraction, this principle *inverts* how many people think about object-oriented programming.

The core idea is that when designing interaction between a high-level and low-level module, one should conceptualize it as an abstract interaction. This affects the design of both modules: the low-level one should be crafted with the interaction in mind, and its usage interface may need to change.

## Traditional Layers Pattern

In conventional application architecture, lower-level components (e.g., Utility Layer) are designed to be consumed by higher-level components (e.g., Policy Layer), enabling highly composite systems. Higher-level components depend directly on lower-level ones, which limits the reuse opportunities for those higher-level components.

The dependency inversion pattern's goal is to avoid this tightly coupled distribution by mediating through an abstract layer, increasing reusability of higher and policy layers.

## Dependency Inversion Pattern

By introducing an abstract layer, both high- and lower-level layers reduce traditional top-to-bottom dependencies. Importantly, "inversion" does not mean lower-level layers *directly* depend on higher-level layers. Instead, *both* layers depend on abstractions (interfaces) that expose behavior needed by the higher-level layers.

In a direct application of dependency inversion, the abstracts are owned by the higher/policy layers. This architecture groups higher/policy components and the abstractions defining lower services into the same package. Lower-level layers are then created through inheritance or implementation of those abstract classes or interfaces.

This inversion of dependencies and ownership encourages reuse of higher and policy layers. Upper layers can use alternative implementations of lower services. When lower-level components are closed or existing services need reuse, an **Adapter** commonly mediates between services and abstractions.

## Dependency Inversion Pattern Generalization

In many projects, the principle and pattern are treated as a single concept applied to all inter-module interfaces. Two common reasons:

1. It's simpler to treat a design principle as a coding pattern. Once an abstract class or interface is coded, a programmer may feel the abstraction work is done.
2. Many unit testing tools rely on inheritance for mocking, so generic interfaces between classes became standard practice.

If the mocking tool depends solely on inheritance, widespread application of the pattern may be necessary. This carries major drawbacks:

1. Merely wrapping a class in an interface doesn't reduce coupling -- only thoughtful abstraction of interactions achieves that.
2. Generic interfaces everywhere make a project harder to understand and maintain.
3. Interface generalization demands more plumbing code, especially factories that typically rely on dependency-injection frameworks.
4. It also restricts programming language usage.

### Generalization Restrictions

Using interfaces for DIP has further design implications in object-oriented programs:

- All member variables in a class must be interfaces or abstracts.
- All concrete class packages must connect only through interface or abstract class packages.
- No class should derive from a concrete class.
- No method should override an implemented method.
- All variable instantiation requires a creational pattern (factory method, factory pattern) or a dependency-injection framework.

## Implementations

Two common DIP implementations share similar logical architecture but differ in implications.

**Direct implementation** packages policy classes with service abstract classes in one library. The low-level component implementing that interface must depend on the high-level component's package for compilation, thereby inverting the conventional dependency.

**A more flexible solution** extracts abstract components into an independent set of packages/libraries. Separating each layer into its own package encourages reuse of any layer, providing robustness and mobility.

## Examples

### Genealogical Module

A genealogical system might represent relationships as a graph of direct relationships (father-son, mother-daughter, husband-wife, etc.). Higher-level modules may need simpler browsing: children, parents, siblings, grandparents, cousins, etc.

Depending on usage, presenting common relationships as distinct direct properties (hiding the underlying graph) lightens coupling between a higher-level module and the genealogical module. This allows changing the internal representation without affecting consuming modules.

### Remote File Server Client

A remote file server client (FTP, cloud storage, etc.) can be modeled as abstract interfaces for connection management, folder operations, file operations, searching, conflict resolution, and history management.

If local and remote files offer the same abstract interfaces, high-level modules applying DIP can use them interchangeably with full transparency.

### Model-View-Controller

In the MVC example, UI and ApplicationLayer packages contain mainly concrete classes, while Controllers contains abstract/interface types. Concrete types Page and CustomerHandler both depend on ICustomerHandler, not on each other. Since UI doesn't reference ApplicationLayer, the concrete CustomerHandler can be replaced without changing the UI class.

## Related Patterns

- **Adapter pattern**: the high-level class defines its own adapter interface as the abstraction
- **Plugin**, **Service Locator**, and **Dependency Injection**: facilitate run-time provisioning of implementations

## History

The dependency inversion principle was postulated by **Robert C. Martin** and described in several publications, including the paper *Object Oriented Design Quality Metrics: an analysis of dependencies* (October 1994), an article in the *C++ Report* in June 1996 titled *The Dependency Inversion Principle*, and the books *Agile Software Development, Principles, Patterns, and Practices* and *Agile Principles, Patterns, and Practices in C#*.

## See Also

- Adapter pattern
- Dependency injection
- Design by contract
- Interface
- Inversion of control
- Service locator pattern
- SOLID

## References

1. Martin, Robert C. (2003). *Agile Software Development, Principles, Patterns, and Practices*. Prentice Hall. pp. 127-131. ISBN 978-0135974445.
2. Freeman, Eric; Freeman, Elisabeth; Kathy, Sierra; Bert, Bates (2004). *Head First Design Patterns*. O'Reilly. ISBN 978-0-596-00712-6.
3. Martin, Robert C. (October 1994). "Object Oriented Design Quality Metrics: An analysis of dependencies" (PDF).
4. Martin, Robert C. (June 1996). "The Dependency Inversion Principle." *C++ Report*, Vol. 8, No. 6, pp. 61-66. ISSN 1040-6042.
