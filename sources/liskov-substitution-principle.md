---
source: https://en.wikipedia.org/wiki/Liskov_substitution_principle
fetched: 2026-06-17
---

# Liskov Substitution Principle

## Overview

The **Liskov substitution principle (LSP)** defines a specific subtyping relation called **strong behavioral subtyping**, first introduced by Barbara Liskov in a 1987 keynote address titled *Data abstraction and hierarchy*. The core idea centers on "substitutability" in object-oriented programming -- the notion that a superclass object can be replaced by a subclass object without breaking the program. This is a **semantic** relation rather than a purely syntactic one, aiming to ensure meaningful interoperability among types in a hierarchy.

## Formal Definition

Liskov and Jeannette Wing articulated the principle in their 1994 paper:

> *Subtype Requirement*: Let phi(x) be a property provable about objects x of type T. Then phi(y) should be true for objects y of type S where S is a subtype of T.

Symbolically: if S is a subtype of T (S <= T), then for all properties phi provable of T-objects, those same properties must hold for S-objects. In essence, whatever holds for T must also hold for S.

## Principle Details

### Substitutability

If S is a subtype of T, then objects of type T may be replaced with objects of type S without altering any desirable properties of the program, such as correctness.

### Relation to Type Theory

Behavioral subtyping is stronger than the typical function subtyping from type theory, which only requires **contravariance** of parameter types and **covariance** of return types. Behavioral subtyping is **undecidable** in general -- for example, verifying that a method "always terminates" for some subtype cannot be done algorithmically (this relates to the halting problem). Nonetheless, the principle remains valuable for reasoning about class hierarchy design.

### Signature Requirements

LSP imposes standard requirements on signatures, widely adopted in modern OOP languages:

- **Contravariance** of method parameter types in the subtype
- **Covariance** of method return types in the subtype
- New exceptions thrown by subtype methods must be subtypes of exceptions thrown by supertype methods

### Behavioral Conditions

Beyond signatures, the subtype must satisfy behavioral conditions resembling design by contract methodology:

1. **Preconditions** cannot be strengthened in the subtype
2. **Postconditions** cannot be weakened in the subtype
3. **Invariants** cannot be weakened in the subtype
4. **History constraint** (the "history rule") -- the novel contribution by Liskov and Wing

## The History Constraint

Objects are considered modifiable only through their methods (encapsulation). Since subtypes may introduce new methods not in the supertype, those methods could allow state changes impermissible in the supertype. The history constraint prohibits this.

**Violation example:** Defining a *mutable point* as a subtype of an *immutable point* violates the history constraint, because the immutable point's state never changes after creation, so its history cannot encompass a mutable point's history.

**Permitted example:** A *circle with immutable center and mutable radius* can be a subtype of an *immutable point* without violating the constraint, since the mutable radius field is not observable through the supertype's methods.

## Origins

The pre- and postcondition rules match those from Bertrand Meyer's 1988 book *Object-Oriented Software Construction*. Both Meyer and Pierre America (who coined the term *behavioral subtyping*) provided proof-theoretic definitions, but their formulations didn't account for **aliasing** in languages with references or pointers. Addressing aliasing was the key improvement by Liskov and Wing in 1994, with the history constraint as the essential new ingredient. Under Meyer's and America's earlier definitions, a mutable point *would* qualify as a behavioral subtype of an immutable point -- LSP specifically forbids this.

## Classic Violation Example: Rectangle-Square

The well-known Rectangle-Square problem illustrates an LSP violation.

A Rectangle class has independent setWidth and setHeight methods. A Square class extends Rectangle, overriding both setters so that changing one dimension also changes the other (maintaining the square invariant).

This violates LSP. Consider a function that sets a rectangle's width to 5 and height to 4, then asserts the area equals 20. Passing a Square causes the assertion to fail -- after setHeight(4), both dimensions become 4, yielding area 16 instead of 20.

The article notes a subtlety: the assumption that setHeight() changes height and area but **not** width may itself be invalid -- not just for squares, but for any rectangle variant that might preserve area or aspect ratio when a dimension changes.

## Relation to SOLID

LSP represents the "L" in the SOLID principles of object-oriented design.

## See Also

- Circle-ellipse problem
- Composition over inheritance
- Design by contract
- Hoare logic

## Key References

- Liskov, B. (1987). "Keynote address - data abstraction and hierarchy." *OOPSLA '87 Addendum*.
- Liskov, B. & Wing, J. (1994). "A behavioral notion of subtyping." *ACM TOPLAS*, 16(6): 1811-41.
- Meyer, B. (1988). *Object-oriented Software Construction*. Prentice Hall.
- Martin, R.C. (1996). "The Liskov Substitution Principle." *C++ Report*.
