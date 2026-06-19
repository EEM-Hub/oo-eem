---
source: sources/wiki-Software_design_pattern.md
source_url: https://en.wikipedia.org/wiki/Software_design_pattern
---

## Software Design Patterns: Overview and Catalog

A comprehensive reference covering the definition, history, classification, and catalog of software design patterns — reusable solution templates for commonly-needed software behaviors. The page traces patterns from Christopher Alexander's architectural origins through the Gang of Four's seminal 1994 book, and catalogs patterns across four categories: creational, structural, behavioral, and concurrency.

## Key Concepts

- A **design pattern** is a description and template for solving a recurring problem — not rigid code to copy, but a reusable approach adaptable across languages and platforms.
- OO design patterns show relationships between **classes and objects** without specifying concrete implementations.
- Patterns that imply **mutable state** may be unsuited for functional programming languages; some patterns become unnecessary when a language has built-in support for the problem they solve.
- A pattern describes a **design motif** (prototypical micro-architecture) — a set of program constituents and their relationships that a developer adapts to their codebase.
- The **Gang of Four (GoF)** — Gamma, Helm, Johnson, Vlissides — published *Design Patterns: Elements of Reusable Object-Oriented Software* in 1994, establishing the canonical pattern catalog.
- Patterns originated from **Christopher Alexander's** architectural pattern language concept (1977), adapted to software by **Kent Beck** and **Ward Cunningham** at OOPSLA 1987.
- **Four pattern categories**: Creational (object creation), Structural (class/object composition), Behavioral (object collaboration), Concurrency (concurrent processing).

## Commands and Syntax

No commands per se, but the GoF documentation format for a pattern includes these sections:

- **Name** — descriptive and unique identifier
- **Intent** — goal and reason for using the pattern
- **Also Known As** — alternative names
- **Motivation** — scenario with problem and context
- **Applicability** — situations where the pattern is usable
- **Structure** — class diagrams and interaction diagrams
- **Participants** — classes/objects and their roles
- **Collaboration** — how participants interact
- **Consequences** — results, side effects, trade-offs
- **Implementation** — solution description
- **Sample Code** — language-specific illustration
- **Known Uses** — real-world examples
- **Related Patterns** — connections and distinctions from similar patterns

## Relationships

- **Architecture patterns vs. design patterns**: Architecture patterns (e.g., Circuit Breaker) operate at a higher abstraction level, addressing system-level structure; design patterns address class/object-level problems.
- **Architecture styles** (Layered, Microservices, Event-Driven) are even more coarse-grained than architecture patterns.
- **Implementation patterns** (programming idioms) are more fine-grained than design patterns, often language-specific (e.g., RAII, copy-and-swap in C++).
- Connects to **anti-patterns** (commonly recurring poor solutions), **refactoring**, **GRASP principles**, and **pattern languages**.
- Domain-specific patterns extend the concept to UI design, information visualization, secure design, web design, and business model design.
- The **Portland Pattern Repository** (Ward Cunningham) served as a central documentation hub for patterns.

## Exam-Relevant Points

- **Creational patterns** (10 listed): Abstract Factory, Builder, Dependency Injection, Factory Method, Lazy Initialization, Multiton, Object Pool, Prototype, RAII, Singleton.
- **Structural patterns** (14 listed): Adapter/Wrapper/Translator, Bridge, Composite, Decorator, Delegation, Extension Object, Facade, Flyweight, Front Controller, Marker, Module, Proxy, Twin.
- **Behavioral patterns** (17 listed): Chain of Responsibility, Command, Fluent Interface, Interpreter, Iterator, Mediator, Memento, Null Object, Observer/Pub-Sub, Servant, Specification, State, Strategy, Template Method, Visitor, plus Blackboard.
- **Concurrency patterns** include: Active Object, Double-Checked Locking (can be an anti-pattern), Monitor Object, Reactor, Read-Write Lock, Thread Pool, Thread-Specific Storage.
- **Peter Norvig's criticism**: 16 of 23 GoF patterns are simplified or eliminated in Lisp/Dylan — patterns can signal missing language features.
- **Hannemann & Kiczales**: Aspect-oriented programming (AspectJ) removed code-level dependencies from 17 of 23 GoF patterns.
- Inappropriate pattern use **increases complexity** unnecessarily.
- Patterns introduce **indirection** which can decrease runtime performance.
- **Meyer & Arnout** achieved full or partial componentization of two-thirds of patterns attempted, addressing the criticism that patterns must be re-implemented in each application.
- Know the distinction: **Design Pattern** (class/object level) vs. **Architecture Pattern** (system level) vs. **Architecture Style** (system organization) vs. **Implementation Pattern** (language idiom).
