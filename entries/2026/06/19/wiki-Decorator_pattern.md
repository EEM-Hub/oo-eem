---
source: sources/wiki-Decorator_pattern.md
source_url: https://en.wikipedia.org/wiki/Decorator_pattern
---

## Decorator Pattern — Dynamic Behavior Extension via Wrapping

The Decorator pattern is a structural Gang-of-Four design pattern that adds behavior to individual objects at runtime by wrapping them in decorator objects that share the same interface. Unlike subclassing, which binds extensions at compile time and affects all instances, decorators compose behavior per-object and can be stacked arbitrarily. This makes it a flexible, memory-efficient alternative to deep inheritance hierarchies.

## Key Concepts

- **Core mechanism**: A Decorator wraps a Component, implements the same interface, forwards all requests to the wrapped object, and adds behavior before or after forwarding
- **Runtime composition**: Decorators are applied and removed dynamically at runtime, unlike subclasses which are fixed at compile time
- **Transparency**: Clients interact with decorated and undecorated objects identically through the shared Component interface
- **Stacking**: Multiple decorators can be layered on a single object, each adding independent functionality — order of wrapping matters
- **Combinatorial explosion avoidance**: With N independent features, subclassing requires up to 2^N classes; decorators require only N decorator classes combined at runtime
- **Supports SRP**: Each decorator encapsulates a single responsibility/concern
- **Supports Open-Closed Principle**: Extends behavior without modifying existing source code
- **Memory-efficient**: Compared to subclassing (unused inherited fields) or property bloat (every instance carries all optional properties)
- **Shared interface**: Both Component and Decorator implement a common interface, mixin, or inherit from a common base

## Commands and Syntax

**Structural recipe (5 steps):**
1. Define a `Component` interface with operations
2. Create `ConcreteComponent` implementing the interface
3. Create abstract `Decorator` class implementing `Component`, holding a `Component` reference
4. In `Decorator`, forward all `Component` methods to the held reference
5. In `ConcreteDecorator` subclasses, override methods to add behavior before/after calling `super`

**Java pattern template:**
```java
// Component interface
public interface Component { void operation(); }

// Concrete component
class ConcreteComponent implements Component {
    public void operation() { /* base behavior */ }
}

// Abstract decorator — implements same interface, holds reference
abstract class Decorator implements Component {
    private final Component wrapped;
    public Decorator(Component c) { this.wrapped = c; }
    public void operation() { wrapped.operation(); }  // delegation
}

// Concrete decorator — adds behavior
class ConcreteDecorator extends Decorator {
    public ConcreteDecorator(Component c) { super(c); }
    public void operation() {
        addedBehavior();       // before
        super.operation();     // delegate
    }
}
```

**C++ static decorator (mixin inheritance):**
```cpp
template <typename T>
class ColoredShape: public T {
    string color;
public:
    explicit ColoredShape(const string& c): color{c} {}
    string getName() const {
        return std::format("{} which is colored {}", T::getName(), color);
    }
};
// Usage: ColoredShape<Circle> redCircle{"red"};
```

## Relationships

- **vs. Subclassing**: Decorator is the runtime-flexible alternative; subclassing is compile-time and affects all instances
- **vs. Adapter**: Adapter converts an interface; Decorator adds responsibility while keeping the same interface
- **vs. Facade**: Facade simplifies an interface; Decorator enriches one
- **With Command pattern**: Decorators are commonly applied/removed via Command (e.g., UI button toggling highlight decorators on text glyphs)
- **With State pattern**: State can be implemented using decorators instead of subclassed state objects, enabling compositional state representation
- **With Flyweight pattern**: Flyweight objects split into shared invariant + decorated variant components; decorators are cached and reused (e.g., iOS UITableView reusable cells)
- **With Facade pattern (hybrid)**: Decorators can augment a Facade, adding new functionality in the coordination space the Facade provides
- **With Adapter/Visitor patterns**: Useful for interfacing with collections of diversely-decorated objects — Adapter unifies interfaces, Visitor enables operations across decorated structures
- **Composition over Inheritance**: Decorator is a primary vehicle for preferring composition; supports multilayered runtime combination without multiple inheritance
- **Real-world implementations**: Java I/O Streams (`BufferedInputStream` wrapping `FileInputStream`) and .NET Framework streams both use this pattern

## Exam-Relevant Points

- Decorator is a **structural** pattern from the Gang of Four (not behavioral or creational)
- Key distinction from subclassing: **per-object, runtime** behavior change vs. **per-class, compile-time**
- Decorator and Component share the **same interface** — this is what makes decoration transparent to clients
- Decorator holds a **reference** to the Component (composition), not inheritance of state
- Supports **Single Responsibility Principle** and **Open-Closed Principle**
- Solves the **combinatorial explosion problem**: N independent extensions need only N decorator classes, not 2^N subclasses
- Java I/O Streams are the canonical real-world example of the Decorator pattern
- The **abstract Decorator class** forwards all methods to the wrapped component; **ConcreteDecorators** override specific methods
- Decorators can be **stacked** — order matters (each wraps the previous)
- Contrast table: **Adapter** = converts interface, **Decorator** = adds responsibility, **Facade** = simplifies interface
- Accepted drawback: inherited fields from Component base class in Decorator go unused (wasted memory per decorator layer)
- C++ offers a **static decorator** variant using template/mixin inheritance (compile-time composition)
- Decorator supports adding behavior to objects that **cannot be subclassed** or whose base class **cannot be modified** (e.g., external frameworks)
