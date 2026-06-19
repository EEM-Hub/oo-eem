---
source: sources/wiki-Encapsulation_computer_programming.md
source_url: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)
---

## Encapsulation in Object-Oriented Programming

Encapsulation is a fundamental OOP principle that refers to two related ideas: bundling data together with the methods that operate on that data, and restricting direct access to an object's internal components. It prevents external code from depending on internal implementation details, enabling developers to present a consistent interface while freely changing how things work underneath. Encapsulation is not unique to OOP — abstract data types, modules, libraries, and lexical closures all provide encapsulation.

## Key Concepts

- **Two distinct meanings**: (1) A language mechanism for restricting direct access to an object's components (access control); (2) A language construct that bundles data with the behavior operating on that data (cohesion). These are related but separable concerns.
- **Encapsulation is not information hiding**: Some researchers treat them as the same concept; others distinguish them. In many OOP languages, components are not hidden automatically — hiding is an optional, overridable layer on top of bundling.
- **Protects state invariants**: Hiding internal representation prevents clients from putting an object into an invalid or inconsistent state.
- **Encourages decoupling**: By exposing only a stable interface, encapsulation reduces interdependencies between software components.
- **Promotes cohesion**: Encourages placing all code concerned with a certain set of data in the same class.
- **Encapsulation vs. inheritance tension**: The Gang of Four (Design Patterns) warn that inheritance often breaks encapsulation by exposing a subclass to its parent's implementation details. Designers tend to overuse inheritance. This leads to the yo-yo problem — deep inheritance hierarchies that are hard to follow and debug.
- **Not OOP-exclusive**: Abstract data types, modules, libraries, and closures all provide encapsulation. Programming language theory explains this similarity through existential types.
- **Override mechanisms exist**: Reflection APIs (Java, Ruby, C#), name mangling (Python), and special keywords (`friend` in C++) can bypass access restrictions. Only object-capability model systems guarantee strong encapsulation.

## Commands and Syntax

**Access specifiers by language**:
- **C++**: `public`, `private`, `protected` (ISO C++ calls these "access specifiers," not information-hiding mechanisms). Also supports `friend` for selective access.
- **Java/C#**: `public`, `private`, `protected` keywords on fields and methods.
- **Smalltalk/Ruby**: Only allow access via object methods (no direct field access from outside).
- **Python**: Convention-based — prefix with underscore (`_maxspeed`) for "private." Name mangling with double underscore (`__var`) provides weak protection. No enforced access restriction.
- **C (non-OOP)**: Opaque pointers via header files — declare a `typedef struct Entity Entity;` in the header, define the struct only in the `.c` implementation file. Clients interact only through API functions.

**C opaque type pattern**:
```c
// api.h — public interface
typedef struct Entity Entity;  // opaque forward declaration
Entity* openEntity(int id);
int processEntity(Entity* e);
void closeEntity(Entity* e);

// api.c — hidden implementation
struct Entity { int ent_id; char ent_name[20]; };
```

## Relationships

- **Information Hiding**: A closely related but distinct concept. Encapsulation (bundling) enables information hiding (restricting access), but they are not synonymous.
- **Inheritance**: Tension exists — subclassing can break encapsulation by exposing parent implementation details. Favor composition over inheritance to preserve encapsulation (Gang of Four advice).
- **Coupling/Decoupling**: Encapsulation is a primary technique for achieving loose coupling between components.
- **Abstract Data Types**: The non-OOP predecessor to encapsulation; same principle of hiding representation behind operations.
- **Facade Pattern**: A design pattern that applies encapsulation at the subsystem level — provides a simplified interface over a complex set of classes.
- **Modules and Libraries**: Non-OOP constructs that also provide encapsulation boundaries.
- **Object-Capability Model**: The strongest form of encapsulation, where access rights are tied to object references themselves.

## Exam-Relevant Points

- Encapsulation has **two meanings** that must be distinguished: data bundling and access restriction. Know both.
- **Encapsulation is not the same as information hiding** — Rogers (2001) explicitly argues this distinction. Bundling is structural; hiding is about access control.
- **Inheritance breaks encapsulation** — this is a key Gang of Four insight. Subclasses become coupled to parent implementation details.
- Access specifiers (`public`, `private`, `protected`) are **not** information hiding according to the ISO C++ standard — they are access control. True information hiding in C++ comes from compiled implementations behind header files.
- **Python has no enforced access restriction** — underscore prefix is convention only. Name mangling (`__var`) provides weak protection but is easily circumvented.
- **Smalltalk and Ruby** enforce the strictest OOP encapsulation: all field access must go through methods.
- Encapsulation **is not unique to OOP** — C's opaque pointer pattern, modules, ADTs, and closures all achieve it. Existential types provide the theoretical foundation.
- **Object-capability model** is the only approach that guarantees encapsulation cannot be bypassed (no reflection backdoor).
- Encapsulation **reduces system complexity** and **increases robustness** by limiting interdependencies (though Wikipedia notes this claim needs citation).
