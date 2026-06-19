---
source: sources/wiki-Class_computer_programming.md
source_url: https://en.wikipedia.org/wiki/Class_(computer_programming)
---

## Classes in Object-Oriented Programming

A class is a syntactic entity structure used to create objects in programming. It encapsulates shared state (variables) and behavior (methods), which may be associated with a particular object instance or with all objects of that class. Classes originated in Simula in the 1960s, drawing on the block concept from ALGOL, and remain foundational to object-oriented programming.

## Key Concepts

- **Class vs. Instance**: Object state differs between instances; class state is shared across all instances. Object methods receive an implicit or explicit reference to the object; class methods do not.
- **Instantiation**: Objects are constructed from classes — memory is allocated, state is initialized, and a reference is returned. Objects exist until destroyed (memory de-allocated).
- **Constructor/Destructor**: Most languages allow custom logic at object lifecycle events via constructors and destructors.
- **Type vs. Class**: A class is a concrete implementation (data structure + subroutines); a type is an interface. Different classes can produce objects of the same abstract type (e.g., `SmallStack` and `ScalableStack` both implementing `Stack`).
- **Structure (Fields)**: Classes contain data fields (also called properties, attributes, or member variables). These define the memory layout of instances in most languages; Python uses associative key-value containers instead.
- **Behavior (Methods)**: Methods are subroutines that operate on objects or classes. They may alter state or provide access to it.
- **Interface**: Every class implements an interface by providing structure and behavior. The public members (methods + attributes) form the class's interface.
- **Invariants**: Some languages (e.g., Eiffel) support class invariants enforced by the type system. Encapsulation is necessary to enforce invariants.

## Access Specifiers

- **Private** — accessible only within the same class
- **Protected** — accessible by the class and its subclasses
- **Public** — accessible by any code
- **Instance-based** (Ruby) — restricts based on the instance, not the class
- **Friend** (C++) — explicitly grants access to designated external functions
- **Path-based** (Java) — restricts access within a package (logical path)

Access specifiers do not necessarily control visibility — a private member may be visible but not usable by client code.

## Inheritance and Relationships

- **Is-a (Hierarchical)**: Subclass derives from a superclass, inheriting structure and behavior. `Button` is-a `Control`. Derived classes specialize by adding or overriding members.
- **Has-a (Compositional)**: A class contains instances of other classes. `Car` has-an `Engine`. Containment by value ties lifetimes; containment by reference does not.
- **Common error**: Confusing "part-of" with "is-a." An engine is part of a car, not a subclass of car.
- **Single vs. Multiple Inheritance**: Java allows implementing multiple interfaces but inheriting from only one class. With multiple inheritance, hierarchy is a DAG; with single, it's a tree.
- **Top type**: In purely OO languages (Java, C#), all classes implicitly extend a root `Object` class.

## Class Taxonomy

| Category | Description |
|----------|-------------|
| **Abstract** | Cannot be instantiated directly; may contain abstract methods. Keyword: `abstract` (Java/C#/PHP), pure virtual functions (C++) |
| **Concrete** | Can be instantiated directly |
| **Final/Sealed** | Cannot be subclassed. `final` (Java/C++/PHP), `sealed` (C#), default in Kotlin |
| **Inner class** | Defined within another class; not necessarily tied to enclosing instance lifecycle |
| **Local class** | Defined within a procedure/function; name scoped to that block |
| **Metaclass** | A class whose instances are themselves classes (Python, Ruby, Smalltalk, CLOS) |

## Commands and Syntax

```objc
// Composition example (Objective-C)
@interface Car : NSObject
@property NSString *name;
@property Engine *engine;
@property NSArray *tires;
@end

// Inheritance chain (Objective-C, iOS SDK)
@interface UIResponder : NSObject
@interface UIView : UIResponder
@interface UIScrollView : UIView
@interface UITableView : UIScrollView
```

## Relationships

- **Inheritance** connects to polymorphism, method overriding, and the Liskov Substitution Principle
- **Composition** connects to object lifetime management and the "favor composition over inheritance" principle
- **Interfaces** bridge abstract types and concrete implementations — central to dependency inversion
- **Metaclasses** connect to metaobject protocols (MOPs) and reflective programming
- **UML modeling** formalizes class relationships with association roles, multiplicity, and directionality
- **Access specifiers** connect to encapsulation and information hiding principles

## Exam-Relevant Points

- A class defines implementation; a type defines interface — they are distinct concepts
- Object state is per-instance; class state is shared across all instances
- "Is-a" = inheritance (hierarchical); "Has-a" = composition — never confuse "part-of" with subclassing
- Abstract classes cannot be instantiated; concrete classes can; final classes cannot be subclassed
- In Java: multiple interface implementation is allowed, but only single class inheritance
- With single inheritance the hierarchy is a tree; with multiple inheritance it is a DAG
- Access specifiers: private (class only), protected (class + subclasses), public (all)
- Access does not equal visibility — private members may be visible but not usable
- A pure abstract base class (C++) containing only pure virtual methods is equivalent to an interface
- Metaclasses are classes whose instances are classes (Python, Ruby, Smalltalk)
- Constructors and destructors handle object lifecycle events at instantiation and destruction
- Encapsulation of state is required to enforce class invariants
