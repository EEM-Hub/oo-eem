---
source: sources/wiki-Structural_pattern.md
source_url: https://en.wikipedia.org/wiki/Structural_pattern
---

## Structural Design Patterns

Structural patterns are a category of software design patterns that deal with how classes and objects are composed to form larger structures. They focus on encapsulating and managing relationships between entities, simplifying interfaces, and ensuring that components work together efficiently.

## Key Concepts

- **Structural patterns** are one of three main GoF pattern categories (alongside Creational and Behavioral)
- They address **composition of classes and objects** — how entities relate to and connect with each other
- Core concern: making independently developed components work together by managing interfaces, hierarchies, and object composition
- The GoF defines **seven** canonical structural patterns: Adapter, Bridge, Composite, Decorator, Facade, Flyweight, Proxy
- Additional structural patterns beyond GoF include: Aggregate, Extensibility, Marker Interface, Pipes and Filters, Opaque Pointer

## Commands and Syntax

Not applicable — this is a pattern catalog topic. Implementation varies by language. Each individual pattern has its own class/interface structure.

## Relationships

- **Adapter** — converts one interface to another; related variant **Retrofit Interface Pattern** adapts a new interface for multiple classes simultaneously
- **Adapter Pipeline** — chains multiple adapters, useful for debugging
- **Aggregate** — a specialization of Composite that adds aggregation methods over children
- **Bridge** — decouples abstraction from implementation so both vary independently; **Tombstone** is a related intermediate-lookup technique
- **Composite** — tree structure with uniform interface across all nodes
- **Decorator** — adds behavior at runtime without subclass explosion
- **Extensibility (Framework)** — hides complexity behind a simple interface
- **Facade** — simplifies an existing interface for common use cases
- **Flyweight** — shares common state across many objects to save memory
- **Marker Interface** — empty interface used for metadata tagging
- **Pipes and Filters** — linear chain where each stage's output feeds the next
- **Opaque Pointer** — hides implementation behind an undeclared/private type
- **Proxy** — stands in for another object, controlling access
- Sibling categories: **Creational patterns** (object creation), **Behavioral patterns** (object interaction), **Concurrency patterns** (multi-threading)

## Exam-Relevant Points

- Know the **seven GoF structural patterns** by name: Adapter, Bridge, Composite, Decorator, Facade, Flyweight, Proxy
- **Decorator vs. subclassing**: Decorator solves the problem of exponential subclass proliferation by composing behavior at runtime
- **Bridge vs. Adapter**: Bridge is designed up-front to let abstraction and implementation vary independently; Adapter retrofits compatibility after the fact
- **Composite**: all objects in the tree share the same interface — this is the defining characteristic
- **Flyweight** is about **space optimization** through shared state (intrinsic vs. extrinsic state)
- **Facade** simplifies; **Adapter** converts; **Proxy** controls access — know the distinction
- **Aggregate** is a Composite variant — expect questions that test whether you can distinguish them
- Structural patterns sit between Creational (how objects are made) and Behavioral (how objects communicate) — understand where each category's responsibility begins and ends
