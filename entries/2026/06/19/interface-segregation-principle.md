---
source: sources/interface-segregation-principle.md
source_url: https://en.wikipedia.org/wiki/Interface_segregation_principle
---

## Interface Segregation Principle (ISP)

The Interface Segregation Principle states that no code should be forced to depend on methods it does not use. It is the "I" in SOLID and was formulated by Robert C. Martin during consulting work at Xerox. ISP guides designers to split large, "fat" interfaces into smaller role interfaces so that each client depends only on the methods it actually needs.

## Key Concepts

- **Core rule**: No client should be forced to depend on methods it does not use.
- **Role interfaces**: The smaller, more specific interfaces that result from applying ISP. Each captures a single role or capability rather than bundling all operations together.
- **Fat class / fat interface**: An interface or class that serves multiple unrelated clients, exposing every method to every consumer regardless of relevance. This is the primary anti-pattern ISP corrects.
- **Decoupling effect**: Segregated interfaces keep systems loosely coupled, making refactoring, change, and redeployment easier.
- **Cascading change problem**: Without ISP, modifying one part of a tightly coupled system forces changes throughout the codebase.
- **Applicability beyond OOP**: ISP is also one of the six IDEALS principles for microservice design, making it relevant to distributed systems architecture.

## Commands and Syntax

No CLI commands. The principle is applied through design decisions:

- **Identify** a large interface that serves multiple client types.
- **Group** methods by which client actually uses them.
- **Extract** each group into a separate, narrowly-scoped interface (role interface).
- **Have the implementation class implement all** the segregated interfaces.
- **Have each client depend only on** the interface relevant to its needs.

**Xerox example pattern**:
```
Before:  StapleJob --> Job (fat class with print, staple, fax methods)
After:   StapleJob --> IStapleJob (only staple methods)
         PrintJob  --> IPrintJob  (only print methods)
         Job implements IStapleJob, IPrintJob, IFaxJob
```

## Relationships

- **Dependency Inversion Principle (DIP)**: ISP and DIP were applied together in the original Xerox solution. DIP introduced the interface layer; ISP determined how to split it. The two principles are complementary — DIP says depend on abstractions, ISP says make those abstractions narrow.
- **Single Responsibility Principle (SRP)**: SRP applies to classes (one reason to change), ISP applies to interfaces (one client role). A fat interface often signals SRP violations in the abstraction layer.
- **High Cohesion (GRASP)**: ISP is described as similar to GRASP's High Cohesion principle — both aim to keep related responsibilities together and unrelated ones apart.
- **IDEALS (microservices)**: ISP appears as a design principle for microservice APIs, where service contracts should expose only what each consumer needs.

## Exam-Relevant Points

- ISP is the "I" in SOLID — know the acronym placement.
- Originated from Robert C. Martin's work at Xerox on a printer system with a monolithic Job class.
- The canonical violation example is the **ATM Transaction** UI from Martin's *Agile Software Development* book.
- The solution pattern: introduce multiple narrow interfaces, have the concrete class implement all of them, have each client depend on only its relevant interface.
- ISP prevents the **forced recompilation/redeployment** problem — when a fat interface changes, all clients must be rebuilt even if the change is irrelevant to them.
- Distinguish ISP from SRP: SRP is about class responsibilities, ISP is about what interfaces expose to their clients.
- ISP extends beyond OOP into microservice design (IDEALS principles).
