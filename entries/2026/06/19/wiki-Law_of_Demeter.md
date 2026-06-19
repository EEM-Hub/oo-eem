---
source: sources/wiki-Law_of_Demeter.md
source_url: https://en.wikipedia.org/wiki/Law_of_Demeter
---

## Law of Demeter (Principle of Least Knowledge)

The Law of Demeter (LoD) is a design guideline for object-oriented software that restricts which objects a method may interact with. Proposed by Ian Holland in 1987 at Northeastern University as part of the Demeter Project, it is a specific case of loose coupling and aligns with information hiding. The core idea: an object should assume as little as possible about the internal structure of other objects.

## Key Concepts

- **Three summary rules**: (1) Each unit should have limited knowledge about other units — only closely related ones. (2) Only talk to friends, not strangers. (3) Only talk to *immediate* friends.
- **"Use only one dot" heuristic**: `a.m()` is fine; `a.m().n()` violates LoD because it reaches through an intermediate object.
- **Formal rule for method `m` of object `a`** — `m` may only invoke methods on: `a` itself, `m`'s parameters, objects instantiated within `m`, `a`'s direct attributes, and accessible global variables.
- **Dog-walking analogy**: Command the dog to walk, not the dog's legs directly.
- **Relationship to other principles**: LoD is a corollary of information hiding and the principle of least privilege. It is a specific case of loose coupling.
- **Named after Demeter**, Greek goddess of agriculture, reflecting a "growing software" (bottom-up) philosophy rather than "building software."

## Commands and Syntax

No CLI commands — this is a design principle. Code-level examples:

```
// VIOLATES LoD — reaches through b to access c
a.getB().getC().doSomething();

// FOLLOWS LoD — a talks only to its immediate collaborator
a.doSomething();  // internally, a delegates to b, which delegates to c
```

**Fix pattern**: Modify `b`'s interface to serve `a`'s request directly, propagating internally to subcomponents. Alternatively, give `a` a direct reference to `c`.

## Relationships

- **Loose coupling** — LoD is a specific case; following it reduces coupling between classes.
- **Information hiding** — LoD enforces information hiding by preventing knowledge of internal object structure.
- **Facade pattern** — Facades are a structural mechanism for applying LoD at the subsystem level.
- **Multilayered architecture** — Layered architectures systematically implement LoD; "layer skipping" violates it.
- **Aspect-oriented programming (AOP)** — The Demeter Project birthed both LoD and AOP ideas; AOP is proposed as a solution to LoD's wrapper method proliferation.
- **Single-responsibility principle** — Complementary; both constrain what a unit should know and do.
- **Tell, Don't Ask** — Closely related idiom that reinforces LoD by pushing behavior to the object that owns the data.

## Exam-Relevant Points

- **LoD restricts method calls to five categories**: self, parameters, locally created objects, direct attributes, and accessible globals.
- **Trade-off**: Following LoD increases maintainability and adaptability but can increase Weighted Methods per Class (WMC) due to wrapper/delegation methods — and higher WMC correlates with more bugs (Basili et al., 1996).
- **Lower Response For a Class (RFC)** from LoD compliance reduces bug probability.
- **"Don't talk to strangers"** is an alternate name (per Larman's *Applying UML and Patterns*).
- **Wide interfaces are a misapplication**, not a consequence of LoD — if a wrapper method is needed, the wrapped object should have been a direct dependency.
- **Layered architectures** are a systematic application of LoD; code may only call within its layer or the next layer down.
- **Origin**: 1987, Ian Holland, Demeter Project, Northeastern University.
