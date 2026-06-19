---
source: sources/wiki-Observer_pattern.md
source_url: https://en.wikipedia.org/wiki/Observer_pattern
---

## Observer Pattern — Event-Based Dependency Notification

The Observer pattern is a behavioral design pattern from the Gang of Four catalog in which a **subject** (event source) maintains a list of **observers** (event sinks) and automatically notifies them of state changes by calling their methods. It establishes a one-to-many dependency with direct references between subject and observers — no intermediary broker is involved.

## Key Concepts

- **Subject** (aka event source/event stream): the object being watched; maintains its own state and a list of registered observers
- **Observer** (aka event sink): a dependent that registers with a subject to receive notifications via a standardized `update()` interface
- **One-to-many dependency**: multiple observers listen to a single subject
- **Loose coupling through interface standardization**: the subject only knows observers implement `update()`, not their concrete types
- **Typically synchronous**: the subject calls observer methods directly when state changes, though asynchronous implementations using event queues are possible
- **No intermediary broker**: distinguishes Observer from Publish-Subscribe — subject and observers hold direct references to each other
- **Registration/deregistration**: observers register themselves at runtime and can be added or removed dynamically
- **Lapsed listener problem**: if the subject holds strong references to observers, unregistered observers can cause memory leaks; mitigated with **weak references**
- **Throttling/temporal decoupling**: for high-frequency state changes (e.g., progress bars), observers can poll at intervals rather than reacting to every change

## Commands and Syntax

Standard interface contract:

- **Subject** provides: `attach(observer)`, `detach(observer)`, `notify()`
- **Observer** provides: `update(subject)` — called by subject during notification
- **Registration flow**: observer calls `subject.attach(this)` to subscribe
- **Notification flow**: on state change, subject calls `notify()`, which iterates observers calling `update()` on each; observers then call `getState()` to synchronize

Java example (simplified):
```java
interface Observer { void update(String event); }
class EventSource {
    List<Observer> observers = new ArrayList<>();
    public void addObserver(Observer o) { observers.add(o); }
    public void notifyObservers(String event) {
        observers.forEach(o -> o.update(event));
    }
}
```

C# uses built-in `IObservable<T>` and `IObserver<T>` interfaces with `Subscribe()` returning an `IDisposable` for clean unsubscription.

## Relationships

- **Publish-Subscribe pattern**: closely related but uses an intermediary broker, decoupling publishers from subscribers; Observer is direct, Pub-Sub is indirect
- **Mediator pattern**: related — centralizes communication between objects, but mediator encapsulates interaction logic rather than broadcasting notifications
- **Singleton pattern**: listed as a related pattern in GoF
- **MVC architecture**: Observer is fundamental to MVC — the View observes the Model
- **Event-driven programming**: Observer is a core mechanism for implementing event handling systems
- **Entity-Component-System (ECS)**: often uses Observer internally
- **Implicit invocation**: architectural style built on the same notification concept
- **Dispose pattern**: relevant for managing observer lifecycle and preventing memory leaks
- **GoF Behavioral patterns**: one of the 23 canonical patterns alongside Strategy, Command, Iterator, Mediator, State, etc.

## Exam-Relevant Points

- Observer is a **behavioral** pattern, not structural or creational
- The subject **does not** know the concrete types of its observers — only that they implement the observer interface
- Key difference from Pub-Sub: Observer has **no broker**; subject holds **direct references** to observers
- The **lapsed listener problem** is the canonical memory leak risk — solved with **weak references**
- `java.util.Observer` and `java.util.Observable` are **deprecated since Java 9** due to their limited model
- Observer is **typically synchronous**; Pub-Sub is **typically asynchronous**
- Observer pattern is **suitable for in-process systems** (GUI, MVC); Pub-Sub scales to **distributed systems**
- Observer does **not** provide: message filtering, delivery guarantees, message persistence, or message logging — these require a full messaging system
- The naive alternative (subject calling specific methods on concrete dependents) creates **tight coupling** but may be preferable in **performance-critical** or **real-time** scenarios
- Throttling via timer-based polling is the standard solution for **high-frequency update** scenarios (e.g., progress bars)
- C# provides first-class support via `IObservable<T>` / `IObserver<T>` with `IDisposable`-based unsubscription
