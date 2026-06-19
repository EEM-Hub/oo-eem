---
source: sources/wiki-State_pattern.md
source_url: https://en.wikipedia.org/wiki/State_pattern
---

## State Pattern — Behavioral Design Pattern for Runtime State Transitions

The State pattern is a Gang of Four behavioral design pattern that allows an object to change its behavior when its internal state changes, effectively making the object appear to change its class. It encapsulates state-specific behavior into separate state objects, eliminating complex conditional logic and closely modeling finite-state machines.

## Key Concepts

- **Core idea**: Delegate state-specific behavior to interchangeable state objects rather than embedding conditionals (`if`/`switch`) in the context class
- **Context**: The class that maintains a reference to the current state object and delegates behavior to it
- **State interface**: Defines the contract for state-specific behavior (e.g., `handle()`)
- **Concrete states**: Each state is a separate class implementing the state interface, encapsulating behavior for that specific state
- **State transitions**: Concrete state objects change the context's current state by calling `setState()` on the context, passing a new state object
- **Two problems solved**: (1) objects need behavior that changes with internal state, (2) new states must be addable without modifying existing state classes (Open/Closed Principle)
- **Closely related to finite-state machines**: Each concrete state represents a machine state; method calls represent transitions
- **Can be interpreted as a switchable Strategy pattern**: The strategy (state) changes via method invocations defined in the pattern's interface
- **Eliminates rigid conditionals**: Avoids committing a class to a fixed set of behaviors, improving maintainability and extensibility

## Commands and Syntax

**Structure (UML participants)**:
- `Context` — holds a `State` reference, delegates via `state.handle()`
- `State` (interface) — declares `handle()` method
- `ConcreteStateA`, `ConcreteStateB` — implement state-specific behavior

**C++ Example** — Fan with Off/Low/High speed states:
```cpp
// Abstract state with pure virtual method
class FanState {
public:
    virtual void handleButtonPress(Fan& fan) const = 0;
    virtual ~FanState() = default;
};

// Context holds current state, delegates button press
class Fan {
    unique_ptr<FanState> currentState;
public:
    void setState(unique_ptr<FanState> state) noexcept;
    void pressButton() noexcept { currentState->handleButtonPress(*this); }
};

// Concrete state performs action and transitions
class OffState : public FanState {
    void handleButtonPress(Fan& fan) const override {
        fan.setState(std::make_unique<LowSpeedState>());
    }
};
```

**Transition flow**: `Context.handle()` → current state performs work → state calls `context.setState(newState)` → next call uses new state.

## Relationships

- **Strategy pattern**: State can be viewed as Strategy where the strategy switches itself through interface methods; Strategy typically has the client choose the algorithm externally
- **Finite-state machines**: State pattern is the OO realization of FSMs — states become classes, transitions become method calls that swap the state object
- **Typestate analysis**: A static analysis technique related to the State pattern that tracks object state at compile time
- **Other behavioral patterns**: Part of the GoF behavioral family alongside Command, Observer, Mediator, Chain of Responsibility, and others
- **Open/Closed Principle**: Adding new states requires only new classes, not modification of existing ones
- **Composition over inheritance**: State pattern uses composition (context holds a state object) rather than inheritance to vary behavior

## Exam-Relevant Points

- State pattern is a **behavioral** GoF pattern — know the classification
- The **Context** delegates to a **State** interface; it never implements state-specific behavior directly
- State transitions are initiated by the **concrete state objects** themselves (they call `setState` on the context), not by the context
- Key differentiator from Strategy: in State, the **state objects control transitions**; in Strategy, the **client selects** the algorithm
- Solves the problem of **rigid conditional logic** for state-dependent behavior — replacing `if`/`switch` with polymorphism
- Adding new states **does not require modifying** existing state classes or the context (Open/Closed Principle)
- The pattern models **finite-state machines** in an object-oriented way
- Documented in *Design Patterns: Elements of Reusable Object-Oriented Software* (GoF, 1995), page 305ff
- The `handle(this)` call passes the context to the state, enabling the state to trigger transitions back on the context
