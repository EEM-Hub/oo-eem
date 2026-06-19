---
source: sources/wiki-Memento_pattern.md
source_url: https://en.wikipedia.org/wiki/Memento_pattern
---

## Memento Pattern (Behavioral Design Pattern)

The Memento pattern is a Gang of Four behavioral design pattern that captures and externalizes an object's internal state without violating encapsulation, so the object can be restored to that state later. It is the foundational pattern behind undo/redo systems, version control mechanisms, and serialization workflows.

## Key Concepts

- **Three participants**: Originator (the object whose state is saved), Memento (an immutable snapshot of that state), and Caretaker (manages when to save/restore but never inspects memento contents)
- **Encapsulation preserved**: The Caretaker never accesses or modifies the Memento's internal data — only the Originator can read it back
- **Memento objects are immutable** — once created, their stored state does not change
- **Operates on a single object** — care must be taken if the Originator mutates other objects or external resources, as the Memento will not capture those side effects
- **Mutable state requires deep copying** — if the Originator's state contains mutable objects, the Memento must store a copy, not a reference
- **Multiple mementos can coexist** — the Caretaker can maintain a list/stack of mementos, enabling multi-level undo or selective rollback
- **Classic example**: A pseudorandom number generator (PRNG) where the seed acts as the memento — restoring the seed reproduces the same sequence
- **Classified as a Behavioral pattern** in the GoF taxonomy

## Commands and Syntax

**Originator interface**:
- `createMemento()` — captures current internal state into a new Memento object and returns it
- `restore(memento)` / `restoreFromMemento(memento)` — resets internal state from the given Memento

**Memento interface**:
- Stores state (typically via constructor)
- `getState()` / `getSavedState()` — accessible only to the Originator (enforced via inner class, package access, or friend/proxy patterns)

**Caretaker role** (no formal interface — it is the client code):
- Calls `createMemento()` before risky operations
- Stores returned Memento objects (often in a list or stack)
- Calls `restore(memento)` to roll back

**Alternative implementation strategies** (beyond inner class):
1. Serialization (serialize/deserialize state)
2. Package-private or module-scoped class for the Memento
3. Proxy-based access to achieve save/restore

## Relationships

- **Command pattern**: Often used together — Command records the operation, Memento stores the state needed to undo it
- **Iterator pattern**: An Iterator's position can be saved/restored via Memento
- **Serialization**: Serialization is both an alternative to and a mechanism for implementing Memento
- **Undo/Redo systems**: Memento provides the state-capture mechanism; a stack of Mementos provides multi-level undo
- **Version control**: Conceptually, each commit is a memento of repository state
- **Prototype pattern**: Both involve copying object state, but Prototype creates new objects while Memento restores existing ones
- **Caretaker–Originator relationship**: The Caretaker depends on the Originator to create and consume Mementos but is decoupled from the state representation

## Exam-Relevant Points

- Memento is a **Behavioral** GoF pattern — not Structural or Creational
- The three roles (Originator, Memento, Caretaker) and their responsibilities are frequently tested
- **Encapsulation is the central design goal** — the Caretaker must not inspect or modify Memento contents
- Memento objects should be **immutable**
- The pattern **only captures one object's state** — it does not handle cascading state across multiple objects
- When state contains mutable fields, the Memento **must store a deep copy**, not a reference
- Primary use cases to know: **undo, version control, serialization**
- The PRNG seed example is the canonical illustration (seed = memento, PRNG = originator, consumer = caretaker)
- `createMemento()` and `restore(memento)` are the two key operations on the Originator
- In Java, the Memento is typically implemented as a **static inner class** of the Originator to restrict access to its state
