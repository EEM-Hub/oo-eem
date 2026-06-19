---
source: sources/wiki-Mediator_pattern.md
source_url: https://en.wikipedia.org/wiki/Mediator_pattern
---

## Mediator Pattern

The Mediator pattern is a behavioral design pattern from the Gang of Four catalog that defines an object encapsulating how a set of objects interact. Instead of objects communicating directly with each other (creating tight coupling), they communicate through a central mediator object, which controls and coordinates their interaction. This promotes loose coupling and makes interactions independently variable.

## Key Concepts

- **Behavioral pattern** — alters program running behavior by restructuring how objects communicate
- **Core problem solved**: tight coupling between interacting objects makes them hard to implement, change, test, and reuse
- **Central idea**: replace direct object-to-object references with indirection through a mediator, so colleagues have no explicit knowledge of each other
- **Loose coupling**: objects only refer to and know about their mediator, not each other
- **Interaction independence**: the interaction logic can be changed independently from the colleague objects themselves
- **Four participants**:
  - **Mediator** — interface defining communication contract between colleagues
  - **ConcreteMediator** — implements the mediator interface; knows all colleagues and coordinates their communication
  - **Colleague** — interface for communication with other colleagues via the mediator
  - **ConcreteColleague** — implements colleague interface; communicates only through its mediator
- **Not the same as the Broker pattern** — despite superficial similarity, these solve different problems

## Commands and Syntax

**Structural flow** (from the UML sequence diagram):
1. `Colleague1` calls `mediate(this)` on the `Mediator1` object
2. `Mediator1` gets changed data from `Colleague1`
3. `Mediator1` performs `action2()` on `Colleague2`
4. `Colleague2` calls `mediate(this)` on `Mediator1` in response
5. `Mediator1` gets changed data from `Colleague2` and performs `action1()` on `Colleague1`

**Typical implementation structure** (C# example):
- Define an `IComponent` interface with a `SetState` method
- Concrete components implement the interface
- The `Mediator` class holds references to all components and coordinates state changes via a single `ChangeState` method

**Event-based variant** (chat room example):
- Mediator exposes an event (e.g., `MessageReceived`)
- Colleagues subscribe to the mediator's event on construction
- Sending goes through `mediator.Send()`; receiving is handled by event callbacks

## Relationships

- **Observer pattern** — mediator implementations often use observer internally to notify colleagues of changes (the Java example explicitly combines both)
- **Facade pattern** — both centralize interaction, but Facade defines a simplified interface to a subsystem (unidirectional), while Mediator enables multidirectional cooperative communication
- **Broker pattern** — related but distinct; easily confused with mediator
- **Coupling** — mediator directly addresses the problem of tight coupling between classes
- **Part of the GoF Behavioral patterns** alongside: Chain of Responsibility, Command, Interpreter, Iterator, Memento, Observer, State, Strategy, Template Method, Visitor

## Exam-Relevant Points

- Mediator is a **behavioral** pattern (not structural or creational)
- One of the **23 GoF design patterns** from *Design Patterns: Elements of Reusable Object-Oriented Software* (1994, Gamma/Helm/Johnson/Vlissides)
- **Primary benefit**: reduces coupling by preventing objects from referring to each other explicitly
- **Trade-off**: the mediator itself can become a "god object" — it centralizes interaction logic, which may grow complex
- Objects communicate **indirectly** through the mediator, not directly with each other
- Mediator makes objects **loosely coupled** — they only know about the mediator, not about each other
- Enables changing interaction behavior **independently** from the objects involved
- The pattern improves **reusability and testability** of individual colleague classes
- Distinguish from Broker pattern and from Facade pattern on exams — mediator is bidirectional coordination among peers, Facade is a simplified interface to a subsystem
