---
source: sources/wiki-Behavioral_pattern.md
source_url: https://en.wikipedia.org/wiki/Behavioral_pattern
---

## Behavioral Design Patterns — Catalog and Classification

Behavioral patterns are software design patterns that focus on communication and collaboration between objects. They define how objects interact, distribute responsibility, and manage control flow, distinguishing them from creational patterns (object construction) and structural patterns (object composition).

## Key Concepts

- **Behavioral patterns govern object collaboration** — they define protocols for how objects communicate and delegate responsibilities at runtime
- **Gang of Four (GoF) behavioral patterns** — the canonical set: Chain of Responsibility, Command, Interpreter, Iterator, Mediator, Memento, Observer, State, Strategy, Template Method, Visitor
- **Additional behavioral patterns** beyond GoF: Blackboard, Null Object, Specification, Publish–Subscribe, Protocol Stack, Scheduled-Task, Single-Serving Visitor
- **Externalize the Stack** — technique to convert recursive functions into iterative ones using an explicit stack; classified as behavioral
- **Observer pattern variant** — the **Weak Reference pattern** decouples observer from observable to prevent memory leaks in environments lacking automatic weak references
- **Publish–Subscribe** extends Observer to distributed systems — decouples senders and receivers via message topics and brokers, supporting asynchronous many-to-many communication
- **Strategy vs. Template Method** — both allow algorithm selection at runtime, but Strategy uses composition while Template Method uses inheritance
- **State pattern** — allows an object to partially change its type at runtime, providing a clean alternative to conditional logic based on state
- **Specification pattern** — enables recombinable business logic using boolean algebra (AND, OR, NOT composition)

## Commands and Syntax

No commands — this is a classification/catalog page. Patterns are referenced individually for implementation details.

## Relationships

- **Sibling categories**: Creational patterns (object construction), Structural patterns (object composition), Concurrency patterns (multi-threaded coordination)
- **Strategy vs. Template Method**: Both solve algorithm-selection but via different mechanisms (composition vs. inheritance) — a classic OO design tradeoff
- **Observer vs. Publish–Subscribe**: Pub/Sub generalizes Observer for distributed, asynchronous, many-to-many contexts with broker intermediaries
- **Chain of Responsibility vs. Command**: Both involve command objects, but CoR routes them through a chain of handlers while Command encapsulates actions directly
- **Mediator vs. Observer**: Mediator centralizes communication through a single coordinator; Observer distributes notification directly from subject to dependents
- **Visitor and Single-Serving Visitor**: SSV is an optimization of Visitor for one-time-use traversal scenarios
- **Scheduled-Task pattern** bridges into real-time computing and concurrency concerns

## Exam-Relevant Points

- Know the **11 GoF behavioral patterns** by name: Chain of Responsibility, Command, Interpreter, Iterator, Mediator, Memento, Observer, State, Strategy, Template Method, Visitor
- **Strategy uses composition; Template Method uses inheritance** — this distinction is frequently tested
- **Observer** defines a **one-to-many** dependency; Publish–Subscribe supports **many-to-many**
- **Memento** provides **rollback/undo** capability by capturing and restoring object state
- **Iterator** accesses elements sequentially **without exposing underlying representation**
- **State pattern** allows partial runtime type change — distinguish from Strategy (which selects algorithms, not object behavior modes)
- **Null Object** acts as a **default value**, eliminating null checks — behavioral, not structural
- **Specification pattern** combines business rules using **boolean composition** (AND, OR, NOT)
- Behavioral patterns are one of **three GoF categories** (Creational, Structural, Behavioral)
