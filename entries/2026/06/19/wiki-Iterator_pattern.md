---
source: sources/wiki-Iterator_pattern.md
source_url: https://en.wikipedia.org/wiki/Iterator_pattern
---

## Iterator Pattern — Decoupling Traversal from Container Representation

The Iterator pattern is a behavioral design pattern (one of the Gang of Four's 23 patterns) that provides a way to sequentially access elements of an aggregate object without exposing its underlying data structure. It separates traversal logic from the collection itself, enabling multiple traversal strategies and allowing algorithms to work generically across different container types.

## Key Concepts

- **Core intent**: "Provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation."
- **Decouples algorithms from containers** — algorithms like `searchForElement()` can be written against an iterator interface rather than a specific container type.
- **Problems it solves**:
  - Accessing/traversing aggregate elements without exposing internal representation (data structures).
  - Adding new traversal operations without modifying the aggregate's interface.
- **Solution mechanism**: Define a separate iterator object that encapsulates accessing and traversing the aggregate. Clients interact only with the iterator interface.
- **Multiple iterators**: Different iterator implementations can traverse the same aggregate in different ways (forward, reverse, filtered, etc.).
- **Open/Closed Principle alignment**: New traversal behavior is added by creating new iterator classes, not by modifying the aggregate.
- **Classification**: Behavioral pattern in the GoF taxonomy (alongside Command, Observer, Strategy, etc.).

## Commands and Syntax

**Participants (from UML structure):**
- `Aggregate` (interface) — declares `createIterator()` factory method
- `ConcreteAggregate` — implements `createIterator()`, returns a concrete iterator
- `Iterator` (interface) — declares `next()`, `hasNext()`
- `ConcreteIterator` — implements traversal, holds reference to the aggregate

**Typical interaction sequence:**
1. Client calls `createIterator()` on an Aggregate
2. Aggregate creates and returns a ConcreteIterator
3. Client calls `hasNext()` / `next()` on the iterator to traverse

**C++ idiom** — iterators model pointer semantics:
```cpp
// Container exposes begin() and end() returning raw pointers or iterator objects
Iterator begin() const noexcept { return elements; }
Iterator end() const noexcept { return elements + listSize; }

// Range-based for loop (uses begin/end protocol)
for (const double& x : v) { /* ... */ }

// Explicit iterator loop
for (auto i = v.begin(); i != v.end(); ++i) { /* ... */ }
```

- C++ uses the "end sentinel" model — equality test against `end()` rather than the iterator knowing it has reached the end.
- C++ and Python are notable for standardizing iterator syntax at the language level.

## Relationships

- **Composite pattern** — iterators are commonly used to traverse composite structures (trees of objects).
- **Observer pattern** — both are behavioral GoF patterns that decouple components; Observer decouples event producers from consumers, Iterator decouples traversal from storage.
- **Factory Method** — `createIterator()` is an example of the Factory Method pattern applied within Iterator.
- **Strategy pattern** — different iterator implementations can be seen as interchangeable traversal strategies.
- **Container/Collection** — the aggregate that the iterator traverses; the pattern exists precisely to hide the container's internal structure.
- **Concept (C++ generic programming)** — in C++, iterators model "concepts" (named sets of requirements), enabling compile-time polymorphism via templates.

## Exam-Relevant Points

- Iterator is a **behavioral** pattern, not structural or creational.
- It is one of the **23 GoF patterns** from *Design Patterns: Elements of Reusable Object-Oriented Software* (1994).
- The pattern's defining sentence: "Provide a way to access the elements of an aggregate object sequentially **without exposing its underlying representation**."
- Two core problems: (1) traverse without exposing representation, (2) add new traversal operations without changing the aggregate interface.
- The solution introduces a **separate object** (the iterator) — traversal logic lives outside the aggregate.
- Placing traversal operations directly in the aggregate interface is **inflexible** because it commits the aggregate to specific traversal operations and prevents adding new ones without interface changes.
- In C++, iterators use **pointer semantics** (dereference, increment, decrement) and rely on an **end sentinel** for bounds checking.
- The `createIterator()` method on the Aggregate is an application of **Factory Method**.
- Different iterators enable **different traversal strategies** over the same aggregate without modifying the aggregate.
- Not all algorithms can be fully decoupled from containers — some are **necessarily container-specific**.
