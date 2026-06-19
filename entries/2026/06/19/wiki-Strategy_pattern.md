---
source: sources/wiki-Strategy_pattern.md
source_url: https://en.wikipedia.org/wiki/Strategy_pattern
---

## Strategy Pattern (Policy Pattern)

The Strategy pattern is a behavioral design pattern from the Gang of Four catalog that enables selecting an algorithm at runtime. Rather than hardcoding a single algorithm, the client receives a reference to one of a family of interchangeable algorithms, allowing the algorithm to vary independently from the clients that use it. This decouples *what* needs to be done from *how* it is done.

## Key Concepts

- **Also known as**: Policy pattern
- **Category**: Behavioral design pattern (Gang of Four)
- **Core idea**: Encapsulate a family of algorithms behind a common interface and make them interchangeable at runtime
- **Participants**:
  - **Context** — holds a reference to a Strategy object; delegates algorithmic work to it rather than implementing it directly
  - **Strategy** (interface) — declares the contract that all concrete algorithms must follow
  - **ConcreteStrategy** (Strategy1, Strategy2, etc.) — each implements a specific algorithm behind the Strategy interface
- **Mechanism**: The Context stores a reference to a Strategy (via function pointer, first-class function, class instance, or reflection) and calls it when needed
- **Runtime flexibility**: The concrete strategy can be swapped at runtime by replacing the reference, changing behavior without modifying the Context
- **Favors composition over inheritance**: Behaviors are not inherited by subclasses but composed via separate strategy objects
- **Eliminates code duplication**: Multiple clients can reuse the same strategy implementations across different parts of a system

## Commands and Syntax

**Java example structure:**

```java
// 1. Define the strategy interface
interface IBrakeBehavior {
    public void brake();
}

// 2. Implement concrete strategies
class BrakeWithABS implements IBrakeBehavior {
    public void brake() { /* ABS braking */ }
}
class Brake implements IBrakeBehavior {
    public void brake() { /* simple braking */ }
}

// 3. Context holds a strategy reference
abstract class Car {
    private IBrakeBehavior brakeBehavior;
    public Car(IBrakeBehavior brakeBehavior) {
        this.brakeBehavior = brakeBehavior;
    }
    public void applyBrake() { brakeBehavior.brake(); }
    public void setBrakeBehavior(IBrakeBehavior brakeType) {
        this.brakeBehavior = brakeType;
    }
}

// 4. Swap strategy at runtime
suvCar.setBrakeBehavior(new Brake());
```

**Key implementation steps:**
1. Define a strategy interface with the algorithm method
2. Create concrete classes implementing each algorithm variant
3. Context class holds a strategy reference (injected via constructor or setter)
4. Client selects and assigns the appropriate strategy, can change it at runtime

## Relationships

- **Open/Closed Principle (OCP)**: Strategy directly supports OCP — classes are open for extension (new strategies) but closed for modification (context doesn't change)
- **Composition over Inheritance**: Strategy is the canonical example of preferring composition to subclass-based behavior variation
- **Dependency Injection**: Strategy is a form of dependency injection — the algorithm is injected into the context
- **State Pattern**: Structurally identical (context delegates to an interface), but State transitions are driven by internal state changes while Strategy is chosen by the client
- **Template Method**: Both vary algorithm steps, but Template Method uses inheritance (subclass overrides steps) while Strategy uses composition (delegate to separate object)
- **Higher-Order Functions**: In functional programming, passing a function as an argument achieves the same effect without the class ceremony
- **Policy-Based Design**: C++ template-based equivalent of Strategy (compile-time rather than runtime selection)
- **Entity-Component-System**: Shares the principle of composing behavior from separate objects rather than deep inheritance hierarchies

## Exam-Relevant Points

- Strategy is a **behavioral** pattern — know the GoF classification (creational, structural, behavioral)
- The pattern allows the algorithm to **vary independently from clients** that use it — this is the canonical one-sentence definition
- Strategy uses **composition over inheritance** to define behavior — this is the key architectural principle
- The Context does **not** implement the algorithm directly; it **delegates** to the Strategy interface
- Strategies can be swapped **at runtime** (not just compile-time) via setter methods
- Strategy supports the **Open/Closed Principle**: new algorithms are added as new classes without modifying existing code
- **Distinguish from State pattern**: structurally similar, but Strategy is chosen externally by the client while State transitions happen internally
- **Distinguish from Template Method**: Template Method uses inheritance to vary steps; Strategy uses composition to vary entire algorithms
- The pattern **eliminates conditional logic** (if/else or switch on type) by replacing it with polymorphic dispatch
- Common real-world applications: validation algorithms, sorting strategies, compression algorithms, pricing rules, authentication methods
