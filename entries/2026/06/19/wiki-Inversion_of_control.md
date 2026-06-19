---
source: sources/wiki-Inversion_of_control.md
source_url: https://en.wikipedia.org/wiki/Inversion_of_control
---

## Inversion of Control (IoC) in Object-Oriented Design

Inversion of Control is a design principle where custom-written code receives flow of control from an external source (typically a framework) rather than directing it. In traditional procedural programming, application code calls library code; with IoC, the framework calls the application code. This principle is foundational to modern frameworks for GUIs, web applications, and event-driven systems.

## Key Concepts

- **Core definition**: Custom code yields control flow to a framework — the framework decides *when* to call your code, not the other way around
- **"Hollywood Principle"**: "Don't call us, we'll call you" — the framework dictates execution flow
- **Two distinct meanings in practice**:
  - **Original meaning**: Framework controls execution flow (callbacks, event loops, template methods)
  - **Java community meaning**: Framework controls dependency resolution (IoC containers, dependency injection) — this is a narrower, separate sense
- **Traditional vs. IoC**: In traditional programming, `main()` calls library functions and blocks for input; with IoC, the framework monitors inputs and invokes registered handlers
- **Run-time binding**: IoC enables dynamic flow through abstractions — the concrete object satisfying a dependency is determined at runtime, not compile time
- **Compatible interfaces required**: Objects must possess compatible interfaces (e.g., class A delegates to interface I, implemented by class B)
- **Independent development**: Reusable framework code and problem-specific code are developed independently but operate together

## Commands and Syntax

**HTML DOM event registration (IoC via callbacks):**
```javascript
document.addEventListener("click", listener, true);
```
The browser framework controls the event loop; custom code only supplies the handler.

**ASP.NET Core endpoint registration (IoC via routing):**
```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();
app.MapGet("/", () => "Hello World!");
app.Run();  // control passes to the framework
```
The application registers endpoints; the framework handles HTTP dispatch.

## Relationships

- **Dependency Injection**: A specific technique for achieving IoC over dependency resolution (not control flow) — often conflated with IoC in Java ecosystems (Spring Framework)
- **Service Locator Pattern**: Alternative to DI for achieving runtime binding of dependencies
- **Event-Driven Programming**: Frequently implemented using IoC — custom code handles events while the framework manages the event loop and dispatch
- **Template Method Pattern**: A GoF behavioral pattern that embodies IoC — the base class controls the algorithm skeleton, subclasses fill in steps
- **Callbacks**: The most basic mechanism for IoC — passing a function to be called by the framework
- **Dependency Inversion Principle (DIP)**: Related but distinct — DIP is about depending on abstractions; IoC is about who controls the flow
- **Observer Pattern / Publish-Subscribe**: Patterns where the framework or mediator controls notification flow
- **Software Frameworks vs. Libraries**: The defining distinction — a library is called by your code; a framework calls your code (IoC)
- **Late Binding**: The runtime mechanism that makes IoC's dynamic flow possible

## Exam-Relevant Points

- IoC **inverts** the traditional relationship: instead of application code calling reusable code, the reusable framework calls the application code
- The term dates to **1988** but relates to Michael Jackson's "program inversion" concept from the **1970s**
- **Dependency injection is NOT the same as IoC** — DI is one specific pattern often associated with IoC containers, but IoC originally refers to control flow inversion
- **Callbacks, schedulers, event loops, and template method** are all design patterns that follow the IoC principle
- IoC makes frameworks **extensible** — the framework provides the skeleton, application code fills in behavior
- In **event-driven programming** with IoC, custom code handles events while the event loop and dispatch are handled by the framework; in web frameworks, dispatch is called **routing** and handlers are called **endpoints**
- Key frameworks using IoC: **Spring Framework** (Java), **ASP.NET Core** (.NET), **Mesa** (1985, one of the earliest)
- IoC requires objects to have **compatible interfaces** for runtime binding
- The distinction between a **library** and a **framework** is precisely IoC: libraries are called by your code; frameworks call your code
