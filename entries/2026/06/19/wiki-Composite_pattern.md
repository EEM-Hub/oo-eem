---
source: sources/wiki-Composite_pattern.md
source_url: https://en.wikipedia.org/wiki/Composite_pattern
---

## Composite Pattern: Tree-Structured Part-Whole Hierarchies

The Composite pattern is a structural design pattern from the Gang of Four catalog that lets clients treat individual objects and compositions of objects uniformly. It organizes objects into tree structures representing part-whole hierarchies, where a single interface (Component) abstracts over both leaf nodes and composite containers, eliminating the need for client code to distinguish between them.

## Key Concepts

- **Core intent**: Compose objects into tree structures to represent part-whole hierarchies; let clients treat individual objects and compositions uniformly through a shared interface.
- **Three participants**: **Component** (the shared interface/abstraction), **Leaf** (terminal objects with no children), and **Composite** (containers that hold and delegate to child Components).
- **Recursive composition**: A Composite holds a collection of Components, which can themselves be Leaves or other Composites, forming an arbitrarily deep tree.
- **Uniform treatment**: Clients program against the Component interface only — they never need to know whether they're working with a Leaf or a Composite.
- **Delegation pattern**: Composite objects forward requests to their children recursively (e.g., `for each child in children: child.operation()`), aggregating results as needed (e.g., summing prices).
- **Has-a relationship**: The Composite "has" child Components — this is composition, not inheritance of behavior.
- **Transparency vs. type safety tradeoff**: Two design variants exist for where to declare child-manipulation methods (`add`, `remove`, `getChild`):
  - **Transparency**: Declare them on Component — clients treat all objects uniformly, but Leaf objects must handle (reject) child operations at runtime, losing compile-time safety.
  - **Type safety**: Declare them only on Composite — clients must distinguish Leaf from Composite for structural mutations, but invalid operations are caught at compile time.
- **GoF recommendation**: The original GoF book favors transparency over type safety.
- **Post-construction optimization**: If the tree structure is fixed after construction, child-manipulation methods can be omitted from the Component interface entirely, since only construction code (which already knows types) needs them.

## Commands and Syntax

**General structure (pseudocode):**
```
interface Component {
    operation()
    // Transparency variant includes: add(Component), remove(Component), getChild(int)
}

class Leaf implements Component {
    operation() { /* do work directly */ }
}

class Composite implements Component {
    children: List<Component>
    operation() {
        for each child in children:
            child.operation()
    }
    add(Component c) { children.append(c) }
    remove(Component c) { children.remove(c) }
}
```

**Recursive aggregation pattern** (e.g., computing total price):
```
Composite.getNetPrice():
    total = self.netPrice
    for each child in children:
        total += child.getNetPrice()
    return total
```

**Leaf rejection of child operations** (transparency variant):
```
Leaf.add(child):
    throw RuntimeError("Leaf cannot have children")
```

## Relationships

- **Structural pattern family**: Sits alongside Adapter, Bridge, Decorator, Facade, Flyweight, and Proxy in the GoF structural patterns.
- **Decorator**: Often used together — Decorator adds responsibilities to individual Components; Composite organizes them into trees. Both rely on recursive composition.
- **Iterator**: Commonly paired with Composite to traverse the tree structure.
- **Visitor**: Frequently applied to Composite structures to define operations across heterogeneous node types without modifying the Component classes.
- **Chain of Responsibility**: Can use a Composite's parent-child links as the chain.
- **Flyweight**: Leaf nodes in a Composite tree are candidates for Flyweight sharing when they have no intrinsic state.
- **Builder**: Can construct Composite trees step-by-step.
- **Law of Demeter**: Relevant because Composite lets clients interact only with the top-level Component, reducing coupling to internal structure.
- **Mixin**: Related approach for composing behavior, but through inheritance rather than containment.

## Exam-Relevant Points

- Composite is classified as a **structural** pattern (not behavioral or creational).
- The pattern's primary purpose is **uniform treatment** of individual and composed objects — this is the canonical one-sentence definition.
- Know the three roles: **Component** (interface), **Leaf** (no children), **Composite** (has children, delegates).
- The transparency vs. type safety tradeoff is a classic exam question — transparency puts `add`/`remove` on Component (uniform but unsafe); type safety puts them on Composite only (safe but non-uniform).
- GoF originally favored **transparency**; modern usage often favors **type safety** and may omit child-manipulation methods from Component entirely.
- Use Composite when: clients should ignore the difference between individual objects and compositions; multiple objects are used the same way with nearly identical handling code.
- Composite uses a **has-a** (composition) relationship, not is-a (inheritance) for the child collection.
- Operations on Composites are implemented via **recursive delegation** down the tree.
- The pattern enables representing **part-whole hierarchies** as tree structures — "part-whole hierarchy" is the key phrase in exam contexts.
