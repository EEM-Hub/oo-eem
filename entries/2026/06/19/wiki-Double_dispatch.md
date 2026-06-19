---
source: sources/wiki-Double_dispatch.md
source_url: https://en.wikipedia.org/wiki/Double_dispatch
---

## Double Dispatch: Runtime Method Selection on Two Object Types

Double dispatch is a special form of multiple dispatch that selects which concrete function to invoke based on the runtime types of **two** objects involved in a call. In most object-oriented languages, only the receiver's dynamic type drives method selection (single dispatch via virtual functions). Double dispatch extends this to also consider the argument's type, enabling richer polymorphic behavior without resorting to type-checking conditionals.

## Key Concepts

- **Single dispatch** resolves a method call based on the runtime type of one object (the receiver). This is standard virtual function behavior in C++, Java, etc.
- **Double dispatch** resolves based on the runtime types of **two** objects — the receiver and one argument.
- **Multiple dispatch** (as in CLOS) generalizes this to N arguments; double dispatch is the N=2 case.
- Double dispatch is a **workaround** for languages that lack native multiple dispatch — it simulates multi-argument polymorphism through two sequential single-dispatch calls.
- The core technique: object A receives the call, then **calls back** into object B passing `this`/`self`, so B's virtual method resolves on A's actual type. Two vtable lookups occur instead of one.
- **Function overloading is static** (resolved at compile time via name mangling), while **virtual dispatch is dynamic** (resolved at runtime via vtable). Double dispatch requires two dynamic dispatches — overloading alone cannot achieve it.
- Dan Ingalls first described the technique in Smalltalk, calling it **multiple polymorphism**.

## Commands and Syntax

**The "call-back" idiom (C++ / Visitor pattern approach):**

```cpp
// Step 1: Each "argument" type overrides a method that calls back into the "receiver"
class Spaceship {
    virtual void collideWith(Asteroid& asteroid) {
        asteroid.collideWith(*this);  // second dispatch — *this has concrete type
    }
};

// Step 2: The "receiver" has overloaded virtual methods for each argument type
class Asteroid {
    virtual void collideWith(Spaceship&) { /* ... */ }
    virtual void collideWith(ApolloSpacecraft&) { /* ... */ }
};
```

**Ruby example — eliminating type-case with double dispatch:**

```ruby
# Shape delegates to the port, passing itself with a type-specific method name
class Rectangle
  def display_on(port)
    port.display_rectangle(self)  # second dispatch
  end
end

# Each port implements type-specific drawing methods
class PrinterPort
  def display_rectangle(object) ... end
  def display_oval(object) ... end
end
```

**C# shortcut** — cast the argument to `dynamic` to get runtime overload resolution without the visitor pattern.

**Eiffel agent approach** — wraps methods as first-class agent objects, passing them instead of making direct calls, decoupling the two objects entirely.

## Relationships

- **Visitor Pattern**: The primary design pattern used to implement double dispatch in single-dispatch languages. The "accept/visit" protocol is exactly the two-step callback mechanism.
- **Multiple Dispatch**: Double dispatch is a special case (N=2). Languages with native multiple dispatch (CLOS, Julia, Dylan) don't need the workaround.
- **Single Dispatch / Virtual Functions**: The baseline that double dispatch extends. Understanding vtable lookup is prerequisite.
- **Function Overloading**: Static (compile-time) resolution — the key limitation that makes double dispatch necessary. Overloading alone cannot replace it.
- **Virtual Method Table (vtable)**: Double dispatch requires two vtable lookups at runtime, increasing instruction path length slightly.
- **Polymorphism taxonomy**: Double dispatch sits under subtype polymorphism, alongside single dispatch and predicate dispatch.

## Exam-Relevant Points

- **Why overloading fails**: Function overloading resolves on the **static** (declared) type of the argument, not the runtime type. Passing a `Spaceship&` that actually refers to an `ApolloSpacecraft` will call the `Spaceship` overload, not the `ApolloSpacecraft` one.
- **The two-step mechanism**: First dispatch is on the receiver (virtual call), second dispatch is via the callback with `*this` (which carries the concrete type). Both are vtable lookups.
- **Performance cost**: Double dispatch adds one extra dynamic dispatch (vtable lookup) compared to single dispatch. The overhead is proportional to the number of calls, generally modest.
- **Use cases to recognize**: collision detection, rendering/display on heterogeneous outputs, event handling with typed events and typed handlers, scheduling/matching algorithms.
- **Visitor pattern is the standard implementation** of double dispatch in languages like C++ and Java that only support single dispatch natively.
- **C# `dynamic` keyword** provides a language-level alternative to the visitor pattern for achieving double dispatch.
- **Open/closed trade-off**: Adding a new shape type requires adding a method to every port/surface class (and vice versa) — this is the expression problem, which double dispatch does not solve.
