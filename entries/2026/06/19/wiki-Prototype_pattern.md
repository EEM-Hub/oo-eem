---
source: sources/wiki-Prototype_pattern.md
source_url: https://en.wikipedia.org/wiki/Prototype_pattern
---

## Prototype Pattern (Creational Design Pattern)

The Prototype pattern is a creational design pattern from the Gang of Four catalog that creates new objects by cloning a prototypical instance rather than using constructors directly. It avoids subclassing the object creator (unlike Factory Method) and bypasses the cost of standard object construction when that cost is prohibitive.

## Key Concepts

- **Core mechanism**: Define a `Prototype` interface with a `clone()` method; concrete classes implement `clone()` to return a copy of themselves.
- **Purpose**: Determine the type of object to create at runtime, not compile-time, by copying a prototype rather than invoking `new` on a hard-coded class.
- **Avoids subclassing**: Unlike Factory Method, Prototype does not require subclassing to vary the product — it uses delegation (cloning) instead of inheritance.
- **Requires initialization**: Prototype does not require subclassing but may require a separate `initialize()` operation to configure the cloned object after creation (e.g., setting room references on a cloned Door).
- **Dynamic configuration**: Prototype objects can be added and removed at runtime, enabling flexible runtime configuration of what objects a factory produces.
- **Polymorphic constructor**: The `clone()` method acts as a virtual constructor — the client calls `clone()` on an abstract type and gets a concrete copy without knowing the specific class.
- **Real-world analogy**: Mitotic cell division — a cell clones itself to produce two identical cells.

## Commands and Syntax

**Implementation structure (C++ idiom):**

```cpp
// 1. Abstract base with pure virtual clone
class MapSite {
public:
    virtual unique_ptr<MapSite> clone() const = 0;
    virtual ~MapSite() = default;
};

// 2. Concrete class implements clone by copying itself
class Room : public MapSite {
    unique_ptr<MapSite> clone() const override {
        return std::make_unique<Room>(*this);
    }
};

// 3. Prototype factory stores prototypes, clones on request
class MazePrototypeFactory : public MazeFactory {
    unique_ptr<Maze> prototypeMaze;
    shared_ptr<Room> prototypeRoom;
    // ...
    unique_ptr<Maze> makeMaze() const override {
        return prototypeMaze->clone();
    }
};
```

**Client usage**: Construct a factory with prototype instances, then call factory methods which internally delegate to `clone()`.

## Relationships

- **vs. Factory Method**: Factory Method requires subclassing the creator to vary products; Prototype avoids subclassing but requires `clone()` + optional `initialize()`.
- **vs. Abstract Factory**: Abstract Factory can store a set of prototypes from which to clone and return products. Abstract Factory can be implemented via Prototype (delegation) rather than Factory Method (inheritance).
- **with Singleton, Builder**: Abstract Factory, Builder, and Prototype can all use Singleton in their implementations.
- **with Composite and Decorator**: Designs heavy in Composite or Decorator often benefit from Prototype for copying complex object structures.
- **Evolution path**: Designs often start with Factory Method and evolve toward Abstract Factory, Prototype, or Builder as flexibility requirements grow.
- **Not the same as**: Prototype-based programming (a language paradigm, e.g., JavaScript) or function prototypes (forward declarations).

## Exam-Relevant Points

- Prototype is one of the **5 creational GoF patterns**: Abstract Factory, Builder, Factory Method, Prototype, Singleton.
- Key distinction: Prototype **does not require subclassing** but **does require an initialize operation**; Factory Method **requires subclassing** but **does not require initialization**.
- The pattern solves two problems: (1) determining the concrete type at runtime, and (2) instantiating dynamically loaded classes.
- The `clone()` method is the central operation — it returns a copy of the object, enabling a "polymorphic constructor."
- Abstract Factory can be implemented with **either** Factory Method (inheritance) **or** Prototype (delegation) — know this trade-off.
- Prototype enables **runtime addition and removal** of product types without changing factory code.
- Use `clone()` over `new` when you need a duplicate that preserves the original object's state (e.g., bank account transaction processing), rather than a default-initialized instance.
