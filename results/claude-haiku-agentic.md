# Exam Results: oo-design-practice.md

**Date:** 2026-06-22 14:46
**Model:** claude:haiku
**Score:** 37/40 (92%)

## Per-Question Results

- **Q1**: CORRECT — Which GoF principle states "Favor object composition over class inheritance"?
- **Q2**: CORRECT — What problem does the Abstract Factory pattern solve?
- **Q3**: CORRECT — Which pattern converts the interface of a class into another interface clients expect?
- **Q4**: CORRECT — What distinguishes Decorator from Adapter?
- **Q5**: WRONG — Which SOLID principle states "A module should be responsible to one, and only one, actor"?
  - Expected: c
  - Got: I'll search the belief database for information about SOLID principles and the Single Responsibility
- **Q6**: CORRECT — What is the key difference between Strategy and State patterns?
- **Q7**: CORRECT — Which pattern's AST is an instance of the Composite pattern?
- **Q8**: CORRECT — What does the Liskov Substitution Principle require?
- **Q9**: CORRECT — Which pattern provides a unified interface to a set of interfaces in a subsystem?
- **Q10**: CORRECT — What is the main drawback of the Singleton pattern?
- **Q11**: CORRECT — Which pattern encapsulates a request as an object, enabling undo/redo?
- **Q12**: CORRECT — What does the Dependency Inversion Principle state?
- **Q13**: CORRECT — Which pattern uses double dispatch to separate algorithms from object structures?
- **Q14**: CORRECT — What problem does the Bridge pattern solve?
- **Q15**: CORRECT — Which pattern defines a one-to-many dependency so that when one object changes state, all dependents are notified?
- **Q16**: CORRECT — What is the Interface Segregation Principle?
- **Q17**: CORRECT — What distinguishes Proxy from Decorator?
- **Q18**: CORRECT — Which creational pattern creates objects by cloning a prototypical instance?
- **Q19**: CORRECT — What is the relationship between Template Method and the Hollywood Principle?
- **Q20**: CORRECT — Why does inheritance break encapsulation according to the GoF?
- **Q21**: CORRECT — Which pattern separates the construction of a complex object from its representation?
- **Q22**: CORRECT — What is the Mediator pattern's main tradeoff?
- **Q23**: CORRECT — Which GoF pattern category has the most patterns (11)?
- **Q24**: CORRECT — What does the Open-Closed Principle state?
- **Q25**: CORRECT — Which structural pattern shares object state to support large numbers of fine-grained objects efficiently?
- **Q26**: CORRECT — What is the key difference between Facade and Mediator?
- **Q27**: CORRECT — Which pattern lets you traverse elements of a collection without exposing the underlying representation?
- **Q28**: CORRECT — What does Memento capture?
- **Q29**: CORRECT — How does Factory Method differ from Abstract Factory?
- **Q30**: CORRECT — What is the Composite pattern's key structural feature?
- **Q31**: CORRECT — Which design principle was originated by Parnas in 1972?
- **Q32**: CORRECT — What does the Law of Demeter restrict?
- **Q33**: WRONG — In the Observer pattern, what distinguishes it from Publish-Subscribe?
  - Expected: b
  - Got: Let me search the belief database for information about Observer and Publish-Subscribe patterns:

``
- **Q34**: CORRECT — What is delegation's relationship to inheritance?
- **Q35**: CORRECT — Which GRASP principle assigns responsibility to the class with the most information needed to fulfill it?
- **Q36**: CORRECT — What problem does the Chain of Responsibility pattern solve?
- **Q37**: CORRECT — Peter Norvig observed that how many of the 23 GoF patterns are simplified or eliminated in dynamic languages?
- **Q38**: WRONG — What is the canonical violation example for the Liskov Substitution Principle?
  - Expected: b
  - Got: a
- **Q39**: CORRECT — Which pattern allows an object to alter its behavior when its internal state changes, appearing to change its class?
- **Q40**: CORRECT — What are the three major forms of polymorphism?

## Wrong Answers (Detail)

### Q5: Which SOLID principle states "A module should be responsible to one, and only one, actor"?
- a) Open-Closed Principle
- b) Liskov Substitution Principle
- c) Single Responsibility Principle **<--**
- d) Interface Segregation Principle
- **Expected:** c
- **Got:** I'll search the belief database for information about SOLID principles and the Single Responsibility
- **Objective:** SOLID Principles

**Model response:**

```

```

### Q33: In the Observer pattern, what distinguishes it from Publish-Subscribe?
- a) Observer uses a message broker, Pub-Sub does not
- b) Observer couples subjects and observers directly, Pub-Sub decouples via a broker **<--**
- c) Observer is asynchronous, Pub-Sub is synchronous
- d) They are identical patterns
- **Expected:** b
- **Got:** Let me search the belief database for information about Observer and Publish-Subscribe patterns:

``
- **Objective:** Behavioral Patterns

**Model response:**

```

```

### Q38: What is the canonical violation example for the Liskov Substitution Principle?
- a) Circle-Ellipse
- b) Rectangle-Square **<--**
- c) Animal-Dog
- d) Stack-Array
- **Expected:** b
- **Got:** a
- **Objective:** SOLID Principles

**Model response:**

```
The belief database confirms that the Liskov Substitution Principle is violated by the circle-ellipse problem with mutable objects. This is the classic example used to illustrate LSP violations: a circle cannot be correctly substituted for an ellipse because setting the width and height independently on an ellipse (via inherited setters) violates the mathematical contract that a circle's dimensions must remain equal.
```


## By Objective

- **SOLID Principles**: 4/6 (66%)
- **Behavioral Patterns**: 11/12 (91%)
- **Core OO Principles**: 6/6 (100%)
- **Creational Patterns**: 5/5 (100%)
- **Structural Patterns**: 8/8 (100%)
- **Related Principles**: 3/3 (100%)
