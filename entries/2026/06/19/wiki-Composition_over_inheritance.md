---
source: sources/wiki-Composition_over_inheritance.md
source_url: https://en.wikipedia.org/wiki/Composition_over_inheritance
---

## Composition Over Inheritance

This page covers the **composition over inheritance** design principle in object-oriented programming, which favors building object capabilities through composed delegate objects (has-a relationships) rather than through class hierarchy (is-a relationships). It demonstrates the pattern using a game object example, discusses benefits and drawbacks, and catalogs language-specific mechanisms for mitigating composition's boilerplate cost.

## Key Concepts

- **Composition over inheritance** achieves code reuse by including component objects as fields rather than inheriting from a base class; method calls are forwarded to these components (**method forwarding** / **delegation**).
- The principle is sometimes called **composite reuse** or **composition with forwarding**.
- Composition models what an object **has-a** (capabilities), while inheritance models what it **is-a** (identity) — the principle argues has-a is more flexible for most designs.
- Composition allows behavior to be **changed at runtime** by swapping delegate objects, whereas inheritance relationships are static and require recompilation.
- The principle is not absolute — the Gang of Four's *Design Patterns* (1994) notes inheritance and composition typically **work hand-in-hand**; many problems easily solved with inheritance are difficult with composition alone.
- Languages like **Go** and **Rust** use type composition exclusively, having no class-based inheritance at all.
- A 2013 empirical study of 93 Java projects found roughly **24% of inheritance uses** were purely for code reuse (internal or external), suggesting meaningful opportunity to use composition instead.

## Commands and Syntax

**Inheritance approach (problem):** Multiple concrete classes (Player, Cloud, Building, Trap) need different combinations of behaviors (Visible, Movable, Solid). Inheritance forces either multiple inheritance (diamond problem risk) or combinatorial explosion of intermediate classes (`VisibleAndSolid`, `VisibleAndMovable`, etc.).

**Composition approach (solution):**
1. Define **abstract delegate interfaces** for each behavior axis (`VisibilityDelegate`, `UpdateDelegate`, `CollisionDelegate`).
2. Implement **concrete strategies** for each (e.g., `Visible`/`NotVisible`, `Movable`/`NotMovable`, `Solid`/`NotSolid`).
3. The composed `GameObject` holds **pointers to delegates** and forwards method calls:
```cpp
class GameObject {
    unique_ptr<VisibilityDelegate> visibilityDelegate;
    unique_ptr<UpdateDelegate> updateDelegate;
    unique_ptr<CollisionDelegate> collisionDelegate;
public:
    void update() { updateDelegate->update(); }
    void draw() const { visibilityDelegate->draw(); }
};
```
4. Concrete types **select their behavior mix** at construction:
```cpp
class Player : public GameObject {
    Player(): GameObject(new Visible(), new Movable(), new Solid()) {}
};
class Smoke : public GameObject {
    Smoke(): GameObject(new Visible(), new Movable(), new NotSolid()) {}
};
```

## Relationships

- **Strategy Pattern**: Composition over inheritance is essentially the Strategy pattern applied structurally — each delegate is a swappable strategy.
- **State Pattern**: Closely related; delegates can be swapped at runtime to change behavior, which is exactly the State pattern.
- **Delegation Pattern**: Method forwarding is the mechanical technique that makes composition work.
- **Diamond Problem / Multiple Inheritance**: Composition sidesteps this entirely by avoiding class hierarchies.
- **Liskov Substitution Principle**: Inheritance requires LSP compliance; composition avoids the subtyping contract altogether.
- **Traits / Mixins / Protocol Extensions**: Language features that mitigate composition's boilerplate drawback — they provide default implementations without full inheritance coupling.
- **Interface Segregation**: The delegate interfaces in the composition approach naturally follow ISP by separating concerns into distinct small interfaces.

## Exam-Relevant Points

- Composition over inheritance means preferring **has-a** over **is-a** relationships for code reuse.
- The primary **benefit** is higher flexibility: behavior can be composed from independent components and changed at runtime.
- The primary **drawback** is **forwarding boilerplate** — every delegated method must be explicitly forwarded, unlike inheritance where methods are automatically available.
- Languages mitigate the boilerplate via: **Go** type embedding, **Kotlin** built-in delegation syntax, **Rust/Swift** trait/protocol default implementations, **Java 8+/C# 8+** default interface methods, **Scala 3** export clauses, **PHP 5.4+** traits.
- Composition avoids the **diamond problem** that plagues multiple inheritance.
- The *Design Patterns* book (GoF, 1994) explicitly recommends: "Favor object composition over class inheritance" — but does **not** say to eliminate inheritance entirely.
- When a base class provides many default methods and only a few need overriding, **inheritance is more concise** — composition would require forwarding all methods.
- The principle applies selectively: it is a **guideline, not a law**.
