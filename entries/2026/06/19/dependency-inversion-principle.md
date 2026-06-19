---
source: sources/dependency-inversion-principle.md
source_url: https://en.wikipedia.org/wiki/Dependency_inversion_principle
---

## Dependency Inversion Principle (DIP)

The Dependency Inversion Principle is one of the five SOLID principles of object-oriented design, postulated by Robert C. Martin. It prescribes that high-level modules and low-level modules should both depend on abstractions rather than on each other, reversing the conventional top-down dependency direction found in layered architectures. The goal is loose coupling, increased reusability of policy/high-level layers, and the ability to swap low-level implementations without affecting higher-level code.

## Key Concepts

- **Two formal statements**: (1) High-level modules should not import from low-level modules; both should depend on abstractions. (2) Abstractions should not depend on details; details should depend on abstractions.
- **"Inversion" meaning**: It does not mean low-level depends on high-level directly. It means both depend on a shared abstraction layer, inverting the traditional top-down dependency chain.
- **Ownership of abstractions**: In direct DIP application, the abstractions are owned by the higher/policy layer, not the lower layer. The lower layer implements interfaces defined by the higher layer.
- **Traditional layers problem**: In conventional architecture, higher-level components depend directly on lower-level ones, creating tight coupling and limiting reuse of higher-level components.
- **Abstract layer mediation**: Introducing an abstract layer between high and low levels reduces coupling and enables substitution of low-level implementations.
- **Adapter for existing services**: When lower-level components are closed or existing services must be reused, an Adapter mediates between the service and the abstraction.

## Generalization Pitfalls

- Wrapping every class in an interface does not automatically reduce coupling — only thoughtful abstraction of interactions achieves that.
- Over-generalized interfaces make projects harder to understand and maintain.
- Excessive interface usage demands more plumbing code (factories, DI frameworks).
- Strict generalization rules (all members must be interfaces, no deriving from concrete classes, no overriding implemented methods) are sometimes applied but carry significant overhead.

## Two Implementation Strategies

- **Direct implementation**: Policy classes and service abstract classes packaged together in one library. Low-level components depend on the high-level package for compilation, inverting the conventional dependency direction.
- **Separated abstractions**: Abstract components extracted into independent packages/libraries. Each layer in its own package promotes reuse, robustness, and mobility. This is the more flexible approach.

## Commands and Syntax

No specific commands — DIP is a design principle. Typical code-level application:

```
// Abstraction owned by the high-level layer
interface IRepository {
    save(entity: Entity): void;
    find(id: string): Entity;
}

// High-level module depends on abstraction
class OrderService {
    constructor(private repo: IRepository) {}
}

// Low-level module implements the abstraction
class SqlRepository implements IRepository {
    save(entity: Entity): void { /* SQL logic */ }
    find(id: string): Entity { /* SQL logic */ }
}
```

Key structural rule: the interface `IRepository` lives in the same package as `OrderService`, not with `SqlRepository`.

## Relationships

- **SOLID**: DIP is the "D" in SOLID, alongside SRP, OCP, LSP, and ISP.
- **Dependency Injection**: A runtime mechanism for providing implementations that satisfy DIP abstractions. DI is how you wire up DIP-compliant code.
- **Inversion of Control (IoC)**: Broader principle; DIP is a specific manifestation of IoC applied to module dependencies.
- **Adapter Pattern**: Used when existing services don't match the abstraction — the adapter bridges them.
- **Factory Method / Abstract Factory**: Creational patterns needed when strict DIP requires that no class directly instantiate concrete dependencies.
- **Service Locator**: Alternative to DI for runtime provisioning of implementations.
- **Interface Segregation Principle (ISP)**: Complements DIP — ISP ensures the abstractions clients depend on are minimal and focused.
- **Open/Closed Principle (OCP)**: DIP supports OCP by allowing extension through new implementations without modifying high-level modules.

## Exam-Relevant Points

- **Know both formal statements verbatim** — exams frequently test the precise wording, especially the distinction between "high-level should not depend on low-level" and "abstractions should not depend on details."
- **Abstractions are owned by the high-level layer**, not the low-level layer. This is the most commonly misunderstood aspect.
- **DIP does not mean low-level depends on high-level** — both depend on abstractions.
- **Distinguish DIP (principle) from DI (pattern)**: DIP states what the dependency structure should look like; DI is a technique for achieving it at runtime.
- **Two implementation approaches**: direct (abstractions co-packaged with policy layer) vs. separated (abstractions in independent packages). Know the tradeoffs — direct inverts compilation dependency; separated maximizes reuse.
- **Over-application warning**: Blindly wrapping every class in an interface does not reduce coupling. Thoughtful abstraction of interactions is required.
- **Robert C. Martin** originated the principle (1994 paper, 1996 C++ Report article, later books).
- **MVC as DIP example**: UI and ApplicationLayer contain concrete classes; Controllers contains abstractions. Both concrete layers depend on the controller abstractions, not on each other.
