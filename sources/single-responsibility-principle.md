---
source: https://en.wikipedia.org/wiki/Single-responsibility_principle
fetched: 2026-06-17
---

# Single-Responsibility Principle

## Definition

The **single-responsibility principle (SRP)** is a programming principle stating that "A module should be responsible to one, and only one, actor." Here, *actor* means a group of stakeholders or users requiring changes to that module.

Robert C. Martin, who originated the term, phrases it as "A class should have only one reason to change." Due to ambiguity around "reason," he later offered an alternative formulation: "Gather together the things that change for the same reasons. Separate those things that change for different reasons." He has also framed the principle in terms of roles or actors -- noting, for instance, that an accountant and a database administrator represent distinct roles even if performed by the same individual. Each module should therefore serve a single role.

## History

Robert C. Martin introduced the term in his article "The Principles of OOD," part of his *Principles of Object Oriented Design*. It gained wider recognition through his 2003 book *Agile Software Development, Principles, Patterns, and Practices*. Martin credited the concept of **cohesion** as a foundation, referencing Tom DeMarco's *Structured Analysis and System Specification* (1979) and Meilir Page-Jones's *The Practical Guide to Structured Systems Design* (1988). In 2014, Martin wrote a blog post to further clarify what he meant by "reason for change."

## Example

Martin defines a responsibility as a *reason to change* and holds that a class or module should have one, and only one, such reason.

Consider a module that both compiles and prints a report. It could change for two distinct reasons: the **content** of the report might change, or the **format** might change. Since these two concerns evolve for different causes and at different times, SRP dictates they belong in **separate classes or modules**. Coupling them together is poor design.

Keeping a class focused on a single concern makes it more robust. If the compilation process changes, having the printing code in the same class creates a greater risk that it will break -- even though it was unrelated to the change.

## See Also

- Chain-of-responsibility pattern
- Coupling (computer programming)
- GRASP (object-oriented design)
- Information hiding
- SOLID
- Separation of concerns

## References

1. Martin, Robert C. (2018). *Clean Architecture: A Craftsman's Guide to Software Structure and Design*. ISBN 978-0-13-449432-6.
2. Martin, Robert C. (2003). *Agile Software Development, Principles, Patterns, and Practices*. Prentice Hall. p. 95. ISBN 978-0135974445.
3. Martin, Robert C. (2014). "The Single Responsibility Principle." *The Clean Code Blog*.
4. Martin, Robert C. (2018). *Clean Architecture*. Prentice Hall. ISBN 978-0-13-449416-6.
5. Martin, Robert C. (2005). "The Principles of OOD." *butunclebob.com*.
6. DeMarco, Tom (1979). *Structured Analysis and System Specification*. Prentice Hall. ISBN 0-13-854380-1.
7. Page-Jones, Meilir (1988). *The Practical Guide to Structured Systems Design*. Yourdon Press Computing Series. p. 82. ISBN 978-8120314825.
