# OO Design Practice Exam

## Q1: Which GoF principle states "Favor object composition over class inheritance"?
- a) Program to an interface, not an implementation
- b) Favor object composition over class inheritance
- c) Depend on abstractions, not concretions
- d) Encapsulate what varies
Answer: b
Objective: Core OO Principles

## Q2: What problem does the Abstract Factory pattern solve?
- a) Creating a single complex object step by step
- b) Creating families of related objects without specifying concrete classes
- c) Cloning existing objects to create new ones
- d) Ensuring only one instance of a class exists
Answer: b
Objective: Creational Patterns

## Q3: Which pattern converts the interface of a class into another interface clients expect?
- a) Bridge
- b) Proxy
- c) Adapter
- d) Decorator
Answer: c
Objective: Structural Patterns

## Q4: What distinguishes Decorator from Adapter?
- a) Decorator changes the interface, Adapter preserves it
- b) Decorator adds responsibilities, Adapter converts interfaces
- c) Decorator uses inheritance, Adapter uses composition
- d) Decorator is behavioral, Adapter is creational
Answer: b
Objective: Structural Patterns

## Q5: Which SOLID principle states "A module should be responsible to one, and only one, actor"?
- a) Open-Closed Principle
- b) Liskov Substitution Principle
- c) Single Responsibility Principle
- d) Interface Segregation Principle
Answer: c
Objective: SOLID Principles

## Q6: What is the key difference between Strategy and State patterns?
- a) Strategy uses inheritance, State uses composition
- b) Strategy is selected by the client, State transitions are initiated by the concrete states
- c) Strategy is structural, State is behavioral
- d) Strategy is for algorithms, State is for data
Answer: b
Objective: Behavioral Patterns

## Q7: Which pattern's AST is an instance of the Composite pattern?
- a) Visitor
- b) Command
- c) Interpreter
- d) Chain of Responsibility
Answer: c
Objective: Behavioral Patterns

## Q8: What does the Liskov Substitution Principle require?
- a) Interfaces should be segregated by client needs
- b) High-level modules should not depend on low-level modules
- c) Objects of a derived class must be substitutable for objects of the base class
- d) Classes should be open for extension but closed for modification
Answer: c
Objective: SOLID Principles

## Q9: Which pattern provides a unified interface to a set of interfaces in a subsystem?
- a) Adapter
- b) Proxy
- c) Facade
- d) Bridge
Answer: c
Objective: Structural Patterns

## Q10: What is the main drawback of the Singleton pattern?
- a) It requires too much memory
- b) It introduces global state and tight coupling, making testing difficult
- c) It cannot be implemented in most languages
- d) It only works with inheritance
Answer: b
Objective: Creational Patterns

## Q11: Which pattern encapsulates a request as an object, enabling undo/redo?
- a) Strategy
- b) Observer
- c) Command
- d) Memento
Answer: c
Objective: Behavioral Patterns

## Q12: What does the Dependency Inversion Principle state?
- a) Dependencies should be injected via constructors
- b) High-level modules should not depend on low-level modules; both should depend on abstractions
- c) Modules should depend on concrete implementations for performance
- d) Dependencies should flow from low-level to high-level modules
Answer: b
Objective: SOLID Principles

## Q13: Which pattern uses double dispatch to separate algorithms from object structures?
- a) Strategy
- b) Iterator
- c) Visitor
- d) Observer
Answer: c
Objective: Behavioral Patterns

## Q14: What problem does the Bridge pattern solve?
- a) Converting one interface to another
- b) Decoupling an abstraction from its implementation to avoid class explosion
- c) Adding responsibilities to objects dynamically
- d) Providing a surrogate for another object
Answer: b
Objective: Structural Patterns

## Q15: Which pattern defines a one-to-many dependency so that when one object changes state, all dependents are notified?
- a) Mediator
- b) Command
- c) Observer
- d) Chain of Responsibility
Answer: c
Objective: Behavioral Patterns

## Q16: What is the Interface Segregation Principle?
- a) Interfaces should inherit from a single base interface
- b) No code should be forced to depend on methods it does not use
- c) Every interface should have exactly one method
- d) Interfaces should be public, implementations private
Answer: b
Objective: SOLID Principles

## Q17: What distinguishes Proxy from Decorator?
- a) Proxy adds behavior, Decorator controls access
- b) Proxy controls access, Decorator adds behavior
- c) Proxy changes the interface, Decorator preserves it
- d) Proxy is behavioral, Decorator is structural
Answer: b
Objective: Structural Patterns

## Q18: Which creational pattern creates objects by cloning a prototypical instance?
- a) Factory Method
- b) Abstract Factory
- c) Builder
- d) Prototype
Answer: d
Objective: Creational Patterns

## Q19: What is the relationship between Template Method and the Hollywood Principle?
- a) Template Method violates the Hollywood Principle
- b) Template Method embodies inversion of control — the framework calls subclass methods, not the reverse
- c) They are unrelated concepts
- d) The Hollywood Principle is a synonym for Template Method
Answer: b
Objective: Behavioral Patterns

## Q20: Why does inheritance break encapsulation according to the GoF?
- a) Subclasses can access private members of the parent
- b) Subclasses are exposed to implementation details of the parent class, creating tight coupling
- c) Inheritance forces all methods to be public
- d) Inheritance prevents polymorphism
Answer: b
Objective: Core OO Principles

## Q21: Which pattern separates the construction of a complex object from its representation?
- a) Abstract Factory
- b) Prototype
- c) Builder
- d) Factory Method
Answer: c
Objective: Creational Patterns

## Q22: What is the Mediator pattern's main tradeoff?
- a) It increases coupling between colleagues
- b) It centralizes control but can become a monolith that is hard to maintain
- c) It eliminates all communication between objects
- d) It requires inheritance hierarchies
Answer: b
Objective: Behavioral Patterns

## Q23: Which GoF pattern category has the most patterns (11)?
- a) Creational
- b) Structural
- c) Behavioral
- d) Architectural
Answer: c
Objective: Core OO Principles

## Q24: What does the Open-Closed Principle state?
- a) Classes should have only one reason to change
- b) Software entities should be open for extension but closed for modification
- c) Subtypes must be substitutable for their base types
- d) Depend on abstractions, not concretions
Answer: b
Objective: SOLID Principles

## Q25: Which structural pattern shares object state to support large numbers of fine-grained objects efficiently?
- a) Composite
- b) Flyweight
- c) Proxy
- d) Decorator
Answer: b
Objective: Structural Patterns

## Q26: What is the key difference between Facade and Mediator?
- a) Facade is bidirectional, Mediator is unidirectional
- b) Facade provides unidirectional simplification, Mediator provides multidirectional coordination
- c) Facade is behavioral, Mediator is structural
- d) They are the same pattern with different names
Answer: b
Objective: Structural Patterns

## Q27: Which pattern lets you traverse elements of a collection without exposing the underlying representation?
- a) Visitor
- b) Observer
- c) Iterator
- d) Composite
Answer: c
Objective: Behavioral Patterns

## Q28: What does Memento capture?
- a) A request as an object
- b) An object's internal state so it can be restored later without violating encapsulation
- c) A grammar as a class hierarchy
- d) A chain of handler objects
Answer: b
Objective: Behavioral Patterns

## Q29: How does Factory Method differ from Abstract Factory?
- a) Factory Method creates families of objects, Abstract Factory creates single objects
- b) Factory Method relies on inheritance, Abstract Factory uses composition
- c) Factory Method is structural, Abstract Factory is behavioral
- d) They are identical patterns
Answer: b
Objective: Creational Patterns

## Q30: What is the Composite pattern's key structural feature?
- a) It wraps objects to add behavior
- b) It treats individual objects and compositions of objects uniformly through a shared interface
- c) It converts one interface to another
- d) It provides a surrogate for another object
Answer: b
Objective: Structural Patterns

## Q31: Which design principle was originated by Parnas in 1972?
- a) Single Responsibility Principle
- b) Separation of Concerns
- c) Information Hiding
- d) Law of Demeter
Answer: c
Objective: Related Principles

## Q32: What does the Law of Demeter restrict?
- a) The number of classes in a package
- b) The depth of inheritance hierarchies
- c) Which objects a method may send messages to
- d) The number of parameters in a method
Answer: c
Objective: Related Principles

## Q33: In the Observer pattern, what distinguishes it from Publish-Subscribe?
- a) Observer uses a message broker, Pub-Sub does not
- b) Observer couples subjects and observers directly, Pub-Sub decouples via a broker
- c) Observer is asynchronous, Pub-Sub is synchronous
- d) They are identical patterns
Answer: b
Objective: Behavioral Patterns

## Q34: What is delegation's relationship to inheritance?
- a) Delegation requires inheritance
- b) Delegation can always replace inheritance as a reuse mechanism
- c) Inheritance is a form of delegation
- d) They cannot be used together
Answer: b
Objective: Core OO Principles

## Q35: Which GRASP principle assigns responsibility to the class with the most information needed to fulfill it?
- a) Creator
- b) Controller
- c) Information Expert
- d) Pure Fabrication
Answer: c
Objective: Related Principles

## Q36: What problem does the Chain of Responsibility pattern solve?
- a) Converting interfaces between incompatible classes
- b) Decoupling the sender of a request from its receiver by giving multiple objects a chance to handle it
- c) Adding responsibilities to objects dynamically
- d) Defining a grammar and interpreter for a language
Answer: b
Objective: Behavioral Patterns

## Q37: Peter Norvig observed that how many of the 23 GoF patterns are simplified or eliminated in dynamic languages?
- a) 5
- b) 10
- c) 16
- d) 23
Answer: c
Objective: Core OO Principles

## Q38: What is the canonical violation example for the Liskov Substitution Principle?
- a) Circle-Ellipse
- b) Rectangle-Square
- c) Animal-Dog
- d) Stack-Array
Answer: b
Objective: SOLID Principles

## Q39: Which pattern allows an object to alter its behavior when its internal state changes, appearing to change its class?
- a) Strategy
- b) State
- c) Command
- d) Template Method
Answer: b
Objective: Behavioral Patterns

## Q40: What are the three major forms of polymorphism?
- a) Static, dynamic, and parametric
- b) Ad hoc, parametric, and subtyping
- c) Compile-time, runtime, and generic
- d) Overloading, overriding, and coercion
Answer: b
Objective: Core OO Principles
