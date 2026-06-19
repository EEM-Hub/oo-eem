---
source: sources/wiki-Flyweight_pattern.md
source_url: https://en.wikipedia.org/wiki/Flyweight_pattern
---

## Flyweight Pattern — Shared Object Memory Optimization

The Flyweight pattern is a structural design pattern from the Gang of Four catalog that minimizes memory usage by sharing common data across many similar objects. Rather than each object storing its own copy of repeated data, flyweights separate **intrinsic state** (shared, context-independent) from **extrinsic state** (unique, context-dependent), allowing many logical objects to reuse a single physical instance for their shared portions.

## Key Concepts

- **Intrinsic state**: Data that is invariant, context-independent, and shareable across objects (e.g., the glyph shape of the letter 'A'). Stored inside the flyweight object.
- **Extrinsic state**: Data that is variant, context-dependent, and cannot be shared (e.g., the position of a specific 'A' in a document). Passed in by the client at use time.
- **FlyweightFactory**: Creates and manages flyweight objects; returns existing instances when available rather than creating duplicates. Often implemented as a Singleton.
- **Classic example**: A word processor where each character references a shared glyph object rather than embedding its own font outline, metrics, and formatting data — only position is stored per-character.
- **Hash consing**: The same idea of sharing data structures appears under this name in other contexts (especially functional programming).
- **Origin**: Term coined by Paul Calder and Mark Linton in 1990 for handling glyphs in a WYSIWYG editor, though similar techniques existed as early as 1988 (ET++ framework).

## Commands and Syntax

**Structural participants:**
- `Client` — uses flyweights, supplies extrinsic state
- `FlyweightFactory` — creates/caches flyweight instances via `getFlyweight(key)`
- `Flyweight` (interface) — accepts extrinsic state, performs operations
- `ConcreteFlyweight` — implements Flyweight, stores intrinsic state

**Runtime sequence:**
1. Client calls `factory.getFlyweight(key)` — factory returns existing or new instance
2. Client calls `flyweight.operation(extrinsicState)` — passes context-dependent data
3. Subsequent requests for the same key return the cached instance

**Implementation patterns (from examples):**
- **C# approach**: Static shared reference (`Pointer.Company`) accessed by all `MyObject` instances
- **C++ approach**: `Registry` class with `HashMap` acting as factory + cache; `findByName()` creates on first access, returns cached thereafter
- **PHP approach**: Private constructor with static `intern()` factory method and class-level cache array — canonical interning pattern

## Relationships

- **Factory Method / Abstract Factory**: FlyweightFactory typically uses factory patterns internally to create instances
- **Singleton**: The FlyweightFactory is often implemented as a singleton for global access
- **Facade**: The factory interface may act as a facade over complex caching logic
- **Chain of Responsibility**: Can encapsulate multi-cache lookup strategies with loose coupling
- **Composite**: Flyweight is often used within composite structures (e.g., shared leaf nodes in a tree)
- **Related concepts**: Copy-on-write (deferred duplication), Memoization (caching computed results), Multiton (keyed singleton variant)
- **Structural pattern family**: Sits alongside Adapter, Bridge, Composite, Decorator, Facade, and Proxy

## Exam-Relevant Points

- Flyweight is a **structural** pattern — know the GoF classification (not behavioral or creational)
- The critical distinction is **intrinsic vs. extrinsic state** — intrinsic is shared and stored in the flyweight; extrinsic is passed in by the client
- The factory **must check for existing instances** before creating new ones — this is the core sharing mechanism
- **Immutable flyweights** are easiest to share safely across threads; mutable flyweights allow reuse via reinitialization but complicate concurrency
- Two caching strategies: **maintained** (FIFO, push/pop) vs. **unmaintained** (bulk initialization at startup, search-based retrieval)
- **Concurrency options**: Pre-instantiate all flyweights (no contention), single-threaded creation (contention, one instance per value), or concurrent creation (no contention, multiple instances per value)
- Making flyweights into **immutable value objects** enables safe sharing — two instances are equal if their values are equal
- The pattern trades **computational overhead** (lookup/creation logic) for **memory savings** — only beneficial when object count is large and shared state is significant
- The word processor / character glyph example is the canonical illustration — expect it on exams
