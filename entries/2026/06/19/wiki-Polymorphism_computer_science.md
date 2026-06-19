---
source: sources/wiki-Polymorphism_computer_science.md
source_url: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
---

## Polymorphism in Computer Science

Polymorphism allows a single interface, operation, or symbol to work across multiple types. In object-oriented programming, it is the provision of one interface to entities of different data types. The term originates from biology, where an organism can have many different forms. Polymorphism is central to type theory and programming language design, with three major forms: ad hoc, parametric, and subtyping.

## Key Concepts

- **Polymorphism** — a value, variable, or operation can have or work with more than one type; contrast with **monomorphism**, where every value has exactly one type (Cardelli & Wegner, 1985)
- **Ad hoc polymorphism** — a common interface for an arbitrary set of individually specified types; functions behave *differently* depending on argument type; realized via function overloading and operator overloading; not a fundamental feature of the type system
- **Coercion polymorphism** — implicit type conversion treated as a form of ad hoc polymorphism
- **Parametric polymorphism** — code written generically using abstract type variables, handling values *uniformly* regardless of type; maintains full static type safety; ubiquitous in functional programming (simply called "polymorphism" there); realized via generics/templates in OO languages
- **Polymorphic function** — a function that can evaluate to or be applied to values of different types
- **Polymorphic data type** — a data type parameterized by a type variable (e.g., `List<T>`)
- **Subtype polymorphism** (inclusion polymorphism) — a function accepting type T also accepts any subtype S <: T, governed by the **Liskov Substitution Principle**; usually resolved dynamically
- **Row polymorphism** — operates on structural types; allows usage of values whose types have certain properties without losing remaining type information; distinct from subtyping
- **Polytypism** (data type genericity) — more general than polymorphism; functions defined over the *structure* of data types themselves
- **Rank polymorphism** — defining feature of array programming languages (APL); operations implicitly work on arrays of any shape/dimensionality
- **Parametricity** — the principle that parametrically polymorphic functions are restricted to working on the *shape* of data, not its value (Reynolds, Girard — System F)
- **Virtual table (vtable)** — the implementation mechanism for subtype polymorphism in most OO languages; each class has a function table, each object has a pointer to its class's vtable
- **Late binding** — virtual function calls are not bound until invocation time
- **Single dispatch** — method resolution based only on the receiver object's type (the `this`/`self` argument)
- **Multiple dispatch** — method resolution based on the runtime types of *all* arguments (e.g., Common Lisp Object System)
- **Type variance** and **bounded quantification** — arise from the interaction between parametric polymorphism and subtyping

## Commands and Syntax

**Ad hoc polymorphism (Java — function overloading):**
```java
class AdHocPolymorphic {
    public String add(int x, int y) {
        return String.format("Sum: %d", x + y);
    }
    public String add(String name) {
        return String.format("Added %s", name);
    }
}
```
The compiler treats these as entirely distinct functions despite sharing a name.

**Parametric polymorphism (Haskell):**
```haskell
data List a = Nil | Cons a (List a)

length :: List a -> Integer
length Nil         = 0
length (Cons x xs) = 1 + length xs

map :: (a -> b) -> List a -> List b
map f Nil         = Nil
map f (Cons x xs) = Cons (f x) (map f xs)
```

**Parametric polymorphism (Java generics):**
```java
class List<T> {
    class Node<T> { T elem; Node<T> next; }
    Node<T> head;
    int length() { ... }
}
```

**Subtype polymorphism (Java):**
```java
abstract class Pet { abstract String speak(); }
class Cat extends Pet { String speak() { return "Meow!"; } }
class Dog extends Pet { String speak() { return "Woof!"; } }

static void letsHear(final Pet pet) {
    System.out.println(pet.speak());
}
// Accepts Cat, Dog, or any Pet subtype
```

## Relationships

- **Subtyping ↔ Liskov Substitution Principle** — subtype polymorphism is governed by LSP; S can substitute for T only if LSP holds
- **Subtyping ↔ Inheritance** — OO languages implement subtype polymorphism via subclassing/inheritance, but the concepts are distinct (subtyping is the type relationship; inheritance is the implementation mechanism)
- **Parametric polymorphism ↔ Generics/Templates** — generics (Java, C#, Go) and templates (C++, D) are the OO realization of parametric polymorphism
- **Ad hoc polymorphism ↔ Type classes** — Haskell type classes provide principled ad hoc polymorphism (structured overloading)
- **Parametric + Subtype → Type variance** — combining these two forms introduces covariance, contravariance, and invariance concerns
- **Parametric + Subtype → Bounded quantification** — constraining type parameters with subtype bounds (e.g., `<T extends Comparable<T>>`)
- **Static vs. Dynamic polymorphism** — ad hoc and parametric are typically static (compile-time); subtyping is typically dynamic (runtime via vtable dispatch)
- **Curiously Recurring Template Pattern (CRTP)** — achieves static subtype polymorphism via template metaprogramming, avoiding dynamic dispatch overhead
- **Duck typing** — dynamic polymorphism without explicit type hierarchy; related to row polymorphism
- **Monomorphization** — compiler strategy (C++, Rust) that generates specialized code for each concrete type, enabling static dispatch for parametric polymorphism

## Exam-Relevant Points

- **Three major forms**: ad hoc (overloading), parametric (generics), subtyping (inheritance-based) — know the distinctions cold
- **Strachey's original classification** (1967): ad hoc and parametric as "the two main classes"; subtyping was added later by Cardelli & Wegner (1985)
- **Ad hoc polymorphism is NOT a fundamental feature of the type system** — functions are treated as entirely distinct by the compiler
- **Parametric polymorphism maintains full static type safety** while making the language more expressive
- **Subtype polymorphism follows LSP**: if S <: T, then objects of type S can be used wherever T is expected
- **Static polymorphism** = resolved at compile time (faster, more optimization); **dynamic polymorphism** = resolved at runtime via virtual dispatch (more flexible, supports duck typing)
- **Vtable mechanism**: each class has a vtable of function pointers; each object has a pointer to its class's vtable; this enables late binding and single dispatch
- **Single dispatch** (most OO languages) vs. **multiple dispatch** (CLOS) — single dispatch resolves only on the receiver; multiple dispatch resolves on all argument types
- **Monomorphization** (C++/Rust) vs. **dynamic dispatch for ABI** (Swift) — tradeoff between performance and shared library code size
- **Parametric polymorphism + subtyping** produces type variance and bounded quantification — a common source of exam questions
- **System F** (polymorphic lambda calculus) is the formal foundation of parametric polymorphism (Reynolds, Girard)
- **Coercion polymorphism** (implicit type conversion) is classified as a form of ad hoc polymorphism
- **Historical firsts**: ALGOL 68 for ad hoc polymorphism; ML for parametric polymorphism; Simula for inclusion polymorphism
