---
source: sources/wiki-Command_pattern.md
source_url: https://en.wikipedia.org/wiki/Command_pattern
---

## Command Pattern (Behavioral Design Pattern)

The Command pattern is a GoF behavioral design pattern that encapsulates a request as an object, containing all information needed to perform an action or trigger an event at a later time — including the method name, the owning object, and parameter values. This decouples the sender of a request from the object that performs it, enabling parameterization of clients with different requests, queuing, logging, and undoable operations.

## Key Concepts

- **Four core roles**: Command (encapsulates request), Receiver (performs the work), Invoker (triggers execution, knows only the Command interface), Client (assembles commands, receivers, and invokers)
- The Command object stores a reference to the Receiver via aggregation and holds parameter values for the receiver's method
- The Invoker is decoupled from concrete commands — it depends only on the abstract Command interface and calls `execute()`
- The Client decides which receivers map to which commands, and which commands map to which invokers
- The pattern closely mirrors **first-class functions** and **higher-order functions** in functional programming — the invoker is a higher-order function and the command is a first-class argument
- One of the 23 GoF design patterns from *Design Patterns: Elements of Reusable Object-Oriented Software* (1994)
- Solves the problem of hard-wiring requests into classes, which couples them at compile-time and prevents runtime configuration

## Commands and Syntax

**C++ implementation structure:**
```cpp
// Abstract command interface
class Command {
public:
    virtual void execute() = 0;
    virtual ~Command() = default;
};

// Concrete command binds a Receiver to an action
template <typename Receiver>
class SimpleCommand : public Command {
    using Action = void (Receiver::*)();
    Receiver* receiver;
    Action action;
public:
    SimpleCommand(shared_ptr<Receiver> receiver, Action action);
    void execute() override { (receiver->*action)(); }
};

// Client creates and wires objects
auto receiver = std::make_shared<MyClass>();
auto command = std::make_unique<SimpleCommand<MyClass>>(receiver, &MyClass::action);
command->execute();
```

**Key method signatures:**
- `execute()` — triggers the command's action on the receiver
- `undo()` — reverses the command (for undo support)
- `toScript()` — serializes the command for macro recording

## Relationships

- **Memento pattern**: Often used alongside Command for undo — Memento stores state snapshots while Command stores operations
- **Strategy pattern**: Both encapsulate behavior, but Strategy replaces an algorithm while Command encapsulates a complete request with its receiver
- **Chain of Responsibility**: Can use Command objects as the requests passed along the chain
- **Observer pattern**: Command can serve as the action triggered on notification
- **Composite pattern**: MacroCommand (composite of commands) enables executing multiple commands as one
- **Model-View-Controller**: Commands often wire controller actions to model operations
- **Function objects / Closures**: Command is the OO equivalent of closures in functional languages
- Related patterns: Batch queue, Command queue, Job scheduler, Priority queue

## Exam-Relevant Points

- The Command pattern **decouples the invoker from the receiver** — the invoker knows nothing about the concrete command or how the request is carried out
- **Four participants**: Command, Receiver, Invoker, Client — know which role does what
- **Multi-level undo** is implemented by maintaining a stack of executed command objects; undo pops and calls `undo()` on each
- **Macro recording**: Keeping a list of command objects as they execute enables replay; adding `toScript()` enables scripting
- The pattern enables **transactional behavior** — if one operation in a sequence fails, all can be rolled back
- **Thread pools** use Command: work items in the queue are command objects implementing a common interface (e.g., `java.lang.Runnable`)
- **Progress bars** can use `getEstimatedDuration()` on each command to estimate total work
- **Networking**: Entire command objects can be serialized and sent across a network for remote execution
- The pattern makes it easy to add new commands without changing existing invoker or client code (Open/Closed Principle)
- Historical note: First published mention by Henry Lieberman (1985); first undo/redo mechanism using Command with execute/undo by Bertrand Meyer (1988)
- In Swing/Delphi, the `Action` class is a command object that also carries UI metadata (icon, tooltip, keyboard shortcut)
