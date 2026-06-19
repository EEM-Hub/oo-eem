---
source: sources/wiki-Chain-of-responsibility_pattern.md
source_url: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
---

## Chain of Responsibility Pattern

The Chain of Responsibility is a behavioral design pattern from the Gang of Four catalog that decouples the sender of a request from its receiver by passing the request along a chain of potential handlers until one processes it. It promotes loose coupling by eliminating the need for the sender to know which specific object will handle a request.

## Key Concepts

- **Core mechanism**: A source of command objects is passed through a series of processing objects; each either handles the command or forwards it to the next in the chain.
- **Loose coupling**: The sender refers only to an abstract Handler interface, not to any concrete receiver class.
- **Single vs. multiple handling**: The strict GoF definition says exactly one handler processes the request. In practice (loggers, UI events, servlet filters), multiple handlers may each take partial responsibility.
- **Tree of responsibility**: A variation where handlers act as dispatchers, sending commands in multiple directions (not just linearly), forming a tree. Can involve recursion (e.g., XML interpreters).
- **Comparison with Decorator**: Structurally nearly identical. The difference is that Decorator has all classes process the request, while Chain of Responsibility has (strictly) one class handle it.
- **New handlers can be added** to the end of the chain dynamically at runtime.

## Commands and Syntax

**Typical structure (C++ example):**

- Abstract handler (`HelpHandler`) defines the interface and holds a successor pointer:
  ```cpp
  class HelpHandler {
      HelpHandler* successor;
      virtual void handleHelp() const {
          if (successor) successor->handleHelp();
      }
  };
  ```
- Concrete handlers (`Button`, `Dialog`) override `handleHelp()`:
  - If `hasHelp()` is true, handle the request locally.
  - Otherwise, call `HelpHandler::handleHelp()` to forward up the chain.
- Client constructs the chain by linking handlers: `Application -> Dialog -> Button`, then calls `button->handleHelp()`.

**UML structure**: `Sender` -> `Handler` (interface with `handleRequest()`) -> `Receiver1` -> `Receiver2` -> `Receiver3`.

## Relationships

- **Behavioral pattern** — one of the GoF behavioral patterns alongside Command, Iterator, Mediator, Observer, State, Strategy, Template Method, and Visitor.
- **Command pattern** — Chain of Responsibility processes command objects; the two patterns are often used together.
- **Decorator pattern** — structurally nearly identical (both use recursive composition via a common interface), but differ in intent: Decorator wraps to add behavior; Chain of Responsibility forwards to find a handler.
- **Loose coupling** — a core principle this pattern promotes.
- **Single Responsibility Principle** — each handler encapsulates responsibility for one type of request.
- **Composite pattern** — tree-of-responsibility variant resembles Composite's recursive structure.

## Exam-Relevant Points

- **Classification**: Behavioral pattern, one of the 23 GoF patterns.
- **Intent**: Avoid coupling sender to receiver; give more than one object a chance to handle a request by chaining receivers.
- **Strict GoF definition**: Exactly one handler processes the request. Practical implementations often relax this.
- **Key distinction from Decorator**: Decorator — all handlers process; Chain of Responsibility — (strictly) one handler processes.
- **Two problems it solves**: (1) Sender-receiver coupling should be avoided. (2) More than one receiver should be able to handle a request.
- **Real-world example**: Apple's Cocoa/Cocoa Touch responder chain — events propagate from views up through view controllers, windows, to the application object (`NSResponder`/`UIResponder` hierarchy).
- **Participants**: Handler (abstract), ConcreteHandler (handles or forwards), Client/Sender (initiates the request).
- **No guarantee of handling**: If no handler in the chain processes the request, it falls off the end unhandled (unless the last handler is a catch-all).
- **Source**: *Design Patterns: Elements of Reusable Object-Oriented Software* (Gamma et al., 1994), pp. 223ff.
