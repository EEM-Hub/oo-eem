---
source: sources/wiki-Interface_object-oriented_programming.md
source_url: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
---

## Interfaces in Object-Oriented Programming

An interface (also called a protocol type) is a data type that acts as an abstraction of a class. It describes a set of method signatures whose implementations may be provided by multiple, otherwise unrelated classes. A class that provides the methods listed in an interface is said to *implement* the interface (or *adopt* the protocol). Interfaces are a core mechanism for achieving encapsulation and reducing coupling between components.

## Key Concepts

- **Interface as abstraction**: An interface defines *what* a type can do (method signatures) without specifying *how* (implementation). It is an abstraction of a class.
- **Implementation/adoption**: A class that provides the methods declared in an interface is said to implement (Java terminology) or adopt (Swift/protocol terminology) it.
- **Encapsulation and decoupling**: Interfaces allow code to depend on capabilities rather than concrete types, reducing coupling. A sorting method needs only `Comparable`, not knowledge of the class internals.
- **Multiple interface implementation**: A single class can implement multiple interfaces (e.g., `Bird implements Flyable, Vocal`), providing a form of multiple behavioral inheritance without the diamond problem of multiple class inheritance.
- **Relationship to abstract classes**: In languages supporting multiple inheritance (e.g., C++), interfaces are typically represented as pure abstract classes (all methods are abstract, no state).
- **Duck typing**: In languages without explicit interface syntax (e.g., Python), interfaces exist as conventions — any class implementing the expected methods satisfies the contract implicitly.
- **Language-specific terminology**: Java uses "interface," Swift/Objective-C use "protocol," Rust uses "trait," Haskell uses "type class," ML/OCaml use "module signature."
- **Traits (Rust)**: Structs do not contain methods directly; methods are added via `impl` blocks, and trait implementations are separate `impl TraitName for StructName` blocks.
- **Concepts (C++)**: C++20 concepts resemble Go-style interfaces — any type (not just classes) can satisfy a concept if it meets all requirements, without explicit inheritance.

## Commands and Syntax

**Java interface declaration and implementation:**
```java
interface Flyable {
    void fly();
}
interface Vocal {
    void vocalize();
}
public class Bird extends Theropod implements Flyable, Vocal {
    public void fly() { ... }
    public void vocalize() { ... }
}
```
- `interface` keyword declares the contract
- `implements` keyword on the class, comma-separated for multiple interfaces
- A class can `extend` one class and `implement` many interfaces simultaneously

**Rust trait declaration and implementation:**
```rust
trait Pet {
    fn speak(&self);
}
struct Dog { name: String }
impl Pet for Dog {
    fn speak(&self) {
        println!("{} says 'Woof!'", self.name);
    }
}
```
- `trait` keyword declares the interface
- `impl TraitName for StructName` provides the implementation separately from the struct definition
- Non-trait methods use plain `impl StructName` blocks

**Python implicit interface (duck typing):**
```python
class MyIterable:
    def __iter__(self):
        ...  # any class with __iter__ is iterable
```
- Can also explicitly subclass an ABC: `collections.abc.Iterable`

## Relationships

- **Abstract classes**: Interfaces are the fully abstract case — no implementation, no state. Abstract classes may provide partial implementations. In C++, interfaces are modeled as abstract classes with all pure virtual methods.
- **Inheritance vs. interfaces**: Inheritance models "is-a" relationships between classes; interfaces model "can-do" capabilities. A class inherits from one superclass but may implement many interfaces.
- **Polymorphism**: Interfaces enable subtype polymorphism — code written against an interface works with any implementing class.
- **Duck typing**: The implicit, convention-based counterpart to explicit interfaces. Same concept, enforced at runtime rather than compile time.
- **Type classes (Haskell) and concepts (C++)**: Serve similar purposes to interfaces but operate outside a class hierarchy — any type satisfying the constraints qualifies.
- **Coupling and dependency inversion**: Interfaces are the mechanism behind the Dependency Inversion Principle (depend on abstractions, not concretions).
- **Delegation**: Related pattern where an object forwards behavior to a delegate that implements an interface.

## Exam-Relevant Points

- An interface defines method signatures only — no implementation, no instance state.
- A class can implement multiple interfaces but (in single-inheritance languages like Java) extend only one class.
- Interfaces reduce coupling by allowing code to depend on abstractions rather than concrete classes.
- In C++, interfaces are represented as abstract classes with all pure virtual methods; C++20 adds concepts as an alternative.
- Rust uses `trait` instead of `interface`; traits are implemented in separate `impl` blocks, not inside the struct.
- Python supports interfaces through duck typing (implicit) and Abstract Base Classes (explicit, e.g., `collections.abc`).
- The terms "interface" (Java family) and "protocol" (Swift/Objective-C) refer to the same concept.
- Interfaces are central to the Dependency Inversion Principle and the Strategy, Observer, and other design patterns.
