---
source: sources/wiki-Delegation_object-oriented_programming.md
source_url: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
---

## Delegation in Object-Oriented Programming

Delegation is a mechanism where evaluating a member (property or method) of one object (the receiver) occurs in the context of another object (the sender). It is the fundamental method for behavior reuse in prototype-based programming, analogous to inheritance in class-based programming. The critical distinction from forwarding is that delegation involves **late binding of `self`** — when a delegated method references `self`/`this`, it resolves to the *original* sending object, not the receiving object.

## Key Concepts

- **Delegation** evaluates a member of the receiver in the context of the sender; `self` in the receiver's method refers back to the original sender
- **Late binding of self** is the defining characteristic: `self` is not statically bound at definition time but dynamically bound at evaluation time to the original object
- **Forwarding** is distinct from delegation — in forwarding, the wrapper does *not* pass itself to the wrapped object; `self` refers to the receiver, not the sender
- **Consultation/aggregation** is simply using another object, with no special `self` rebinding
- **Explicit delegation** manually passes responsibilities between objects; works in any OO language
- **Implicit delegation** uses language-level method lookup rules; requires language support (Self, JavaScript)
- **Object schizophrenia** — the ambiguity of `this`/`self` that arises when delegation causes `self` in one object to refer to a different object
- Delegation operates on **instances at runtime**, while inheritance typically operates on **types at compile time**
- Delegation can be added or removed at runtime and can affect only a subset of instances
- **Dual inheritance** — when a language supports both delegation and inheritance simultaneously, requiring additional method lookup rules to resolve ambiguity
- Delegation depends on **dynamic binding** — the ability for a method call to invoke different code segments at runtime

## Commands and Syntax

**Delegation example (pseudocode):**
```java
class A {
    void foo() { this.bar(); }
    void bar() { print("a.bar"); }
}
class B {
    private delegate A a;
    public B(A a) { this.a = a; }
    void foo() { a.foo(); }
    void bar() { print("b.bar"); }
}
b = new B(new A());
b.foo(); // prints "b.bar" — self in A.foo() resolves to b
```

**Equivalent with inheritance:**
```java
class A {
    void foo() { this.bar(); }
    void bar() { print("A.bar"); }
}
class B extends A {
    void foo() { super.foo(); }
    void bar() { print("B.bar"); }
}
b = new B();
b.foo(); // prints "B.bar" — this is unambiguous, only one object
```

**Dual inheritance:**
```java
class C extends A {
    delegationlink D d;
}
```

## Relationships

- **Inheritance** — delegation is the prototype-based analog; some authors consider them equivalent or one a special case of the other (Stein 1987: "Delegation is Inheritance")
- **Forwarding** — commonly confused with delegation; forwarding does *not* rebind `self` to the sender
- **Prototype-based programming** (Self, JavaScript) — delegation is the primary reuse mechanism, replacing class-based inheritance
- **Delegation pattern** — a design pattern for implementing delegation explicitly in languages lacking native support
- **Aggregation** — using another object without `self` rebinding; weaker coupling than delegation
- **Role-oriented programming** — has utilized delegation (though older implementations actually used aggregation)
- **Aspect-oriented programming** — delegation proposed for advice resolution (Ernst & Lorenz, 2003)
- **Cocoa/NeXTStep** — macOS uses delegation extensively for customizing framework component behavior (e.g., `windowShouldClose:`)

## Exam-Relevant Points

- **Delegation vs. forwarding**: delegation rebinds `self` to the sender; forwarding does not — this is the key distinguishing test
- **Delegation vs. inheritance**: delegation is per-instance and runtime; inheritance is per-type and compile-time
- In the delegation code example, `b.foo()` prints **"b.bar"** because `this` in `A.foo()` refers to the original sender `b`, not the receiver `a`
- Inheritance can be statically type-checked; delegation generally cannot without generics
- Delegation is sometimes called "run-time inheritance for specific objects"
- Lieberman (1986) defined delegation as a language feature; Self and JavaScript are the best-known languages with native support
- Dual inheritance (delegation + inheritance together) introduces method lookup ambiguity requiring resolution rules
- The delegation pattern (GoF) is an explicit implementation strategy; it should not be confused with language-level delegation support
