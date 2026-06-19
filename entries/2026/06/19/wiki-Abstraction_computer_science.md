---
source: sources/wiki-Abstraction_computer_science.md
source_url: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
---

## Abstraction in Computer Science

Abstraction is the fundamental technique of providing access to functionality while hiding irrelevant implementation details. It preserves information relevant in a given context and discards what is irrelevant (John V. Guttag). In software, abstractions enable humans to build enormous systems by concentrating on a few issues at a time, manifesting as abstract data types, functions, control structures, and layered architectures.

## Key Concepts

- **Core definition**: Abstraction provides access while hiding details that would make access more challenging; it focuses attention on details of greater importance.
- **Leaky abstractions**: Joel Spolsky's observation that all abstractions are leaky — they can never completely hide underlying details — though this does not negate their usefulness.
- **Control abstraction**: Programming languages abstract away low-level register/binary operations, letting programmers express computation at higher levels (e.g., `a := (1 + 2) * 5` hides binary conversion, assembly instructions, memory addressing).
- **Data abstraction**: Enforces separation between abstract properties of a data type (the interface/contract) and concrete implementation details (which may change without affecting clients). Example: a lookup table can be implemented as a hash table, BST, or linear list.
- **Language abstraction**: The generational progression from machine language → assembly → high-level languages → scripting/DSLs, each serving as a stepping stone.
- **Abstraction gradient**: A concept from the Cognitive Dimensions framework measuring how the level of abstraction in a language affects its usability.
- **Soundness vs. exactness**: Abstractions need not be exact (faithful) but must be sound — they should never give incorrect answers, though they may answer "I don't know."
- **Rice's theorem relevance**: Non-trivial properties of programs are undecidable, making abstraction essential for reasoning about program behavior.

## Commands and Syntax

- **Java abstract class declaration**:
  ```java
  public class Animal extends LivingThing {
      private Location loc;
      private double energyReserves;
      public boolean isHungry() { return energyReserves < 2.5; }
      public void eat(Food food) { energyReserves += food.getCalories(); }
      public void moveTo(Location location) { this.loc = location; }
  }
  ```
- **C++ pure virtual (abstract) syntax**: `function(parameters) = 0;`
- **Java keywords**: `abstract` (for abstract classes/methods), `interface` (for pure abstraction contracts)

## Relationships

- **Encapsulation**: Hides state details; abstraction extends this by associating behavior with data and standardizing type interactions.
- **Polymorphism**: Abstraction proceeding into operations — enabling substitution of different types in the same role.
- **Inheritance / Delegation**: Abstraction proceeding inward, structuring types/classes to simplify complex relationships.
- **Abstract Data Types**: The data-side manifestation of abstraction — separating use from representation.
- **Structured Programming**: Splits complex tasks into smaller pieces with clear flow-control and interfaces, reducing side-effect complexity.
- **Layered Architecture**: Stacks abstraction levels so changes in one layer don't affect others (physical → logical → view in databases).
- **Abstract Interpretation / Model Checking**: Formal methods that use abstraction to reason about program behavior safely.
- **Domain Analysis / OO Analysis**: Determining what to abstract vs. what to expose is the central concern of object-oriented design.

## Exam-Relevant Points

- Abstraction in OOP manifests through three mechanisms: **encapsulation** (hiding state), **polymorphism** (substituting types), and **inheritance/delegation** (structuring type hierarchies).
- **Data abstraction** separates interface (contract) from implementation; changes to implementation should not impact client code — this is the contract principle.
- **Database abstraction levels**: Physical (how data is stored), Logical (what data exists and relationships), View (subset visible to users). The separation between physical and logical is called **physical data independence**.
- **Leaky abstraction** (Spolsky): No abstraction perfectly hides all underlying details — a critical design consideration.
- OO design decisions about **what to abstract** involve three analyses: domain analysis (scope), legacy analysis (interoperability), and detailed OO analysis (class structure).
- Programming language abstraction features: OOP uses `abstract`/`interface` keywords; FP uses lambda abstractions and higher-order functions; Lisp family uses macro systems for syntactic abstraction.
- **Greenspun's Tenth Rule**: Any sufficiently complicated program contains an ad-hoc, informally-specified, bug-ridden, slow implementation of half of Common Lisp — illustrating that complex abstraction architectures are both inevitable and difficult.
