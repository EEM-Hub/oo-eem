---
source: https://en.wikipedia.org/wiki/SOLID
fetched: 2026-06-17
---

# SOLID

## Overview

SOLID is a mnemonic acronym used in object-oriented programming and functional programming, representing five design principles that aim to make source code more understandable, flexible, and maintainable. These principles also underpin methodologies like agile and adaptive software development.

Robert C. Martin introduced the foundational concepts in his 2000 paper *Design Principles and Design Patterns*, which addressed software rot. The acronym itself was coined around 2004 by Michael Feathers.

## Principles

### Single Responsibility Principle (SRP)

This principle holds that "there should never be more than one reason for a class to change." Each class should focus on a single responsibility. Benefits include improved maintainability, easier unit testing, and the ability to modify one responsibility without affecting unrelated system components.

### Open-Closed Principle (OCP)

Under OCP, "software entities should be open for extension, but closed for modification." This supports extensibility (adding features without altering existing code), stability (lower risk of introducing bugs), and adaptability to evolving requirements.

### Liskov Substitution Principle (LSP)

LSP requires that "functions that use pointers or references to base classes must be able to use" those of derived classes seamlessly. This enables polymorphic behavior, ensures subclasses honor the superclass contract, and guarantees that substituting a subclass object won't break program behavior. It is related to design by contract.

### Interface Segregation Principle (ISP)

ISP states that "clients should not be forced to depend upon interface methods that they do not use." This promotes decoupling between classes, allows more targeted interface implementations, and prevents unnecessary dependencies.

### Dependency Inversion Principle (DIP)

DIP asserts that "one should depend upon abstractions, not concretes." This fosters loose coupling between modules, enables implementation changes without affecting clients, and improves overall maintainability.

## Key People & Sources

- **Robert C. Martin** ("Uncle Bob") -- software engineer and instructor who articulated the core principles in his 2000 paper and further elaborated them in *Agile Software Development, Principles, Patterns, and Practices* (2003) and *Clean Architecture* (2018).
- **Michael Feathers** -- credited with coining the SOLID acronym circa 2004.
- **Sandi Metz** -- gave a 2009 talk titled "SOLID Object-Oriented Design" at the Gotham Ruby Conference.

## See Also

- Code reuse
- GRASP (object-oriented design)
- Inheritance (object-oriented programming)
- List of software development philosophies

## References

1. Metz, Sandi (May 2009). "SOLID Object-Oriented Design." Talk at the 2009 Gotham Ruby Conference (YouTube).
2. Martin, Robert C. "Principles Of OOD." ButUncleBob.com (dates to at least 2003).
3. Martin, Robert C. (13 Feb 2009). "Getting a SOLID start." Uncle Bob Consulting LLC.
4. Martin, Robert C. (2000). "Design Principles and Design Patterns." objectmentor.com (PDF).
5. Martin, Robert (2018). *Clean Architecture*, Pearson, p. 58. ISBN 978-0-13-449416-6.
6. "Single Responsibility Principle." objectmentor.com (PDF).
7. Martin, Robert C. (2003). *Agile Software Development, Principles, Patterns, and Practices*, Prentice Hall, p. 95. ISBN 978-0135974445.
8. "Open/Closed Principle." objectmentor.com (PDF).
9. "Liskov Substitution Principle." objectmentor.com (PDF).
10. "Interface Segregation Principle." objectmentor.com, 1996 (PDF).
11. "Dependency Inversion Principle." objectmentor.com (PDF).
