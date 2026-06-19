---
source: https://en.wikipedia.org/wiki/Interface_segregation_principle
fetched: 2026-06-17
---

# Interface Segregation Principle

The **interface segregation principle (ISP)** is a principle in software engineering stating that "no code should be forced to depend on methods it does not use." It is one of the five SOLID principles of object-oriented design.

## Core Concept

ISP advocates splitting large interfaces into smaller, more specific ones so that clients only need to know about relevant methods. These narrower interfaces are also called **role interfaces**. The principle aims to keep systems decoupled, making them easier to refactor, change, and redeploy.

Beyond OO design, ISP also serves as a key principle in distributed systems and is one of the six IDEALS principles for microservice design.

## Importance in Object-Oriented Design

Interfaces provide abstraction layers that simplify code and prevent coupling to dependencies. Without proper interface design, a system can become so tightly coupled across multiple levels that changing one part forces numerous additional changes throughout the codebase. Using interfaces or abstract classes helps prevent this cascading effect.

## Origin

The principle was first formulated by **Robert C. Martin** while consulting for **Xerox**. Xerox had built a new printer system capable of tasks like stapling and faxing. As the software grew, modifications became increasingly difficult -- even small changes required lengthy redeployment cycles, making development nearly impossible.

The root cause was a single **Job class** used by almost all tasks. Print jobs, staple jobs, and others all depended on this one "fat" class containing methods for every client type. A staple job, for instance, was exposed to all print job methods despite having no use for them.

Martin's solution introduced an interface layer between the Job class and its clients, applying the Dependency Inversion Principle. Rather than one monolithic Job class, separate interfaces (e.g., Staple Job interface, Print Job interface) were created for each job type. The respective Staple or Print classes used only their relevant interface, while the Job class implemented all of them.

## Typical Violation

A well-known example of ISP violation appears in Martin's book *Agile Software Development: Principles, Patterns, and Practices* -- the **ATM Transaction example**. It illustrates a User Interface for an ATM that handles all request types (deposits, withdrawals, etc.) through a single interface, demonstrating the need to segregate it into individual, more specific interfaces.

## Relationship to Other Principles

- **SOLID** -- ISP is the "I" in SOLID
- **High Cohesion Principle** of GRASP -- ISP is described as similar to this principle
- **Dependency Inversion Principle** -- used in conjunction with ISP in the original Xerox solution

## References

1. Martin, Robert C. (2002). *Agile Software Development: Principles, Patterns, and Practices*. Pearson Education.
2. Fowler, Martin. "Role Interfaces."
3. Martin, Robert C. (1996). "Interface Segregation Principle." *C++ Report*.
4. Merson, Paulo (2021). "IDEALS principles for microservice design." *The InfoQ eMag*, Issue #91.
