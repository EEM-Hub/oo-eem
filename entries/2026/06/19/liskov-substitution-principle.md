---
source: sources/liskov-substitution-principle.md
source_url: https://en.wikipedia.org/wiki/Liskov_substitution_principle
---

## Liskov Substitution Principle (LSP)

The Liskov Substitution Principle defines **strong behavioral subtyping**: a subclass must be substitutable for its superclass without breaking program correctness. Introduced by Barbara Liskov in 1987 and formalized with Jeannette Wing in 1994, LSP is a **semantic** constraint on type hierarchies — not merely syntactic — and represents the "L" in SOLID.

## Key Concepts

- **Substitutability**: Objects of type T may be replaced with objects of subtype S without altering desirable program properties (correctness, etc.)
- **Formal definition**: If S ≤ T, then every property provable about T-objects must also hold for S-objects
- **Stronger than type-theoretic subtyping**: Goes beyond covariance/contravariance of signatures to require behavioral compatibility
- **Undecidable in general**: Full behavioral subtyping cannot be verified algorithmically (relates to the halting problem), but remains a powerful design reasoning tool
- **Signature requirements**:
  - Contravariance of method parameter types in the subtype
  - Covariance of method return types in the subtype
  - New exceptions must be subtypes of supertype exceptions
- **Behavioral conditions** (from design by contract):
  1. Preconditions cannot be **strengthened** in the subtype
  2. Postconditions cannot be **weakened** in the subtype
  3. Invariants cannot be **weakened** in the subtype
  4. The **history constraint** must be satisfied (Liskov & Wing's novel contribution)
- **History constraint**: Subtypes may not introduce methods that allow state changes impermissible in the supertype. Encapsulation means objects are only modifiable through their methods; new subtype methods must not permit histories that the supertype's contract forbids.

## Commands and Syntax

No commands per se, but the canonical violation pattern:

```
class Rectangle:
    setWidth(w)   — sets width independently
    setHeight(h)  — sets height independently

class Square extends Rectangle:
    setWidth(w)   — sets BOTH width and height to w
    setHeight(h)  — sets BOTH width and height to h
```

A function expecting Rectangle behavior (`setWidth(5); setHeight(4); assert area == 20`) fails when given a Square (area becomes 16). The implicit postcondition — that `setHeight` does not modify width — is violated.

## Relationships

- **Design by Contract** (Bertrand Meyer): LSP's pre/postcondition and invariant rules directly mirror DbC methodology. Meyer's original formulation lacked handling for aliasing.
- **SOLID Principles**: LSP is the "L" — it constrains how inheritance hierarchies should be structured to maintain correctness.
- **Composition over Inheritance**: LSP violations are a primary motivation for preferring composition; when substitutability cannot be maintained, inheritance is the wrong tool.
- **Circle-Ellipse Problem**: The geometric analogue of Rectangle-Square; same structural violation pattern.
- **Hoare Logic**: The formal reasoning framework underlying pre/postcondition verification.
- **Open/Closed Principle**: LSP enables OCP — if subtypes are safely substitutable, systems can be extended without modification.
- **Type Theory**: LSP goes beyond standard function subtyping (which only requires variance rules) to impose behavioral constraints.

## Exam-Relevant Points

- **Preconditions cannot be strengthened; postconditions and invariants cannot be weakened** — the most commonly tested behavioral conditions
- The **history constraint** is Liskov & Wing's unique contribution beyond Meyer's earlier work; it addresses aliasing in languages with references/pointers
- **Mutable point as subtype of immutable point** violates the history constraint (classic exam example)
- **Rectangle-Square** is the canonical violation example: Square's setters break Rectangle's implicit postcondition that dimensions are independent
- Behavioral subtyping is **undecidable** — you cannot algorithmically verify full LSP compliance
- **Contravariance of parameters, covariance of returns** — the signature-level requirements
- LSP is a **semantic** relation, not just syntactic — correct signatures alone are insufficient
- The subtlety in Rectangle-Square: the assumption that `setHeight` doesn't change width may itself be an unstated postcondition, revealing that the real issue is poorly specified contracts
