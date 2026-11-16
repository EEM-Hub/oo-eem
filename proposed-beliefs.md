# Proposed Beliefs

Review each entry: change `[ACCEPT]` to `[ACCEPT]` to keep, or vice versa.
Then run: `expert-build accept-beliefs`

---

**Generated:** 2026-06-19
**Source:** 56 entries from entries/
**Model:** claude

### [ACCEPT] solid-acronym-five-principles
SOLID is a mnemonic acronym for five object-oriented design principles: Single Responsibility, Open-Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] solid-martin-2000-feathers-2004
Robert C. Martin articulated the SOLID principles in his 2000 paper 'Design Principles and Design Patterns', and Michael Feathers coined the SOLID acronym circa 2004.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] srp-one-reason-to-change
The Single Responsibility Principle states that a class should have only one reason to change — it should encapsulate exactly one responsibility.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] ocp-open-extension-closed-modification
The Open-Closed Principle states that software entities should be open for extension but closed for modification — new behavior is added by extending, not by altering existing code.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] lsp-substitutability-contract
The Liskov Substitution Principle requires that objects of a derived class must be substitutable for objects of their base class without breaking program correctness, and is closely related to design by contract.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] isp-no-unused-method-dependencies
The Interface Segregation Principle states that clients should not be forced to depend on interface methods they do not use — prefer many small focused interfaces over one large general-purpose interface.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] dip-depend-on-abstractions
The Dependency Inversion Principle states that high-level modules should not depend on low-level modules; both should depend on abstractions rather than concretions.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] lsp-preconditions-postconditions-rule
LSP compliance requires that subclass preconditions are no stronger and postconditions no weaker than those of the superclass.
- Source: entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID

### [ACCEPT] abstract-factory-creates-families
The Abstract Factory pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes, distinguishing it from Factory Method which creates single objects.
- Source: entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern

### [ACCEPT] abstract-factory-is-creational-gof
Abstract Factory is one of five creational patterns in the GoF catalog, alongside Builder, Factory Method, Prototype, and Singleton.
- Source: entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern

### [ACCEPT] abstract-factory-uses-composition
The Abstract Factory pattern relies on object composition rather than inheritance of the client class — client code depends only on abstract interfaces, never on concrete classes.
- Source: entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern

### [ACCEPT] abstract-factory-swap-one-line
Changing the product family in an Abstract Factory requires changing only which concrete factory is instantiated — typically one line in one file — rather than changing every instantiation site.
- Source: entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern

### [ACCEPT] abstract-factory-often-singleton
Abstract factories are often implemented as singletons — a single global factory object through which all client code routes creation requests.
- Source: entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern

### [ACCEPT] abstract-factory-participants
The Abstract Factory pattern has five structural participants: AbstractFactory, ConcreteFactory, AbstractProduct, ConcreteProduct, and Client.
- Source: entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern

### [ACCEPT] abstract-type-cannot-instantiate
An abstract type cannot be instantiated directly; instantiation occurs only through a concrete subtype that implements all abstract methods.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] one-abstract-method-makes-class-abstract
A class with even one abstract method (pure virtual function in C++) is itself abstract and cannot be instantiated.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] abstractness-propagates-to-subclass
A subclass that inherits from an abstract type but does not implement all inherited abstract methods is itself abstract.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] java-interface-methods-abstract-by-default
In Java, interface methods are abstract by default; the 'default' keyword (Java 8+) allows concrete method implementations in interfaces.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] abstract-type-vs-adt-distinction
Abstract types and abstract data types (ADTs) are different concepts: an abstract type is about instantiation and subtyping, while an ADT is about encapsulation and information hiding.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] meyers-non-leaf-classes-abstract-heuristic
The design heuristic 'make all non-leaf classes abstract' (Meyers/Riel) states that every class should be either a concrete leaf with no subtypes or an abstract interior node in the hierarchy.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] concept-vs-abstract-type-no-inheritance
In generic programming, a 'concept' specifies required syntax and semantics like an abstract type but does not require a subtype/inheritance relationship — two unrelated types can satisfy the same concept.
- Source: entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type

### [ACCEPT] data-abstraction-separates-interface-implementation
Data abstraction enforces separation between the abstract properties of a data type (interface/contract) and its concrete implementation details, so implementation changes do not affect client code.
- Source: entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)

### [ACCEPT] leaky-abstractions-spolsky
Joel Spolsky's Law of Leaky Abstractions states that all non-trivial abstractions are leaky — they can never completely hide all underlying implementation details.
- Source: entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)

### [ACCEPT] database-three-abstraction-levels
Database abstraction has three levels: Physical (how data is stored), Logical (what data and relationships exist), and View (subset visible to users); the separation between physical and logical is called physical data independence.
- Source: entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)

### [ACCEPT] oop-abstraction-three-mechanisms
Abstraction in OOP manifests through three mechanisms: encapsulation (hiding state), polymorphism (substituting types), and inheritance/delegation (structuring type hierarchies).
- Source: entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)

### [ACCEPT] adapter-pattern-structural-gof
The Adapter pattern (also called Wrapper) is a structural GoF design pattern that converts the interface of an existing class into a different interface that clients expect, without modifying the adaptee's source code.
- Source: entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern

### [ACCEPT] adapter-object-vs-class-variant
The Adapter pattern has two structural variants: object adapter (uses composition/delegation, can adapt an adaptee and all its subclasses) and class adapter (uses multiple inheritance, adapts only a specific concrete class).
- Source: entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern

### [ACCEPT] adapter-vs-decorator-vs-facade-vs-proxy
Adapter converts an interface (different interface out); Decorator adds behavior but preserves the same interface; Facade simplifies/creates a new interface to a subsystem; Proxy provides the same interface but controls access.
- Source: entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern

### [ACCEPT] object-adapter-preferred-over-class-adapter
Object adapters are generally preferred over class adapters because they don't require multiple inheritance and can adapt any subclass of the adaptee, not just one specific concrete class.
- Source: entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern

### [ACCEPT] adapter-three-roles
The Adapter pattern has three roles: Client (needs the target interface), Adaptee (has useful functionality but wrong interface), and Adapter (bridges the two by wrapping the adaptee).
- Source: entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern

### [ACCEPT] creational-patterns-two-subcategories
Creational patterns have two subcategories: object-creational (defer creation to another object) and class-creational (defer creation to subclasses)
- Source: entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern

### [ACCEPT] factory-method-is-class-creational
Factory Method is the only class-creational pattern among the GoF creational patterns; Abstract Factory, Builder, Prototype, and Singleton are object-creational
- Source: entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern

### [ACCEPT] gof-five-creational-patterns
The GoF book defines exactly five canonical creational patterns: Abstract Factory, Builder, Factory Method, Prototype, and Singleton
- Source: entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern

### [ACCEPT] lazy-init-object-pool-di-not-gof
Lazy Initialization, Object Pool, and Dependency Injection are commonly listed creational patterns but are not part of the original GoF catalog
- Source: entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern

### [ACCEPT] creational-patterns-flexibility-dimensions
Creational patterns increase flexibility in four dimensions: what gets created, who creates it, how it gets created, and when creation happens
- Source: entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern

### [ACCEPT] decorator-is-structural-gof-pattern
The Decorator pattern is classified as a structural pattern in the Gang of Four taxonomy, not behavioral or creational
- Source: entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern

### [ACCEPT] decorator-per-object-runtime-vs-subclass-per-class-compile
Decorator adds behavior per-object at runtime, while subclassing adds behavior per-class at compile time affecting all instances
- Source: entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern

### [ACCEPT] decorator-combinatorial-explosion-n-vs-2n
With N independent features, subclassing requires up to 2^N classes while the Decorator pattern requires only N decorator classes combined at runtime
- Source: entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern

### [ACCEPT] java-io-streams-canonical-decorator-example
Java I/O Streams (e.g., BufferedInputStream wrapping FileInputStream) are the canonical real-world example of the Decorator pattern
- Source: entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern

### [ACCEPT] adapter-vs-decorator-vs-facade-distinction
Adapter converts an interface to make incompatible classes work together, Decorator adds responsibility while keeping the same interface, and Facade simplifies a complex interface
- Source: entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern

### [ACCEPT] decorator-supports-srp-and-ocp
The Decorator pattern supports both the Single Responsibility Principle (each decorator encapsulates one concern) and the Open-Closed Principle (extends behavior without modifying existing code)
- Source: entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern

### [ACCEPT] delegation-vs-forwarding-self-rebinding
Delegation rebinds self/this to the original sender object, while forwarding does not — self in the receiver's method refers to the receiver itself in forwarding
- Source: entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)

### [ACCEPT] delegation-per-instance-runtime-inheritance-per-type-compile
Delegation operates per-instance at runtime, while inheritance typically operates per-type at compile time
- Source: entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)

### [ACCEPT] delegation-primary-reuse-in-prototype-languages
Delegation is the fundamental method for behavior reuse in prototype-based programming (Self, JavaScript), analogous to inheritance in class-based programming
- Source: entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)

### [ACCEPT] object-schizophrenia-delegation-ambiguity
Object schizophrenia is the ambiguity of this/self that arises when delegation causes self in one object to refer to a different object
- Source: entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)

### [ACCEPT] gof-book-23-patterns-three-categories
The GoF book Design Patterns (1994) defines exactly 23 patterns in 3 categories: 5 creational, 7 structural, 11 behavioral
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] gof-two-core-principles
The two core design principles from the GoF book are 'program to an interface, not an implementation' and 'favor object composition over class inheritance'
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] inheritance-whitebox-composition-blackbox-reuse
The GoF book calls inheritance 'white-box reuse' (parent internals visible to subclasses) and composition 'black-box reuse' (internals hidden behind well-defined interfaces)
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] inheritance-breaks-encapsulation-gof
The GoF book states that inheritance breaks encapsulation because subclasses are coupled to parent implementation details
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] norvig-16-of-23-patterns-simplified-dynamic-languages
Peter Norvig demonstrated that 16 of the 23 GoF patterns are simplified or eliminated by features in dynamic languages
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] gof-retrospective-add-remove-patterns
In a 2009 retrospective, the GoF authors would have added dependency injection, extension object, type object, and null object; Gamma wanted to remove Singleton but lacked consensus
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] gof-book-cpp-and-smalltalk-examples
The GoF Design Patterns book uses C++ and Smalltalk for its code examples
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] aggregation-shared-lifetimes-acquaintance-loose-coupling
In GoF terminology, aggregation implies shared lifetimes (has-a/part-of) while acquaintance (association) implies loose coupling (knows-of/uses) and is generally preferred
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] double-dispatch-two-runtime-types
Double dispatch selects which function to invoke based on the runtime types of two objects (receiver and argument), unlike single dispatch which only considers the receiver's type
- Source: entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch

### [ACCEPT] function-overloading-static-cannot-achieve-double-dispatch
Function overloading resolves on the static (declared) type of the argument at compile time, so it alone cannot achieve double dispatch which requires runtime type resolution
- Source: entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch

### [ACCEPT] visitor-pattern-implements-double-dispatch
The Visitor pattern is the standard design pattern used to implement double dispatch in single-dispatch languages like C++ and Java via the accept/visit two-step callback mechanism
- Source: entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch

### [ACCEPT] double-dispatch-callback-mechanism
Double dispatch works via two sequential single-dispatch calls: the receiver dispatches on its own type, then calls back into the argument passing this/self, causing a second vtable lookup on the argument's concrete type
- Source: entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch

### [ACCEPT] double-dispatch-special-case-of-multiple-dispatch
Double dispatch is the N=2 special case of multiple dispatch; languages with native multiple dispatch (CLOS, Julia, Dylan) do not need the double dispatch workaround
- Source: entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch

### [ACCEPT] csharp-dynamic-keyword-double-dispatch-alternative
C# provides a language-level alternative to the Visitor pattern for double dispatch by casting the argument to dynamic, which triggers runtime overload resolution
- Source: entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch

### [ACCEPT] delegation-can-always-replace-inheritance
According to the GoF book, delegation can always replace inheritance, but adds runtime complexity
- Source: entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns

### [ACCEPT] info-hiding-parnas-1972
David Parnas first described information hiding in 1972 in the paper 'On the Criteria To Be Used in Decomposing Systems into Modules'
- Source: entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding

### [ACCEPT] info-hiding-is-principle-encapsulation-is-mechanism
Information hiding is the design principle (segregate volatile decisions behind stable interfaces); encapsulation is the mechanism or technique that enforces it
- Source: entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding

### [ACCEPT] info-hiding-hides-design-decisions-not-just-data
Information hiding is about hiding design decisions likely to change, not merely hiding data
- Source: entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding

### [ACCEPT] info-hiding-applies-at-every-granularity
Information hiding applies at every level of granularity — classes, modules, subsystems, databases, and hardware components — not just at the class level
- Source: entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding

### [ACCEPT] parnas-provided-criterion-for-modular-decomposition
Parnas's contribution was providing the criterion for principled modular decomposition — hide what is likely to change — distinguishing it from earlier ad hoc modularity (Gauthier & Pont, 1970)
- Source: entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding

### [ACCEPT] encapsulation-more-general-than-oop
Encapsulation is more general than OOP — for example, a relational database encapsulates behind SQL, hiding all internal machinery
- Source: entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding

### [ACCEPT] inheritance-originated-hoare-1966-implemented-simula-67
The concept of inheritance originated with C.A.R. Hoare's 1966 work on record subclasses and was first implemented in Simula 67 by Dahl and Nygaard (1967)
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] inheritance-vs-subtyping-distinction
Inheritance reuses implementation and establishes a syntactic relationship; subtyping establishes a semantic is-a relationship enabling substitutability — inheritance does not guarantee behavioral subtyping (LSP)
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] fragile-base-class-problem
The fragile base class problem — modifications to a base class causing unintended behavioral changes in subclasses — is the central criticism of implementation inheritance
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] cpp-default-inheritance-private-java-effectively-public
In C++, default inheritance visibility is private; in Java, there is no visibility modifier on inheritance (effectively public)
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] cpp-private-members-never-inherited
In C++, private members are never inherited (not accessible) in any derivation mode — private, protected, or public
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] final-sealed-enables-static-dispatch
Marking a class final (Java/C++) or sealed (C#) prevents subclassing and enables static dispatch (early binding) by eliminating vtable lookups
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] cpp-private-inheritance-models-implemented-in-terms-of
C++ private inheritance models 'is implemented in terms of' — it provides code reuse without substitutability (not an is-a relationship)
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] class-hierarchy-forms-dag
A class hierarchy with inheritance forms a directed acyclic graph (DAG), not necessarily a tree, especially when multiple inheritance is used
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] yo-yo-problem-deep-inheritance
The yo-yo problem results from excessively deep inheritance hierarchies where too many thin layers make debugging and comprehension difficult
- Source: entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)

### [ACCEPT] interface-defines-method-signatures-no-implementation-no-state
An interface (protocol type) defines method signatures only — no implementation and no instance state
- Source: entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)

### [ACCEPT] class-can-implement-multiple-interfaces-extend-one-class
In single-inheritance languages like Java, a class can implement multiple interfaces but extend only one class
- Source: entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)

### [ACCEPT] interface-terminology-varies-by-language
The interface concept uses different terminology by language: Java uses 'interface', Swift/Objective-C use 'protocol', Rust uses 'trait', Haskell uses 'type class', C++20 uses 'concept'
- Source: entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)

### [ACCEPT] rust-traits-implemented-in-separate-impl-blocks
In Rust, traits are implemented in separate 'impl TraitName for StructName' blocks, not inside the struct definition; non-trait methods use plain 'impl StructName' blocks
- Source: entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)

### [ACCEPT] cpp20-concepts-resemble-go-style-interfaces
C++20 concepts resemble Go-style interfaces — any type (not just classes) can satisfy a concept if it meets all requirements, without explicit inheritance
- Source: entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)

### [ACCEPT] interfaces-central-to-dependency-inversion-principle
Interfaces are the mechanism behind the Dependency Inversion Principle — depend on abstractions (interfaces), not concretions (concrete classes)
- Source: entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)

### [ACCEPT] interpreter-pattern-is-behavioral-gof
The Interpreter pattern is a behavioral design pattern from the Gang of Four catalog that evaluates sentences in a language by mapping one class per grammar rule
- Source: entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern

### [ACCEPT] interpreter-ast-is-composite-pattern-instance
The abstract syntax tree (AST) that the Interpreter pattern evaluates is an instance of the Composite pattern — nonterminal expressions are composites, terminal expressions are leaves
- Source: entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern

### [ACCEPT] interpreter-does-not-describe-parsing
The Interpreter pattern does not describe how to parse or build the AST — it only describes evaluation of an already-constructed syntax tree
- Source: entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern

### [ACCEPT] interpreter-best-for-simple-stable-grammars
The Interpreter pattern is best suited for simple, relatively stable grammars; for complex grammars the class hierarchy becomes unwieldy and parser generators or the Visitor pattern are more appropriate
- Source: entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern

### [ACCEPT] ioc-framework-calls-application-code
Inversion of Control means custom code receives flow of control from a framework rather than directing it — the framework calls your code instead of your code calling library code
- Source: entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control

### [ACCEPT] ioc-distinguishes-framework-from-library
The defining distinction between a framework and a library is IoC: a library is called by your code; a framework calls your code
- Source: entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control

### [ACCEPT] dependency-injection-is-not-ioc
Dependency injection is not the same as Inversion of Control — DI is one specific pattern for dependency resolution often associated with IoC containers, but IoC originally refers to control flow inversion
- Source: entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control

### [ACCEPT] ioc-hollywood-principle
IoC is also known as the Hollywood Principle: 'Don't call us, we'll call you' — the framework dictates execution flow
- Source: entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control

### [ACCEPT] template-method-pattern-embodies-ioc
The Template Method pattern is a GoF behavioral pattern that embodies IoC — the base class controls the algorithm skeleton while subclasses fill in specific steps
- Source: entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control

### [ACCEPT] cohesion-measures-element-belonging
Cohesion measures the degree to which elements within a module belong together and the strength of relationship between a class's methods and data.
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] cohesion-is-ordinal-not-interval
Cohesion is an ordinal (qualitative) measure, not an interval or numeric ratio — the ranked types do not represent steady progression.
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] cohesion-invented-by-constantine-1960s
Cohesion was invented by Larry Constantine in the late 1960s as part of Structured Design, formalized in Stevens, Myers & Constantine (1974) and Yourdon & Constantine (1979).
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] cohesion-seven-types-worst-to-best
The seven types of cohesion ranked worst to best are: coincidental, logical, temporal, procedural, communicational, sequential, functional (with perfect/atomic as an eighth ideal).
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] utilities-class-coincidental-cohesion
A 'Utilities' class is the canonical example of coincidental cohesion (the worst kind), where parts are grouped arbitrarily with no meaningful relationship.
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] srp-is-oo-functional-cohesion
The Single Responsibility Principle (SRP) is the OO formalization of functional cohesion — a class should have one reason to change.
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] high-cohesion-does-not-mean-single-method-classes
High cohesion does not mean single-method classes — a single-function module has perfect cohesion but may be too narrow and creates tight coupling to other modules.
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] lcom-measures-cohesion
LCOM (Lack of Cohesion of Methods) is a static code analysis metric that can compute cohesion.
- Source: entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)

### [ACCEPT] command-pattern-encapsulates-request-as-object
The Command pattern is a GoF behavioral design pattern that encapsulates a request as an object containing the method name, owning object, and parameter values, decoupling the sender from the performer.
- Source: entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern

### [ACCEPT] command-pattern-four-roles
The Command pattern has four core roles: Command (encapsulates request), Receiver (performs work), Invoker (triggers execution via abstract Command interface), and Client (assembles commands, receivers, and invokers).
- Source: entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern

### [ACCEPT] command-pattern-undo-via-stack
Multi-level undo is implemented via the Command pattern by maintaining a stack of executed command objects; undo pops and calls undo() on each.
- Source: entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern

### [ACCEPT] command-pattern-mirrors-first-class-functions
The Command pattern closely mirrors first-class functions and higher-order functions in functional programming — the invoker is a higher-order function and the command is a first-class argument.
- Source: entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern

### [ACCEPT] command-pattern-enables-transactional-rollback
The Command pattern enables transactional behavior — if one operation in a sequence fails, all can be rolled back.
- Source: entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern

### [ACCEPT] thread-pools-use-command-pattern
Thread pools use the Command pattern: work items in the queue are command objects implementing a common interface (e.g., java.lang.Runnable).
- Source: entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern

### [ACCEPT] composite-pattern-is-structural
The Composite pattern is a structural (not behavioral or creational) GoF design pattern that organizes objects into tree structures representing part-whole hierarchies.
- Source: entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern

### [ACCEPT] composite-three-participants
The Composite pattern has three participants: Component (shared interface), Leaf (terminal objects with no children), and Composite (containers that hold and delegate to child Components).
- Source: entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern

### [ACCEPT] composite-transparency-vs-type-safety
The Composite pattern has two design variants: transparency (add/remove on Component — uniform but unsafe at compile time) vs type safety (add/remove only on Composite — safe but non-uniform).
- Source: entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern

### [ACCEPT] gof-favored-composite-transparency
The original GoF book favors transparency over type safety for the Composite pattern, placing child-manipulation methods on the Component interface.
- Source: entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern

### [ACCEPT] composite-uses-recursive-delegation
Operations on Composite objects are implemented via recursive delegation — the Composite forwards requests to its children, which may themselves be Composites, forming arbitrarily deep trees.
- Source: entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern

### [ACCEPT] composition-over-inheritance-has-a-vs-is-a
Composition over inheritance means preferring has-a (delegate objects as fields) over is-a (class hierarchy) relationships for code reuse, enabling runtime behavior changes.
- Source: entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance

### [ACCEPT] gof-favor-composition-not-eliminate-inheritance
The GoF Design Patterns book (1994) recommends 'Favor object composition over class inheritance' but does not say to eliminate inheritance entirely — they note the two typically work hand-in-hand.
- Source: entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance

### [ACCEPT] composition-primary-drawback-forwarding-boilerplate
The primary drawback of composition over inheritance is forwarding boilerplate — every delegated method must be explicitly forwarded, unlike inheritance where methods are automatically available.
- Source: entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance

### [ACCEPT] composition-avoids-diamond-problem
Composition avoids the diamond problem that plagues multiple inheritance by sidestepping class hierarchies entirely.
- Source: entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance

### [ACCEPT] go-rust-composition-only-no-inheritance
Go and Rust use type composition exclusively, having no class-based inheritance at all.
- Source: entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance

### [ACCEPT] composition-over-inheritance-is-strategy-pattern
Composition over inheritance is essentially the Strategy pattern applied structurally — each delegate object is a swappable strategy.
- Source: entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance

### [ACCEPT] coupling-six-procedural-types-ordered
The six procedural coupling types from tightest to loosest are: content, common, external, control, stamp, data.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] coupling-coined-by-constantine-1960s
Coupling was coined by Larry Constantine in the late 1960s as part of structured design, formalized in Stevens, Myers & Constantine (1974) and Yourdon & Constantine (1979).
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] low-coupling-high-cohesion-good-design
Low coupling combined with high cohesion is widely considered the canonical hallmark of well-structured, readable, and maintainable modular design.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] coupling-control-params-weighted-2x
In the Pressman coupling metric formula, control parameters are weighted 2x compared to data parameters, reflecting their greater impact on interdependence.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] connascence-finer-grained-than-coupling
Connascence (Page-Jones) is a finer-grained framework than coupling for analyzing dependencies, adding locality and degree dimensions; connascence of name is weaker than connascence of position.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] stamp-coupling-passes-unneeded-structure
Stamp coupling occurs when modules share a composite data structure but use only parts of it — changes to unused fields can still force retesting.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] content-coupling-violates-information-hiding
Content coupling — where one module directly uses another's internal code — violates the information hiding principle and is the tightest form of procedural coupling.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] hohpe-eight-dimensions-of-coupling
Hohpe identifies eight dimensions of coupling: Technology, Location, Topology, Data Format & Type, Semantic, Conversation, Order, and Temporal dependency.
- Source: entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)

### [ACCEPT] encapsulation-two-meanings
Encapsulation has two distinct meanings: (1) a language mechanism for restricting direct access to an object's components (access control), and (2) a language construct that bundles data with the behavior operating on that data (cohesion).
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] encapsulation-not-information-hiding
Encapsulation and information hiding are related but distinct concepts: bundling (encapsulation) is structural, while hiding is about access control. Rogers (2001) explicitly argues this distinction.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] inheritance-breaks-encapsulation-gof
The Gang of Four (Design Patterns, 1994) warn that inheritance often breaks encapsulation by exposing a subclass to its parent's implementation details, and that designers tend to overuse inheritance.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] python-no-enforced-access-restriction
Python has no enforced access restriction — underscore prefix (_var) is convention only, and name mangling (__var) provides weak protection that is easily circumvented.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] smalltalk-ruby-strictest-oop-encapsulation
Smalltalk and Ruby enforce the strictest OOP encapsulation: all field access must go through methods — no direct field access from outside the object.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] encapsulation-not-oop-exclusive
Encapsulation is not unique to OOP — C's opaque pointer pattern, modules, abstract data types, libraries, and lexical closures all provide encapsulation. Existential types provide the theoretical foundation.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] object-capability-model-guarantees-encapsulation
The object-capability model is the only approach that guarantees encapsulation cannot be bypassed (no reflection backdoor), unlike Java/Ruby/C# reflection APIs or Python name mangling.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] c-opaque-pointer-encapsulation-pattern
C achieves encapsulation via the opaque pointer pattern: declare a typedef struct forward declaration in the header file, define the struct only in the .c implementation file, and expose only API functions to clients.
- Source: entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)

### [ACCEPT] facade-pattern-gof-structural
The Facade pattern is a structural design pattern from the GoF catalog (Design Patterns, 1994, pp. 185ff) that provides a simplified, unified interface to a complex subsystem of classes.
- Source: entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern

### [ACCEPT] facade-vs-adapter-vs-decorator
Facade, Adapter, and Decorator serve distinct purposes: Adapter converts one interface to match what a client expects, Decorator dynamically adds/alters behavior at runtime, and Facade provides a simplified interface for complexity reduction.
- Source: entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern

### [ACCEPT] facade-may-add-functionality
A Facade object may perform additional functionality before/after forwarding requests to subsystem classes — it is not limited to pure delegation.
- Source: entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern

### [ACCEPT] facade-reduces-client-dependencies
The Facade pattern reduces client dependencies on subsystem classes: clients depend only on the Facade, replacing tight coupling with loose coupling.
- Source: entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern

### [ACCEPT] factory-method-gof-creational
The Factory Method pattern is a creational GoF pattern whose intent is: 'Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory method lets a class defer instantiation to subclasses.'
- Source: entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern

### [ACCEPT] factory-method-relies-on-inheritance
The Factory Method pattern relies on inheritance (subclassing) to vary the product being created, distinguishing it from Abstract Factory which uses object composition.
- Source: entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern

### [ACCEPT] factory-method-supports-open-closed-principle
Factory Method supports the Open-Closed Principle: new product types can be added by creating new ConcreteCreator subclasses without modifying existing creator code.
- Source: entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern

### [ACCEPT] factory-method-combines-with-template-method
Factory Method frequently combines with Template Method: the creator's constructor defines the algorithm skeleton while the factory method is the hook that varies the concrete product type (as shown in the GoF MazeGame example).
- Source: entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern

### [ACCEPT] factory-method-abstract-or-default
A factory method can be abstract (forcing subclasses to implement it) or concrete with a default implementation (allowing optional override).
- Source: entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern

### [ACCEPT] flyweight-pattern-gof-structural
The Flyweight pattern is a structural GoF design pattern that minimizes memory usage by sharing common data across many similar objects, separating intrinsic state (shared, context-independent) from extrinsic state (unique, context-dependent).
- Source: entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern

### [ACCEPT] flyweight-intrinsic-vs-extrinsic-state
In the Flyweight pattern, intrinsic state is invariant, context-independent, and stored inside the flyweight object; extrinsic state is variant, context-dependent, and passed in by the client at use time.
- Source: entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern

### [ACCEPT] flyweight-term-origin
The term 'Flyweight' was coined by Paul Calder and Mark Linton in 1990 for handling glyphs in a WYSIWYG editor, though similar techniques existed as early as 1988 in the ET++ framework.
- Source: entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern

### [ACCEPT] flyweight-immutable-value-objects
Making flyweights into immutable value objects enables safe sharing across threads — two instances are equal if their values are equal.
- Source: entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern

### [ACCEPT] flyweight-factory-checks-existing
The FlyweightFactory must check for existing instances before creating new ones — this is the core sharing mechanism. The factory is often implemented as a Singleton.
- Source: entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern

### [ACCEPT] grasp-nine-patterns
GRASP consists of exactly nine patterns: Information Expert, Creator, Controller, Indirection, Low Coupling, High Cohesion, Polymorphism, Protected Variations, and Pure Fabrication.
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-created-by-larman
GRASP was created by Craig Larman, first published in 'Applying UML and Patterns' (1997, 2nd ed. 2001, 3rd ed. 2004).
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-information-expert-principle
GRASP's Information Expert principle states: assign responsibility to the class that has the information needed to fulfill it — look at what data is required, find where it lives, and place the method there.
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-creator-four-criteria
GRASP's Creator pattern assigns class B the responsibility to create object A when B satisfies one or more criteria: contains/aggregates A, records A, closely uses A, or has A's initializing data.
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-controller-beyond-ui
GRASP's Controller is the first object beyond the UI layer that handles system events — it does not do the work itself but delegates. It comes in two variants: use case controller and facade controller.
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-pure-fabrication-not-domain-concept
GRASP's Pure Fabrication is a class that does not represent a domain concept, invented solely to achieve low coupling, high cohesion, and reuse. It corresponds to the 'service' concept in Domain-Driven Design.
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-protected-variations-wraps-instability
GRASP's Protected Variations pattern identifies points of predicted instability and wraps them with a stable interface, using polymorphism for varying implementations. It is closely related to the SOLID Open/Closed Principle.
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] grasp-low-coupling-high-cohesion-evaluative
GRASP's Low Coupling and High Cohesion are evaluative patterns (qualities to assess and aim for), not constructive patterns (specific structures to build).
- Source: entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)

### [ACCEPT] gof-eleven-behavioral-patterns
The Gang of Four defined 11 behavioral patterns: Chain of Responsibility, Command, Interpreter, Iterator, Mediator, Memento, Observer, State, Strategy, Template Method, and Visitor
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] strategy-uses-composition-template-method-uses-inheritance
Strategy pattern uses composition to vary algorithms while Template Method pattern uses inheritance to vary algorithm steps
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] observer-one-to-many-pubsub-many-to-many
Observer pattern defines a one-to-many dependency between objects, while Publish-Subscribe supports many-to-many communication via message brokers
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] state-pattern-partial-runtime-type-change
The State pattern allows an object to partially change its type at runtime, providing a clean alternative to conditional logic based on state
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] specification-pattern-boolean-composition
The Specification pattern enables recombinable business logic using boolean algebra composition (AND, OR, NOT)
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] null-object-is-behavioral-not-structural
The Null Object pattern is classified as a behavioral pattern, not structural, and acts as a default value to eliminate null checks
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] memento-provides-undo-via-state-capture
The Memento pattern provides rollback/undo capability by capturing and restoring an object's internal state without violating encapsulation
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] bridge-pattern-is-structural
The Bridge pattern is a structural GoF design pattern that decouples an abstraction from its implementation so both can vary independently
- Source: entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern

### [ACCEPT] bridge-uses-composition-not-inheritance
The Bridge pattern uses composition/delegation as its primary decoupling mechanism: the abstraction holds a reference to an implementor object rather than inheriting from it
- Source: entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern

### [ACCEPT] bridge-solves-class-explosion
The Bridge pattern solves class explosion when abstraction and implementation dimensions multiply: M × N subclasses become M + N classes
- Source: entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern

### [ACCEPT] bridge-single-impl-degenerates-to-pimpl
When only one fixed implementation exists, the Bridge pattern degenerates to the Pimpl idiom (pointer to implementation) in C++
- Source: entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern

### [ACCEPT] bridge-designed-upfront-adapter-applied-after
Bridge is designed upfront to separate abstraction from implementation; Adapter is applied after design to reconcile incompatible interfaces
- Source: entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern

### [ACCEPT] bridge-four-participants
The Bridge pattern has four participants: Abstraction (high-level interface holding Implementor reference), RefinedAbstraction (extends Abstraction), Implementor (interface for implementations), and ConcreteImplementor (concrete implementation)
- Source: entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern

### [ACCEPT] builder-is-creational-pattern
The Builder pattern is a creational GoF pattern that separates the construction of a complex object from its representation, allowing the same construction process to create different representations
- Source: entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern

### [ACCEPT] builder-four-participants
The Builder pattern has four participants: Director (orchestrates construction steps), Builder (abstract interface for creating parts), ConcreteBuilder (implements Builder, constructs and assembles parts), and Product (the complex object being built)
- Source: entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern

### [ACCEPT] builder-director-independent-of-concrete-classes
In the Builder pattern, the Director does not create products directly — it uses the Builder interface, making it independent of concrete builder and product classes
- Source: entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern

### [ACCEPT] builder-requires-one-concrete-builder-per-product
A distinct ConcreteBuilder is required for each type of product in the Builder pattern, which is a key disadvantage
- Source: entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern

### [ACCEPT] builder-vs-abstract-factory
Abstract Factory creates families of related objects in one step; Builder constructs one complex object step-by-step through a sequence of build operations
- Source: entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern

### [ACCEPT] chain-of-responsibility-is-behavioral
Chain of Responsibility is a behavioral GoF pattern that decouples the sender of a request from its receiver by passing the request along a chain of potential handlers until one processes it
- Source: entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern

### [ACCEPT] cor-strict-gof-one-handler-processes
The strict GoF definition of Chain of Responsibility specifies that exactly one handler processes the request, though practical implementations often allow multiple handlers to take partial responsibility
- Source: entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern

### [ACCEPT] cor-vs-decorator-structural-similarity
Chain of Responsibility and Decorator are structurally nearly identical (both use recursive composition via a common interface), but differ in intent: Decorator has all handlers process the request while Chain of Responsibility has one handler process it
- Source: entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern

### [ACCEPT] cor-no-guarantee-of-handling
In Chain of Responsibility, if no handler in the chain processes the request, it falls off the end unhandled unless the last handler is a catch-all
- Source: entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern

### [ACCEPT] cor-apple-responder-chain-example
Apple's Cocoa/Cocoa Touch responder chain (NSResponder/UIResponder hierarchy) is a real-world implementation of the Chain of Responsibility pattern
- Source: entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern

### [ACCEPT] class-defines-implementation-type-defines-interface
A class is a concrete implementation (data structure + subroutines) while a type is an interface; different classes can produce objects of the same abstract type
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] object-state-per-instance-class-state-shared
Object state differs between instances while class state is shared across all instances of that class
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] is-a-inheritance-has-a-composition
In OO design, 'is-a' relationships map to inheritance (hierarchical) while 'has-a' relationships map to composition; confusing 'part-of' with subclassing is a common design error
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] single-inheritance-tree-multiple-inheritance-dag
With single inheritance the class hierarchy forms a tree; with multiple inheritance it forms a directed acyclic graph (DAG)
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] java-single-class-inheritance-multiple-interfaces
Java allows implementing multiple interfaces but permits inheriting from only one class (single class inheritance)
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] access-specifiers-not-visibility
Access specifiers (private, protected, public) do not necessarily control visibility — a private member may be visible to client code but not usable by it
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] metaclass-instances-are-classes
A metaclass is a class whose instances are themselves classes; examples exist in Python, Ruby, Smalltalk, and CLOS
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] abstract-class-cannot-be-instantiated
Abstract classes cannot be instantiated directly and may contain abstract methods; a pure abstract base class in C++ containing only pure virtual methods is equivalent to an interface
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] classes-originated-in-simula-from-algol-blocks
Classes originated in Simula in the 1960s, drawing on the block concept from ALGOL
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] gof-three-pattern-categories
The Gang of Four organized the 23 design patterns into three categories: Creational (object construction), Structural (object composition), and Behavioral (object communication)
- Source: entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern

### [ACCEPT] encapsulation-required-to-enforce-invariants
Encapsulation of state is required to enforce class invariants; some languages like Eiffel support class invariants enforced by the type system
- Source: entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)

### [ACCEPT] prototype-pattern-is-creational-gof
The Prototype pattern is one of the 5 creational GoF patterns (Abstract Factory, Builder, Factory Method, Prototype, Singleton)
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] prototype-creates-objects-by-cloning
The Prototype pattern creates new objects by cloning a prototypical instance via a clone() method rather than using constructors directly
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] prototype-avoids-subclassing-unlike-factory-method
Prototype does not require subclassing to vary the product (unlike Factory Method) but does require a clone() method and may require a separate initialize() operation
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] factory-method-requires-subclassing-not-init
Factory Method requires subclassing the creator to vary products but does not require an initialization operation; Prototype is the inverse — no subclassing but requires initialize()
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] abstract-factory-implementable-via-prototype-or-factory-method
Abstract Factory can be implemented via either Factory Method (inheritance) or Prototype (delegation/cloning)
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] prototype-enables-runtime-product-addition-removal
Prototype enables runtime addition and removal of product types without changing factory code
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] prototype-clone-acts-as-polymorphic-constructor
The clone() method in the Prototype pattern acts as a polymorphic (virtual) constructor — the client calls clone() on an abstract type and gets a concrete copy without knowing the specific class
- Source: entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern

### [ACCEPT] proxy-pattern-is-structural-gof
The Proxy pattern is a structural GoF design pattern that provides a surrogate or placeholder object controlling access to another object
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] proxy-and-real-subject-share-same-interface
The proxy and real subject must implement the same interface (Subject), making the proxy transparent to clients
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] proxy-three-variants-remote-virtual-protection
The three main proxy variants are Remote (different address space), Virtual (deferred/lazy creation of expensive objects), and Protection (access control based on permissions)
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] proxy-holds-reference-does-not-inherit-real-subject
The proxy holds a reference to the real subject and forwards requests to it — it does not inherit from the real subject
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] proxy-controls-access-decorator-adds-behavior
Proxy controls access to the wrapped object; Decorator adds behavior. Proxy typically manages the lifecycle of the real object; Decorator does not.
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] proxy-same-interface-adapter-changes-interface
Proxy preserves the same interface as the wrapped object; Adapter changes the interface to match what the client expects
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] proxy-supports-open-closed-principle
The Proxy pattern supports the Open/Closed Principle by enabling cross-cutting concerns (caching, logging, security) without modifying the real subject
- Source: entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern

### [ACCEPT] pubsub-highest-decoupling-among-messaging-patterns
Publish-subscribe provides the highest level of decoupling among architectural messaging patterns — higher than RPC or point-to-point messaging
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] pubsub-three-decoupling-dimensions
Pub/sub decouples along three dimensions: spatial (location), temporal (timing), and logical (identity) — publishers and subscribers need not know each other's identity, location, or be active at the same time
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] pubsub-three-filtering-strategies
Pub/sub supports three message filtering strategies: topic-based (named channels), content-based (attribute constraints), and hybrid (topic + content filtering combined)
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] pubsub-distinct-from-observer-pattern
Pub/sub is distinct from the Observer pattern: pub/sub is distributed, asynchronous, and broker-mediated; Observer is typically in-process, synchronous, and uses direct references
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] pubsub-sibling-of-message-queue-paradigm
Pub/sub is a sibling of the message queue paradigm — queues deliver to one consumer, pub/sub delivers to all matching subscribers; many frameworks support both (JMS, Kafka, MQTT)
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] pubsub-does-not-guarantee-delivery-by-default
Pub/sub does not guarantee message delivery by default; assured delivery requires additional design such as subscriber acknowledgment
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] pubsub-earliest-system-isis-toolkit-1987
The earliest described pub/sub system was the 'news' subsystem of the Isis Toolkit, presented at SOSP 1987
- Source: entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern

### [ACCEPT] soc-coined-by-dijkstra-1974
Separation of concerns was coined by Edsger W. Dijkstra in 1974 in 'On the Role of Scientific Thought'
- Source: entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns

### [ACCEPT] soc-four-dimensions-temporal-quality-view-size
SoC has four dimensions: temporal (sequencing activities), quality (correctness vs efficiency), view (data flow vs control flow), and size (modularity)
- Source: entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns

### [ACCEPT] soc-broader-than-modularity
SoC is broader than modularity: modularity is separation by size, while SoC also covers temporal separation (project phases), quality separation, and view separation
- Source: entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns

### [ACCEPT] cross-cutting-concerns-motivate-aop
Cross-cutting concerns (security, logging) span multiple modules and resist standard modular decomposition, motivating aspect-oriented programming (AOP)
- Source: entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns

### [ACCEPT] kruchten-4plus1-view-model-applies-soc
Kruchten's 4+1 View Model applies SoC to software architecture with five views: logical, process, development, physical, plus scenarios
- Source: entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns

### [ACCEPT] singleton-pattern-is-creational-gof
The Singleton pattern is a creational GoF pattern that restricts a class to exactly one instance and provides a global access point via a static accessor method
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] singleton-private-constructor-static-accessor
Singleton implementation requires two key steps: making the constructor private to prevent external instantiation, and providing a static accessor method (e.g., getInstance()) returning a reference to a private static instance
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] singleton-lazy-init-not-thread-safe
Naive lazy initialization of a Singleton is not thread-safe; solutions include double-checked locking with volatile (Java 5+), Meyers Singleton with local static (C++11+), or initialization-on-demand holder idiom (Java)
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] java-double-checked-locking-requires-volatile
In Java, the volatile keyword on the Singleton instance field is required for double-checked locking to work correctly under the Java 5+ memory model
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] meyers-singleton-thread-safe-cpp11
The Meyers Singleton uses a local static variable inside getInstance() and is thread-safe in C++11+ without explicit locking, leveraging the language's guarantee of thread-safe static local initialization
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] singleton-anti-pattern-criticisms
Singleton is criticized as an anti-pattern because it introduces global state, increases coupling, hinders unit testing, violates the Single Responsibility Principle, and prevents concurrent use of multiple instances
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] singleton-foundation-for-other-creational-patterns
Singleton is often used as the implementation basis for Abstract Factory, Factory Method, Builder, and Prototype patterns
- Source: entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern

### [ACCEPT] dip-is-d-in-solid
The Dependency Inversion Principle is the 'D' in SOLID, one of five OO design principles.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-originated-by-robert-c-martin
Robert C. Martin originated the Dependency Inversion Principle, first in a 1994 paper and later in a 1996 C++ Report article.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-statement-one-both-depend-on-abstractions
DIP statement 1: High-level modules should not import from low-level modules; both should depend on abstractions.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-statement-two-abstractions-not-depend-on-details
DIP statement 2: Abstractions should not depend on details; details should depend on abstractions.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-abstractions-owned-by-high-level-layer
In DIP, the abstractions (interfaces) are owned by the higher/policy layer, not the lower implementation layer.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-not-low-depends-on-high
DIP does not mean low-level modules depend on high-level modules; it means both depend on a shared abstraction layer.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-differs-from-dependency-injection
DIP is a design principle specifying dependency structure; Dependency Injection is a runtime mechanism for providing implementations that satisfy DIP abstractions.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-two-implementation-strategies
DIP has two implementation strategies: direct (abstractions co-packaged with policy layer, inverting compilation dependency) and separated (abstractions in independent packages, maximizing reuse).
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] dip-wrapping-every-class-in-interface-not-sufficient
Wrapping every class in an interface does not automatically reduce coupling; only thoughtful abstraction of interactions achieves that.
- Source: entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle

### [ACCEPT] isp-is-i-in-solid
The Interface Segregation Principle is the 'I' in SOLID.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-no-client-forced-to-depend-on-unused-methods
ISP states that no code should be forced to depend on methods it does not use.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-originated-from-martin-xerox-work
ISP was formulated by Robert C. Martin during consulting work at Xerox on a printer system with a monolithic Job class.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-role-interfaces-from-fat-interface
ISP prescribes splitting large 'fat' interfaces into smaller role interfaces, where each captures a single role or capability.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-prevents-forced-recompilation
ISP prevents forced recompilation/redeployment: without ISP, changing a fat interface forces all clients to rebuild even if the change is irrelevant to them.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-differs-from-srp
SRP applies to class responsibilities (one reason to change), while ISP applies to what interfaces expose to their clients (one client role).
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-applies-to-microservice-design
ISP extends beyond OOP into microservice design as one of the six IDEALS principles, where service contracts should expose only what each consumer needs.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] isp-similar-to-grasp-high-cohesion
ISP is described as similar to GRASP's High Cohesion principle — both aim to keep related responsibilities together and unrelated ones apart.
- Source: entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle

### [ACCEPT] lsp-is-l-in-solid
The Liskov Substitution Principle is the 'L' in SOLID.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-introduced-by-liskov-1987
LSP was introduced by Barbara Liskov in 1987 and formalized with Jeannette Wing in 1994.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-subtype-substitutable-without-breaking-correctness
LSP requires that objects of a subtype S can replace objects of supertype T without altering desirable program properties (correctness).
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-semantic-not-just-syntactic
LSP is a semantic relation requiring behavioral compatibility, not merely syntactic signature conformance.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-preconditions-postconditions-invariants-rules
LSP behavioral conditions: preconditions cannot be strengthened, postconditions cannot be weakened, and invariants cannot be weakened in the subtype.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-history-constraint
The history constraint (Liskov & Wing's novel contribution) requires that subtypes must not introduce methods allowing state changes impermissible in the supertype.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-contravariance-parameters-covariance-returns
LSP signature requirements: contravariance of method parameter types and covariance of method return types in the subtype.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-rectangle-square-canonical-violation
The Rectangle-Square problem is the canonical LSP violation: Square's setters break Rectangle's implicit postcondition that width and height are independently modifiable.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-behavioral-subtyping-undecidable
Full behavioral subtyping (LSP) is undecidable — it cannot be verified algorithmically in general.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] lsp-violations-motivate-composition-over-inheritance
LSP violations are a primary motivation for preferring composition over inheritance; when substitutability cannot be maintained, inheritance is the wrong tool.
- Source: entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle

### [ACCEPT] ocp-is-o-in-solid
The Open-Closed Principle is the 'O' in SOLID.
- Source: entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle

### [ACCEPT] ocp-open-for-extension-closed-for-modification
OCP states that software entities should be open for extension but closed for modification.
- Source: entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle

### [ACCEPT] ocp-meyer-coined-term-1988
Bertrand Meyer coined the Open-Closed Principle in 'Object-Oriented Software Construction' (1988), using concrete implementation inheritance.
- Source: entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle

### [ACCEPT] ocp-polymorphic-version-martin-1996
Robert C. Martin's 1996 C++ Report article is the seminal reference for the polymorphic version of OCP, which uses abstract base classes and interfaces instead of concrete inheritance.
- Source: entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle

### [ACCEPT] ocp-two-historical-interpretations
OCP has two historical interpretations: Meyer's (concrete inheritance, 1988) and the polymorphic version (abstract interfaces, 1990s); the polymorphic version is the modern, widely-adopted interpretation.
- Source: entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle

### [ACCEPT] ocp-linked-to-protected-variations-and-information-hiding
Craig Larman linked OCP to Cockburn's Protected Variations pattern and Parnas's information hiding, showing OCP as one instance of a broader design strategy.
- Source: entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle

### [ACCEPT] srp-is-s-in-solid
The Single-Responsibility Principle is the 'S' in SOLID.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] srp-one-actor-not-one-function
SRP says a module should be responsible to one actor (group of stakeholders), not one function — a class can have multiple methods as long as they all serve the same actor.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] srp-originated-by-robert-c-martin
SRP was originated by Robert C. Martin; originally phrased as 'one reason to change,' later refined to the actor-based formulation.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] srp-rooted-in-cohesion-structured-design
SRP is derived from the concept of cohesion in structured design (DeMarco 1979, Page-Jones 1988), not invented from scratch.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] srp-gather-separate-heuristic
SRP heuristic: gather together things that change for the same reasons, separate those that change for different reasons.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] srp-canonical-example-report-module
The canonical SRP violation example is a report module handling both compilation (content) and printing (format), since these serve different actors and evolve at different times.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] srp-key-sources-books
SRP key sources: 'Agile Software Development, Principles, Patterns, and Practices' (2003) for original formulation; 'Clean Architecture' (2018) for actor-based refinement.
- Source: entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle

### [ACCEPT] iterator-is-behavioral-gof-pattern
The Iterator pattern is classified as a behavioral pattern in the Gang of Four taxonomy, not structural or creational.
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] iterator-pattern-decouples-traversal-from-container
The Iterator pattern provides a way to access elements of an aggregate object sequentially without exposing its underlying representation, by encapsulating traversal logic in a separate iterator object.
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] iterator-create-iterator-is-factory-method
The createIterator() method on the Aggregate interface is an application of the Factory Method pattern.
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] iterator-participants-aggregate-and-iterator
The Iterator pattern has four participants: Aggregate (declares createIterator()), ConcreteAggregate (implements it), Iterator (declares next()/hasNext()), and ConcreteIterator (implements traversal with a reference to the aggregate).
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] iterator-cpp-uses-end-sentinel-model
In C++, iterators use pointer semantics (dereference, increment, decrement) and rely on an end sentinel model — equality test against end() rather than the iterator knowing it has reached the end.
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] iterator-enables-multiple-traversal-strategies
Different iterator implementations can traverse the same aggregate in different ways (forward, reverse, filtered) without modifying the aggregate, aligning with the Open/Closed Principle.
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] iterator-commonly-used-with-composite
Iterators are commonly used to traverse composite structures (trees of objects), linking the Iterator and Composite patterns.
- Source: entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern

### [ACCEPT] lod-proposed-1987-holland-northeastern
The Law of Demeter was proposed by Ian Holland in 1987 at Northeastern University as part of the Demeter Project.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] lod-five-permitted-method-call-targets
The Law of Demeter restricts a method m of object a to invoking methods only on: a itself, m's parameters, objects instantiated within m, a's direct attributes, and accessible global variables.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] lod-is-specific-case-of-loose-coupling
The Law of Demeter is a specific case of loose coupling and a corollary of information hiding and the principle of least privilege.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] lod-one-dot-heuristic
The Law of Demeter's 'use only one dot' heuristic means a.m() is acceptable but a.m().n() violates LoD because it reaches through an intermediate object.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] lod-tradeoff-wmc-vs-rfc
Following the Law of Demeter increases maintainability but can increase Weighted Methods per Class (WMC) due to wrapper methods, which correlates with more bugs (Basili et al., 1996); however, lower Response For a Class (RFC) from LoD compliance reduces bug probability.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] lod-facade-applies-at-subsystem-level
The Facade pattern is a structural mechanism for applying the Law of Demeter at the subsystem level.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] lod-layered-architectures-systematic-application
Layered architectures are a systematic application of the Law of Demeter — code may only call within its layer or the next layer down; layer skipping violates LoD.
- Source: entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter

### [ACCEPT] mediator-is-behavioral-gof-pattern
The Mediator pattern is a behavioral GoF design pattern that defines an object encapsulating how a set of objects interact, replacing direct object-to-object references with indirection through a central mediator.
- Source: entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern

### [ACCEPT] mediator-four-participants
The Mediator pattern has four participants: Mediator (communication interface), ConcreteMediator (knows all colleagues and coordinates), Colleague (interface for mediated communication), and ConcreteColleague (communicates only through its mediator).
- Source: entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern

### [ACCEPT] mediator-colleagues-only-know-mediator
In the Mediator pattern, colleague objects are loosely coupled — they only refer to and know about their mediator, not about each other.
- Source: entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern

### [ACCEPT] mediator-vs-facade-directionality
The Mediator pattern enables multidirectional cooperative communication among peers, while the Facade pattern defines a simplified unidirectional interface to a subsystem.
- Source: entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern

### [ACCEPT] mediator-god-object-tradeoff
A trade-off of the Mediator pattern is that the mediator itself can become a 'god object' as it centralizes interaction logic, which may grow complex.
- Source: entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern

### [ACCEPT] mediator-often-uses-observer-internally
Mediator implementations often use the Observer pattern internally to notify colleagues of changes.
- Source: entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern

### [ACCEPT] memento-is-behavioral-gof-pattern
The Memento pattern is a behavioral GoF design pattern that captures and externalizes an object's internal state without violating encapsulation, so the object can be restored to that state later.
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] memento-three-participants
The Memento pattern has three participants: Originator (object whose state is saved), Memento (immutable snapshot of that state), and Caretaker (manages when to save/restore but never inspects memento contents).
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] memento-encapsulation-central-goal
Encapsulation is the central design goal of the Memento pattern — the Caretaker must not inspect or modify Memento contents; only the Originator can read them back.
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] memento-requires-deep-copy-for-mutable-state
When the Originator's state contains mutable objects, the Memento must store a deep copy rather than a reference to preserve correct snapshot semantics.
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] memento-only-captures-single-object-state
The Memento pattern only captures one object's state — it does not handle cascading state across multiple objects or external resources.
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] memento-used-with-command-for-undo
The Memento and Command patterns are often used together — Command records the operation while Memento stores the state needed to undo it.
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] memento-java-static-inner-class
In Java, the Memento is typically implemented as a static inner class of the Originator to restrict access to its stored state.
- Source: entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern

### [ACCEPT] mixin-reuse-without-is-a-relationship
Mixins provide code reuse without establishing an 'is-a' relationship — behavior is 'included' rather than 'inherited', which is the key distinction from class inheritance.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-originated-in-flavors-lisp
Mixins originated in the Flavors system on Symbolics Lisp Machines (Howard Cannon), with the name inspired by mix-in toppings at Steve's Ice Cream Parlor in Somerville, Massachusetts.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-avoids-diamond-problem
Mixins provide a mechanism for multiple inheritance without the diamond problem — the ambiguity that arises when a class inherits from two classes sharing a common ancestor.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-python-mro-order-matters
In Python, mixin order in the class declaration affects Method Resolution Order (MRO) — the mixin is typically listed first so its methods take priority.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-ruby-uses-modules-include
Ruby implements mixins via modules and the include keyword, not class inheritance — e.g., including Comparable and defining <=> gives <, <=, >, >= for free.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-java-default-methods-since-java8
Java achieves mixin-like behavior through default methods on interfaces, available since Java 8; C# added the same capability in C# 8.0.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-clos-method-combinations
CLOS supports method combinations (:before, :after, :around, and arithmetic like +) that allow mixins to augment rather than replace existing behavior, and CALL-NEXT-METHOD invokes the shadowed method from within an :around method.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-cpp-crtp-pattern
C++ traditionally implements mixins via the Curiously Recurring Template Pattern (CRTP), where a base class template takes the derived class as a template parameter.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-no-direct-instances
Mixins typically have no direct instances — they exist solely to contribute behavior to other classes.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] mixin-vs-decorator-composition-level
Both mixins and the Decorator pattern add behavior, but decorators wrap at the object level while mixins compose at the class level.
- Source: entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin

### [ACCEPT] visitor-pattern-separates-algorithm-from-object-structure
The Visitor pattern separates an algorithm from the object structure it operates on, allowing new operations to be added without modifying element classes.
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-uses-double-dispatch
The Visitor pattern simulates double dispatch in single-dispatch languages: element.accept(visitor) dispatches on element type, then visitor.visit(this) dispatches on visitor type.
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-trade-off-new-ops-vs-new-types
The Visitor pattern makes adding new operations easy (add a new visitor) but adding new element types hard (every existing visitor must be updated).
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-is-gof-behavioral
The Visitor pattern is one of the twenty-three Gang of Four design patterns, classified as a behavioral pattern.
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-implements-open-closed-principle
The Visitor pattern is a primary mechanism for satisfying the Open/Closed Principle: element classes are closed for modification but open for extension via new visitor implementations.
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-unnecessary-with-sum-types
Languages with sum types and pattern matching (e.g., ML, Rust, Haskell) largely obviate the Visitor pattern because the compiler enforces exhaustive case handling natively.
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-multiple-dispatch-dissolves
In languages supporting multiple dispatch (e.g., Common Lisp), the Visitor pattern dissolves into ordinary generic function overloading with no accept/visit ceremony needed.
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] visitor-pattern-three-participants
The Visitor pattern has three participants: Visitor (declares visit methods per element type), Element (declares accept(visitor) calling visitor.visit(this)), and Client (constructs object structure and initiates traversal).
- Source: entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern

### [ACCEPT] mvc-invented-by-reenskaug-at-xerox-parc
MVC was invented by Trygve Reenskaug at Xerox PARC in the late 1970s while working on Smalltalk-79; his original design had four parts: Model, View, Thing, and Editor.
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] mvc-three-components
MVC divides application logic into three components: Model (data/logic), View (presentation), and Controller (input handling/mediation).
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] mvc-observer-and-strategy-patterns
MVC relies on the Observer pattern for model-to-view notification and the Strategy pattern for swappable controllers.
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] django-mtv-renames-mvc-components
Django uses an MTV variant of MVC where 'view' means controller and 'template' means view.
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] webobjects-1996-drove-web-mvc-adoption
NeXT's WebObjects (1996), originally written in Objective-C, drove MVC adoption in web development.
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] smalltalk80-views-talk-to-model-and-controller
In Smalltalk-80, views communicate with both model and controller; in WebObjects, views talk only to the controller.
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] mvc-variants-hmvc-mva-mvp-mvvm-adr
HMVC, MVA, MVP, MVVM, and Action-Domain-Responder (ADR) all evolved from MVC.
- Source: entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller

### [ACCEPT] ooad-equals-ooa-plus-ood
OOAD comprises OOA (what the system must do) and OOD (how it will be built); OOA produces conceptual models, use cases, system sequence diagrams, UI docs, and relational data models.
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] open-closed-principle-definition
The Open-Closed Principle states that modules should be open for extension (e.g., via subclassing) but closed for modification (stable interfaces).
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] acyclic-dependencies-principle-dag
The Acyclic Dependencies Principle requires that the dependency graph of packages/components form a directed acyclic graph (DAG) with no cycles.
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] composite-reuse-principle-from-gof
The Composite Reuse Principle (favor polymorphic composition over inheritance) originates from the Gang of Four.
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] ooad-favors-iterative-over-waterfall
OOAD strongly favors iterative and incremental approaches over waterfall, as formulated by the Unified Process, acknowledging that analysis, design, and coding inform each other continuously.
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] ooa-integrates-process-and-data-in-objects
OOA organizes requirements around objects that integrate both process and data, unlike traditional methods that model data (ER diagrams) and behavior (flowcharts) separately.
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] dependency-injection-passes-dependencies-in
Dependency injection means needed objects are passed in rather than created internally, improving testability and decoupling.
- Source: entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design

### [ACCEPT] simula-first-oop-language
Simula (1961-1967) is generally accepted as the first OOP language, introducing classes, inheritance, and dynamic binding.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] alan-kay-coined-oop-term
Alan Kay coined the term 'object-oriented programming' in 1967 and created Smalltalk at Xerox PARC in the 1970s.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] oop-three-pillars
The three commonly cited pillars of OOP are encapsulation, inheritance, and polymorphism, though the exact feature set defining OOP is contested.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] gof-23-patterns-5-7-11
The Gang of Four (1994) cataloged 23 design patterns: 5 Creational, 7 Structural, and 11 Behavioral.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] liskov-substitution-principle-definition
The Liskov Substitution Principle (LSP) states that a subclass instance must be substitutable wherever the superclass is expected; it is undecidable in general and violated by the circle-ellipse problem with mutable objects.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] go-omits-inheritance-favors-composition
Go deliberately omits inheritance, favoring composition ('has-a' over 'is-a').
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] god-object-antipattern
God Object is an anti-pattern in OOP describing an object that knows or does too much.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] open-recursion-via-this-self
Open recursion allows methods to call other methods on the same object via 'this'/'self', enabling late binding where a superclass method invokes a subclass override.
- Source: entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming

### [ACCEPT] observer-pattern-behavioral-gof
The Observer pattern is a behavioral design pattern from the GoF catalog where a subject maintains a list of observers and notifies them of state changes.
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] observer-vs-pubsub-no-broker
Observer pattern uses direct references between subject and observers with no intermediary broker; Publish-Subscribe uses a broker, decoupling publishers from subscribers.
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] observer-typically-synchronous-pubsub-async
The Observer pattern is typically synchronous (subject calls observer methods directly); Publish-Subscribe is typically asynchronous.
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] lapsed-listener-problem-weak-references
The lapsed listener problem is the canonical memory leak risk in the Observer pattern — strong references to unregistered observers prevent garbage collection; mitigated with weak references.
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] java-observer-deprecated-since-java-9
java.util.Observer and java.util.Observable were deprecated since Java 9 due to their limited model.
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] observer-subject-interface-attach-detach-notify
The Observer pattern's standard subject interface provides attach(observer), detach(observer), and notify(); the observer interface provides update(subject).
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] csharp-iobservable-iobserver-idisposable
C# provides built-in IObservable<T> and IObserver<T> interfaces with Subscribe() returning an IDisposable for clean observer unsubscription.
- Source: entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern

### [ACCEPT] polymorphism-three-major-forms
The three major forms of polymorphism are ad hoc (overloading), parametric (generics), and subtyping (inheritance-based).
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] strachey-1967-adhoc-parametric-cardelli-1985-subtyping
Strachey (1967) originally classified polymorphism into ad hoc and parametric; Cardelli & Wegner (1985) added subtyping as a third form.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] vtable-mechanism-for-dynamic-dispatch
In most OO languages, subtype polymorphism is implemented via a vtable (virtual table): each class has a table of function pointers, and each object holds a pointer to its class's vtable, enabling late binding.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] single-dispatch-vs-multiple-dispatch
Single dispatch resolves methods based only on the receiver object's type; multiple dispatch (e.g., Common Lisp Object System) resolves based on the runtime types of all arguments.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] system-f-foundation-of-parametric-polymorphism
System F (polymorphic lambda calculus, by Reynolds and Girard) is the formal foundation of parametric polymorphism.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] monomorphization-cpp-rust-static-dispatch
Monomorphization (used by C++ and Rust) generates specialized code for each concrete type, enabling static dispatch for parametric polymorphism at the cost of larger binary size.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] polymorphism-historical-firsts-algol68-ml-simula
Historical firsts for polymorphism: ALGOL 68 for ad hoc polymorphism, ML for parametric polymorphism, Simula for inclusion (subtype) polymorphism.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] adhoc-polymorphism-not-fundamental-type-system-feature
Ad hoc polymorphism (function/operator overloading) is not a fundamental feature of the type system — the compiler treats overloaded functions as entirely distinct functions.
- Source: entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)

### [ACCEPT] gof-authors-gamma-helm-johnson-vlissides
The Gang of Four (GoF) authors are Gamma, Helm, Johnson, and Vlissides, who published Design Patterns: Elements of Reusable Object-Oriented Software in 1994
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern

### [ACCEPT] design-patterns-originated-christopher-alexander-1977
Design patterns originated from Christopher Alexander's architectural pattern language concept (1977), adapted to software by Kent Beck and Ward Cunningham at OOPSLA 1987
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern

### [ACCEPT] four-pattern-categories-creational-structural-behavioral-concurrency
The four design pattern categories are Creational (object creation), Structural (class/object composition), Behavioral (object collaboration), and Concurrency (concurrent processing)
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern

### [ACCEPT] norvig-16-of-23-gof-patterns-simplified-in-lisp
Peter Norvig demonstrated that 16 of 23 GoF patterns are simplified or eliminated in Lisp/Dylan, suggesting patterns can signal missing language features
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern

### [ACCEPT] pattern-abstraction-hierarchy-four-levels
The pattern abstraction hierarchy has four levels from coarse to fine: Architecture Style > Architecture Pattern > Design Pattern (class/object level) > Implementation Pattern (language idiom)
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern

### [ACCEPT] hannemann-kiczales-aop-removed-dependencies-17-of-23-gof
Hannemann and Kiczales showed that aspect-oriented programming (AspectJ) removed code-level dependencies from 17 of 23 GoF patterns
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern

### [ACCEPT] gof-seven-structural-patterns
The GoF defines seven canonical structural patterns: Adapter, Bridge, Composite, Decorator, Facade, Flyweight, and Proxy
- Source: entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern

### [ACCEPT] state-pattern-is-behavioral-gof-models-fsm
The State pattern is a behavioral GoF pattern that models finite-state machines in an object-oriented way, where concrete states are classes and transitions are method calls that swap the state object
- Source: entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern

### [ACCEPT] state-pattern-transitions-initiated-by-concrete-states
In the State pattern, state transitions are initiated by the concrete state objects themselves (they call setState on the context), not by the context
- Source: entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern

### [ACCEPT] state-vs-strategy-transition-control-difference
State and Strategy patterns are structurally identical (context delegates to an interface), but in State the state objects control transitions internally, while in Strategy the client selects the algorithm externally
- Source: entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern

### [ACCEPT] strategy-pattern-composition-over-inheritance
The Strategy pattern is the canonical example of composition over inheritance: behavior is composed via separate strategy objects rather than inherited through subclasses
- Source: entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern

### [ACCEPT] strategy-pattern-supports-open-closed-principle
The Strategy pattern directly supports the Open/Closed Principle: new algorithms are added as new classes without modifying existing context code
- Source: entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern

### [ACCEPT] template-method-vs-strategy-inheritance-vs-composition
Template Method uses inheritance to vary individual algorithm steps (white-box reuse), while Strategy uses composition to swap entire algorithm objects (black-box reuse)
- Source: entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern

### [ACCEPT] template-method-abstract-vs-hook-methods
Template Method pattern defines two types of helper methods: abstract methods (primitive operations) that subclasses must implement, and hook methods with empty default bodies that subclasses may optionally override
- Source: entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern

### [ACCEPT] template-method-subclass-must-not-override-template
In the Template Method pattern, subclasses must not override the template method itself (it should be final/non-virtual) — they may only override the abstract and hook helper methods
- Source: entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern

### [ACCEPT] template-method-is-inversion-of-control
The Template Method pattern is a foundational mechanism for inversion of control (Hollywood Principle): the base class drives execution by calling down to subclass-provided steps, not the reverse
- Source: entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern

### [ACCEPT] decorator-solves-subclass-explosion
The Decorator pattern solves exponential subclass proliferation by composing behavior at runtime instead of through inheritance
- Source: entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern

### [ACCEPT] bridge-vs-adapter-upfront-vs-retrofit
Bridge is designed up-front to let abstraction and implementation vary independently, while Adapter retrofits interface compatibility after the fact
- Source: entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern

### [ACCEPT] flyweight-pattern-space-optimization-shared-state
The Flyweight pattern achieves space optimization by sharing intrinsic (common) state across many objects while keeping extrinsic (context-specific) state external
- Source: entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern

### [ACCEPT] mutable-state-patterns-unsuited-for-functional-programming
Design patterns that imply mutable state may be unsuited for functional programming languages, and some patterns become unnecessary when a language has built-in support for the problem they solve
- Source: entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern


---

**Generated:** 2026-11-11
**Source:** 56 entries from /home/forge/workspace/entries/
**Model:** openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dip-goals-loose-coupling-reusability-swappability
The goal of DIP is loose coupling, increased reusability of high-level policy layers, and the ability to swap low-level implementations without affecting higher-level code.
- Source: /home/forge/workspace/entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dip-abstract-layer-enables-low-level-substitution
Introducing an abstract layer between high-level and low-level modules reduces coupling and enables substitution of low-level implementations.
- Source: /home/forge/workspace/entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dip-uses-adapter-for-existing-services
When lower-level components are closed or existing services must be reused, an Adapter mediates between the service and the DIP abstraction.
- Source: /home/forge/workspace/entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dip-excessive-interface-usage-requires-plumbing-code
Over-generalized interfaces and excessive interface usage demand more plumbing code such as factories and DI frameworks.
- Source: /home/forge/workspace/entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dip-is-ioc-applied-to-module-dependencies
DIP is a specific manifestation of Inversion of Control applied to module dependencies.
- Source: /home/forge/workspace/entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dip-mvc-example-controllers-own-abstractions
In an MVC DIP example, UI and ApplicationLayer contain concrete classes while Controllers contains abstractions, and both concrete layers depend on the controller abstractions.
- Source: /home/forge/workspace/entries/2026/06/19/dependency-inversion-principle.md
- Source URL: https://en.wikipedia.org/wiki/Dependency_inversion_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] isp-fat-interface-serves-unrelated-clients
A fat interface or class serves multiple unrelated clients and exposes every method to every consumer regardless of relevance.
- Source: /home/forge/workspace/entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] isp-prevents-cascading-change
Without ISP, modifying one part of a tightly coupled system forces changes throughout the codebase, a cascading change problem.
- Source: /home/forge/workspace/entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] isp-xerox-solution-job-implements-role-interfaces
In the Xerox ISP solution, the Job class implements segregated interfaces such as IStapleJob, IPrintJob, and IFaxJob, and each client depends only on its relevant interface.
- Source: /home/forge/workspace/entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] isp-canonical-violation-atm-transaction-ui
The canonical ISP violation example is the ATM Transaction UI from Robert C. Martin's 'Agile Software Development' book.
- Source: /home/forge/workspace/entries/2026/06/19/interface-segregation-principle.md
- Source URL: https://en.wikipedia.org/wiki/Interface_segregation_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-formal-definition-property-preservation
LSP's formal definition is: if S is a subtype of T, then every property provable about T-objects must also hold for S-objects.
- Source: /home/forge/workspace/entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-new-exceptions-must-be-subtypes
LSP signature requirements state that new exceptions thrown by a subtype must be subtypes of exceptions thrown by the supertype.
- Source: /home/forge/workspace/entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-mutable-point-subtype-immutable-point-violates-history
A mutable point as a subtype of an immutable point violates LSP's history constraint.
- Source: /home/forge/workspace/entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-mirrors-design-by-contract
LSP's pre/postcondition and invariant rules directly mirror Bertrand Meyer's Design by Contract methodology, though Meyer's original formulation lacked handling for aliasing.
- Source: /home/forge/workspace/entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-circle-ellipse-problem-analogue
The Circle-Ellipse problem is the geometric analogue of the Rectangle-Square problem and has the same structural LSP violation pattern.
- Source: /home/forge/workspace/entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-enables-ocp
LSP enables the Open/Closed Principle because safely substitutable subtypes allow systems to be extended without modifying existing code.
- Source: /home/forge/workspace/entries/2026/06/19/liskov-substitution-principle.md
- Source URL: https://en.wikipedia.org/wiki/Liskov_substitution_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ocp-polymorphic-version-separates-interface-and-implementation-reuse
The polymorphic version of OCP deliberately separates interface reuse via inheritance from implementation reuse.
- Source: /home/forge/workspace/entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ocp-motivation-changing-code-risks-breaking-clients
OCP's key motivation is that changing existing code risks breaking existing clients, while extending via new classes or implementations avoids that risk.
- Source: /home/forge/workspace/entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ocp-strategy-and-template-method-are-common-vehicles
Strategy and Template Method patterns are common implementation vehicles for achieving OCP in practice.
- Source: /home/forge/workspace/entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ocp-meyer-version-adds-descendants-without-modifying-original
In Meyer's OCP version, adding a descendant class does not modify the original class or disturb existing clients.
- Source: /home/forge/workspace/entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ocp-robustness-principle-related-at-api-boundaries
The Robustness Principle is a related concern about stability under change, applied at protocol or API boundaries rather than class design.
- Source: /home/forge/workspace/entries/2026/06/19/open-closed-principle.md
- Source URL: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-distinct-roles-are-separate-actors
In SRP, distinct roles such as accountant and database administrator represent separate actors even if performed by the same person, and each module should serve a single role.
- Source: /home/forge/workspace/entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-design-test-more-than-one-actor
An SRP design test is to ask which actors might request changes to a class; if more than one actor is identified, the class likely violates SRP and should be split.
- Source: /home/forge/workspace/entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-violation-increases-coupling
Violating SRP increases coupling, so changes to one concern risk breaking unrelated concerns in the same module.
- Source: /home/forge/workspace/entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-is-class-level-separation-of-concerns
SRP can be viewed as the class-level application of the broader separation of concerns principle.
- Source: /home/forge/workspace/entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-chain-of-responsibility-complements-srp
The Chain-of-Responsibility pattern can distribute responsibilities across handlers, complementing SRP at the architectural level.
- Source: /home/forge/workspace/entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-vs-information-hiding-axis-vs-mechanism
SRP and information hiding both localize the impact of change; SRP focuses on the axis of change (actor), while information hiding focuses on the mechanism of change (implementation detail).
- Source: /home/forge/workspace/entries/2026/06/19/single-responsibility-principle.md
- Source URL: https://en.wikipedia.org/wiki/Single-responsibility_principle
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] solid-addresses-software-rot
SOLID addresses software rot, the gradual degradation of software quality over time.
- Source: /home/forge/workspace/entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ocp-violation-risks-regressions
Violating the Open-Closed Principle means every new feature risks breaking existing functionality.
- Source: /home/forge/workspace/entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] isp-violation-produces-fat-interfaces-stubs
Violating the Interface Segregation Principle leads to fat interfaces that force implementors to provide stub or no-op methods.
- Source: /home/forge/workspace/entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lsp-violation-breaks-polymorphism
Violating the Liskov Substitution Principle breaks polymorphism.
- Source: /home/forge/workspace/entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gof-patterns-apply-solid-principles
Strategy, Template Method, Factory, and Decorator are direct applications of one or more SOLID principles.
- Source: /home/forge/workspace/entries/2026/06/19/solid-overview.md
- Source URL: https://en.wikipedia.org/wiki/SOLID
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-factory-decouples-object-creation-from-usage
The Abstract Factory pattern decouples object creation from object usage.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-factory-products-share-family-theme
All products created by a single concrete Abstract Factory share a common theme or variant.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-factory-returns-abstract-references
An Abstract Factory returns a pointer or reference to an abstract type, never the concrete type.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-factory-implemented-with-factory-methods
Abstract Factory is often implemented using Factory Methods internally.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-factory-has-classic-and-modern-variants
Abstract Factory has a classic structural variant using abstract classes and inheritance and a modern variant using interfaces or protocols with implementation rather than inheritance.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_factory_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_factory_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-type-also-called-existential-type
Abstract types are also known as existential types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-method-has-no-implementation
An abstract method or pure virtual function is declared in an abstract type with no implementation, and concrete subtypes must provide the implementation.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-type-may-be-incomplete-or-pure
Abstract types may provide some implemented methods or none; types with no implementation are called protocols, interfaces, signatures, or class types depending on the language.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-type-approximated-by-traits-mixins-flavors-roles-type-classes
Traits, mixins, flavors, roles, and type classes can implement or approximate abstract types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-class-abstractness-signals-four-ways
An abstract class can be signaled by an explicit keyword, abstract methods, incomplete inheritance, or a dynamic convention.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-method-violations-runtime-in-dynamic-languages
In dynamically typed languages, abstract method violations are detected at runtime, such as Objective-C doesNotRecognizeSelector.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstract_type.md
- Source URL: https://en.wikipedia.org/wiki/Abstract_type
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstraction-hides-irrelevant-implementation-details
Abstraction provides access to functionality while hiding irrelevant implementation details, preserving information relevant in a given context and discarding what is irrelevant.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] control-abstraction-hides-low-level-operations
Control abstraction in programming languages hides low-level register and binary operations, letting programmers express computation at higher levels.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lookup-table-adts-can-use-hash-bst-or-list
A lookup table abstract data type can be implemented as a hash table, binary search tree, or linear list.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] language-abstraction-progression-machine-to-dsl
Language abstraction progresses from machine language to assembly to high-level languages to scripting and domain-specific languages.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstraction-must-be-sound-not-exact
Abstractions need not be exact but must be sound, never giving incorrect answers though they may answer I don't know.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] rice-theorem-makes-abstraction-essential
Rice's theorem states that non-trivial properties of programs are undecidable, making abstraction essential for reasoning about program behavior.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstraction-scope-requires-domain-legacy-detailed-analysis
Determining what to abstract in object-oriented design involves domain analysis, legacy analysis, and detailed object-oriented analysis.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Abstraction_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adapter-naming-convention-classname-to-interface
Adapter classes conventionally follow the naming pattern ClassNameToInterfaceAdapter, such as DAOToProviderAdapter or LightningToMicroUsbAdapter.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adapter-constructor-injects-adaptee
An object adapter constructor typically takes the adaptee as a parameter and stores it as an instance variable.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adapter-runtime-variant-uses-registry-factory
The runtime adapter variant uses a registry or factory to look up adapters dynamically, enabling multiple views of the same data source without altering class hierarchies.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adapter-class-adapter-java-interface-constraint
Class adapters are constrained in languages like Java before JDK 1.8 that do not support multiple inheritance of classes, so the target must be defined as an interface.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ports-and-adapters-decouple-domain-from-external
Ports and Adapters Architecture uses adapters as a core architectural concept to decouple domain logic from external systems.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adapter-solves-three-interface-problems
The Adapter pattern solves three specific problems: reusing a class that lacks the required interface, making incompatible interfaces work together, and providing an alternative interface for a class.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Adapter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Adapter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] weak-reference-pattern-observer-variant
The Weak Reference pattern is an Observer pattern variant that decouples observer from observable to prevent memory leaks in environments lacking automatic weak references.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] externalize-the-stack-technique
Externalize the Stack is a behavioral technique that converts recursive functions into iterative ones using an explicit stack.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-centralizes-observer-distributes
The Mediator pattern centralizes communication through a single coordinator, while the Observer pattern distributes notification directly from subject to dependents.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] single-serving-visitor-optimization
Single-Serving Visitor (SSV) is an optimization of the Visitor pattern for one-time-use traversal scenarios.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] iterator-sequential-access-without-exposing-representation
The Iterator pattern accesses elements sequentially without exposing the underlying representation of the aggregate.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] chain-of-responsibility-vs-command
Chain of Responsibility routes command objects through a chain of handlers, while Command encapsulates actions directly.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Behavioral_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Behavioral_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bridge-creates-two-layers-of-abstraction
The Bridge pattern creates two layers of abstraction: one for the abstraction hierarchy and one for the implementation hierarchy.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bridge-enables-runtime-implementation-selection
The Bridge pattern enables runtime binding, allowing the implementation to be selected or swapped at runtime, unlike compile-time inheritance binding.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bridge-vs-strategy
Both Bridge and Strategy use composition to delegate behavior, but Strategy varies a single algorithm while Bridge separates an entire abstraction from its implementation hierarchy.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bridge-vs-template-method
Template Method uses inheritance to vary steps, while Bridge uses composition to vary the entire implementation.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bridge-complements-abstract-factory
Bridge can be used together with Abstract Factory, which can create the concrete implementors that the Bridge uses.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Bridge_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Bridge_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-vs-factory-method
Factory Method uses inheritance (subclass decides object creation) while Builder uses composition (Director delegates to a Builder object).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-related-to-currying
The Builder pattern is related to Currying in that both involve incremental construction or configuration before producing a final result.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-often-constructs-composite-trees
Builders are often used to construct Composite trees.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-mutability-requirement
In the Builder pattern, builders must be mutable to accumulate state across build steps.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-defers-compile-time-errors-to-runtime
The Builder pattern can defer compile-time errors to runtime in null-safe languages.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-director-controls-step-order
In the Builder pattern, the Director controls the stepwise creation process, and the order of construction steps matters.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-client-retrieves-result-from-builder
In the classic Builder pattern formulation, the Client retrieves the finished product from the Builder, not directly from the Director.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Builder_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Builder_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cor-dynamic-handler-addition
New handlers can be added to the end of a Chain of Responsibility dynamically at runtime.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cor-tree-of-responsibility-variation
A variation of Chain of Responsibility is the tree of responsibility, where handlers act as dispatchers sending commands in multiple directions, potentially involving recursion (e.g., XML interpreters).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cor-collaborates-with-command
Chain of Responsibility processes command objects and is often used together with the Command pattern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cor-handler-srp-alignment
Each handler in Chain of Responsibility encapsulates responsibility for one type of request, aligning with the Single Responsibility Principle.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cor-tree-variant-resembles-composite
The tree-of-responsibility variant of Chain of Responsibility resembles the Composite pattern's recursive structure.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cor-solves-two-problems
Chain of Responsibility solves two problems: avoiding sender-receiver coupling and allowing more than one receiver to handle a request.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Chain-of-responsibility_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] object-methods-receive-object-reference
Object methods receive an implicit or explicit reference to the object, while class methods do not receive an object reference.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] instantiation-allocates-initializes-returns-reference
Instantiation constructs an object from a class by allocating memory, initializing state, and returning a reference to the object.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] data-fields-define-memory-layout-except-python
In most languages, class data fields (properties, attributes, member variables) define the memory layout of instances, but Python uses associative key-value containers instead.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pure-oo-languages-implicit-root-object
In purely object-oriented languages like Java and C#, all classes implicitly extend a root Object class.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inner-class-not-tied-to-enclosing-instance
An inner class is defined within another class but is not necessarily tied to the enclosing instance's lifecycle.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] local-class-scoped-to-block
A local class is defined within a procedure or function and its name is scoped to that block.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] containment-by-value-ties-lifetimes
In composition, containment by value ties the lifetimes of the contained and containing objects, while containment by reference does not.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] constructors-destructors-handle-lifecycle
Constructors and destructors allow custom logic at object lifecycle events (instantiation and destruction).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Class_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Class_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cohesion-high-correlates-with-robustness-reliability-reusability-understandability
High cohesion correlates with robustness, reliability, reusability, and understandability.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] high-cohesion-reduces-complexity-improves-maintainability-increases-reusability
High cohesion reduces complexity, improves maintainability, and increases reusability.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cohesion-increases-when-methods-share-functionality-related-activities-grouped-source-files
Cohesion increases when methods share common functionality, perform a small number of related activities, and related methods are grouped together in source files.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] coincidental-and-logical-cohesion-empirically-inferior
Empirical studies show coincidental and logical cohesion are inferior to other cohesion types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] communicational-and-sequential-cohesion-empirically-very-good
Empirical studies show communicational and sequential cohesion are very good.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] functional-cohesion-empirically-superior
Empirical studies show functional cohesion is superior.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] perfect-atomic-cohesion-irreducible-computation
Perfect or atomic cohesion describes a module that cannot be decomposed further because it is a single irreducible computation.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Cohesion_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] command-object-stores-receiver-reference-and-parameter-values
A Command object stores a reference to its Receiver via aggregation and holds parameter values for the receiver's method.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] command-client-decides-receiver-command-invoker-mappings
In the Command pattern, the Client decides which receivers map to which commands and which commands map to which invokers.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] command-pattern-solves-hardwired-requests-compile-time-coupling
The Command pattern solves the problem of hard-wiring requests into classes, which couples them at compile-time and prevents runtime configuration.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] command-memento-complement-undo-state-vs-operations
The Command and Memento patterns are often used together for undo: Memento stores state snapshots while Command stores operations.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] command-strategy-differ-algorithm-vs-complete-request
Command and Strategy both encapsulate behavior, but Strategy replaces an algorithm while Command encapsulates a complete request with its receiver.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] macrocommand-composite-executes-multiple-commands-as-one
The Composite pattern enables a MacroCommand that executes multiple commands as one.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] command-pattern-enables-serialized-network-remote-execution
The Command pattern enables entire command objects to be serialized and sent across a network for remote execution.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Command_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Command_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] composite-enables-uniform-treatment-individual-and-composed-objects
The Composite pattern lets clients treat individual objects and compositions of objects uniformly through a shared Component interface.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] composite-recursive-aggregation-sums-child-results
Composite recursive aggregation can compute results such as total price by summing the composite's own value and each child's recursively computed value.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] composite-uses-has-a-relationship-for-child-components
Composite objects use a has-a (composition) relationship to hold child Components, not is-a inheritance, for the child collection.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] composite-fixed-tree-can-omit-child-manipulation-from-component
If a Composite tree structure is fixed after construction, child-manipulation methods can be omitted from the Component interface entirely.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] decorator-and-composite-both-use-recursive-composition
Decorator and Composite patterns are often used together and both rely on recursive composition.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-applied-to-composite-defines-operations-without-modifying-component
Visitor is frequently applied to Composite structures to define operations across heterogeneous node types without modifying the Component classes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-leaf-nodes-shared-when-no-intrinsic-state
Leaf nodes in a Composite tree are candidates for Flyweight sharing when they have no intrinsic state.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-can-construct-composite-trees-step-by-step
The Builder pattern can construct Composite trees step-by-step.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composite_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Composite_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] composition-over-inheritance-aka-composite-reuse-with-forwarding
Composition over inheritance is sometimes called composite reuse or composition with forwarding.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-relationships-static-require-recompilation
Inheritance relationships are static and require recompilation to change behavior.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] java-study-2013-24-percent-inheritance-code-reuse
A 2013 empirical study of 93 Java projects found roughly 24% of inheritance uses were purely for code reuse.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-behavior-combinations-cause-class-explosion
Using inheritance for different combinations of behaviors can force combinatorial explosion of intermediate classes such as VisibleAndSolid and VisibleAndMovable.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] languages-mitigate-composition-boilerplate-via-delegation-features
Languages mitigate composition's forwarding boilerplate via features such as Go type embedding, Kotlin built-in delegation syntax, Rust/Swift trait or protocol default implementations, Java 8+/C# 8+ default interface methods, Scala 3 export clauses, and PHP 5.4+ traits.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-more-concise-when-base-class-provides-many-defaults
When a base class provides many default methods and only a few need overriding, inheritance is more concise because composition would require forwarding all methods.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-requires-lsp-compliance-composition-avoids-subtyping-contract
Inheritance requires Liskov Substitution Principle compliance, whereas composition avoids the subtyping contract altogether.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] composition-delegates-swapped-runtime-implement-state-pattern
Swapping composition delegates at runtime to change behavior is exactly the State pattern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Composition_over_inheritance.md
- Source URL: https://en.wikipedia.org/wiki/Composition_over_inheritance
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] coupling-measures-inter-module-interdependence
Coupling is the degree of interdependence between software modules and measures how closely connected two routines or modules are.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pressman-coupling-metric-range-0-67-to-1-0
The Pressman coupling metric C(module) ranges from approximately 0.67 for low coupling to 1.0 for high coupling.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] oo-subclass-coupling-child-depends-parent-parent-independent-child
Subclass coupling is an OO-specific coupling type where the child depends on the parent, but the parent does not depend on the child.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] oo-temporal-coupling-actions-bundled-by-time-only
Temporal coupling is an OO-specific coupling type where actions are bundled into one module only because they happen at the same time.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dynamic-coupling-measured-runtime-addresses-static-precision-loss
Dynamic coupling is measured at runtime and addresses precision loss of static metrics when dynamic binding or inheritance is heavily used.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] semantic-coupling-measures-conceptual-similarity-via-comments-identifiers-lsi
Semantic coupling measures conceptual similarity between entities using comments, identifiers, and techniques such as Latent Semantic Indexing.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] logical-evolutionary-coupling-detected-from-release-history
Logical or evolutionary coupling is detected from release history and identifies modules that tend to change together.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] coupling-increases-classes-attribute-call-reference-subclass
Coupling increases between classes A and B if A has an attribute of type B, calls services on B, has a method referencing B as a parameter or return type, or is a subclass of B.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Coupling_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] creational-patterns-encapsulate-instantiation-knowledge
Creational patterns encapsulate knowledge of which concrete classes a system uses and how instances of those classes are created and combined.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] creational-patterns-abstract-instantiation-process
Creational patterns abstract the instantiation process so a system is independent of how its objects are created, composed, and represented.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] creator-concretecreator-structure
In the creational pattern structure, a Creator declares the object interface and returns objects, while a ConcreteCreator implements the object's interface.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] builder-separates-construction-from-representation
The Builder pattern separates construction of a complex object from its representation so the same construction process can create different representations.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dependency-injection-accepts-objects-from-injector
Dependency Injection accepts required objects from an injector rather than creating them directly.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Creational_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Creational_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] decorator-wraps-component-forwards-requests
A Decorator wraps a Component, implements the same interface, forwards all requests to the wrapped object, and adds behavior before or after forwarding.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] decorator-stacking-order-matters
Multiple decorators can be layered on a single object, and the order of wrapping affects the resulting behavior.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] decorator-holds-component-reference-via-composition
The Decorator holds a reference to the Component via composition rather than inheriting the Component's state.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-decorator-forwards-concrete-decorator-overrides
The abstract Decorator class forwards all methods to the wrapped component, while ConcreteDecorator subclasses override specific methods to add behavior.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-static-decorator-uses-template-mixin-inheritance
C++ offers a static decorator variant that uses template or mixin inheritance for compile-time composition.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Decorator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Decorator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] delegation-evaluates-member-in-sender-context
Delegation evaluates a member of a receiver object in the context of a sender object.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] explicit-delegation-manual-responsibility-passing
Explicit delegation manually passes responsibilities between objects and works in any object-oriented language.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] implicit-delegation-requires-language-lookup-support
Implicit delegation uses language-level method lookup rules and requires language support such as that found in Self or JavaScript.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dual-inheritance-requires-lookup-resolution-rules
When a language supports both delegation and inheritance, dual inheritance introduces method lookup ambiguity that requires additional resolution rules.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cocoa-delegation-customizes-framework-behavior
macOS Cocoa/NeXTStep uses delegation extensively to customize framework component behavior, for example through methods such as windowShouldClose:.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Delegation_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] design-patterns-book-published-1994-by-gof-authors
Design Patterns: Elements of Reusable Object-Oriented Software was published in 1994 by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides, collectively known as the Gang of Four.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] design-patterns-book-sales-and-award
The Design Patterns book sold over 500,000 copies in 14 languages and received the 2005 ACM SIGPLAN Programming Languages Achievement Award.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gof-pattern-template-sections
Each GoF pattern is documented with intent, motivation, applicability, structure, participants, collaborations, consequences, implementation notes, sample code, known uses, and related patterns.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] toolkit-vs-framework-definition
In the GoF book, a toolkit is an object-oriented subroutine library, while a framework is a set of cooperating classes forming a reusable design.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] parameterized-types-allow-deferred-dependent-types
Parameterized types such as generics or templates allow types to be defined without specifying all dependent types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Design_Patterns.md
- Source URL: https://en.wikipedia.org/wiki/Design_Patterns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] dan-ingalls-smalltalk-multiple-polymorphism
Dan Ingalls first described the double dispatch technique in Smalltalk and called it multiple polymorphism.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] eiffel-agent-double-dispatch-approach
In Eiffel, double dispatch can be implemented by wrapping methods as first-class agent objects and passing them instead of making direct calls.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] double-dispatch-common-use-cases
Common uses of double dispatch include collision detection, rendering or display on heterogeneous outputs, event handling with typed events and typed handlers, and scheduling or matching algorithms.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] double-dispatch-does-not-solve-expression-problem
Double dispatch does not solve the expression problem: adding a new shape type requires adding a method to every port or surface class.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ruby-double-dispatch-shape-delegates-to-port
In Ruby, double dispatch can eliminate type-case logic by having a shape delegate to a port and pass itself using a type-specific method name such as display_rectangle.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Double_dispatch.md
- Source URL: https://en.wikipedia.org/wiki/Double_dispatch
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-access-specifiers-not-information-hiding
The ISO C++ standard calls public, private, and protected 'access specifiers' rather than information-hiding mechanisms.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-friend-keyword-bypasses-access
C++ provides the friend keyword for selective access that can bypass private and protected access restrictions.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] yo-yo-problem-deep-inheritance-hierarchies
The yo-yo problem refers to deep inheritance hierarchies that are hard to follow and debug.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] encapsulation-reduces-interdependencies-via-stable-interface
Encapsulation reduces interdependencies between software components by exposing only a stable interface.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Encapsulation_computer_programming.md
- Source URL: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-delegates-to-subsystem-objects
A Facade object implements a simplified interface by delegating calls to appropriate subsystem objects internally.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-client-facade-subsystem-structure
The Facade pattern's structural arrangement is Client → Facade → {Class1, Class2, Class3}.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-stepping-stone-refactoring
Facade can serve as a stepping stone when refactoring monolithic or tightly-coupled systems toward loose coupling.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-hardware-register-protocols
Facade is commonly used with hardware register protocols such as Modbus and I2C to abstract indexed-value access.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-layered-architecture-entry-points
Facade provides entry points at each layer level in layered architectures.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-does-not-require-interface-conformance
Unlike Adapter, Facade does not require the wrapper to conform to a specific interface or support polymorphism.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Facade_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Facade_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] factory-method-participants-four-roles
Factory Method structure has four participant roles: Creator declares the factory method, ConcreteCreator overrides it to return a ConcreteProduct, Product defines the product interface, and ConcreteProduct implements Product.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] factory-method-makes-new-operator-redundant
Factory Method makes the new operator redundant in client code, decoupling callers from concrete class names.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] factory-method-can-use-interface-implementation
Factory Method can also rely on interface implementation as an alternative to subclassing for deciding which concrete class to instantiate.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] abstract-factory-uses-factory-methods
Abstract Factory is often implemented using Factory Methods; Abstract Factory creates families of related objects while Factory Method creates a single object.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] factory-method-real-world-framework-examples
Factory Method appears in frameworks such as HTML5 DOM Document.createElement(), Qt QMainWindow::createPopupMenu, Java javax.xml.parsers.DocumentBuilderFactory, and ADO.NET IDbCommand.CreateParameter.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] simple-factory-not-gof-pattern
Simple Factory is not one of the GoF design patterns, unlike Factory Method and Abstract Factory.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Factory_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Factory_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-participants-four-roles
Flyweight participants include Client (supplies extrinsic state), FlyweightFactory (creates/caches via getFlyweight(key)), Flyweight interface (accepts extrinsic state), and ConcreteFlyweight (stores intrinsic state).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-word-processor-glyph-example
The canonical Flyweight example is a word processor where each character references a shared glyph object for font outline, metrics, and formatting data, while only position is stored per character.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hash-consing-shares-flyweight-idea
Hash consing is the same data-sharing idea as Flyweight and appears in functional programming contexts.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-often-used-in-composite-structures
Flyweight is often used within Composite structures, such as shared leaf nodes in a tree.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-two-caching-strategies-maintained-unmaintained
Flyweight caching has two strategies: maintained (FIFO, push/pop) and unmaintained (bulk initialization at startup, search-based retrieval).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-trades-computation-for-memory
Flyweight trades computational overhead for memory savings and is beneficial when object count is large and shared state is significant.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-concurrency-creation-options
Flyweight concurrency options include pre-instantiating all flyweights (no contention), single-threaded creation (contention, one instance per value), or concurrent creation (no contention, multiple instances per value).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Flyweight_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Flyweight_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-indirection-mediates-components
GRASP's Indirection pattern introduces an intermediate object to mediate between two components, reducing direct coupling; MVC's controller mediating between model and view is a classic example.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-high-cohesion-focused-responsibilities
GRASP's High Cohesion keeps each class focused on a single, well-defined set of related responsibilities; low cohesion leads to classes that are hard to comprehend, reuse, and maintain.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-polymorphism-replaces-conditionals
GRASP's Polymorphism assigns behavior that varies by type to the varying types via polymorphic operations rather than explicit conditional branching.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-patterns-not-mutually-exclusive
GRASP patterns are not mutually exclusive; multiple patterns often apply simultaneously to a single design decision.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-creator-relates-to-factory
GRASP's Creator relates to the Factory pattern, which is an alternative when Creator criteria do not apply or more complex creation logic is needed.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-controller-relates-to-command-facade-layers
GRASP's Controller relates to the Command pattern, Facade pattern, Layers pattern, and Pure Fabrication.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-GRASP_object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] info-hiding-protects-against-internal-representation-change
A module designed with information hiding protects the rest of the program from changes to its internal representation, such as switching a 3D point from three scalars to an array.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] info-hiding-shifts-dependency-to-interfaces
In object-oriented programming, information hiding shifts dependency from uncertain implementations onto well-defined interfaces so clients need not change when the implementation changes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] booch-encapsulation-separates-contractual-interface-from-implementation
Grady Booch defined encapsulation as compartmentalizing the elements of an abstraction that constitute its structure and behavior, serving to separate the contractual interface of an abstraction from its implementation.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] access-modifiers-implement-information-hiding
Access modifiers such as private, protected, and public in languages like Java and C++ are practical mechanisms for implementing information hiding.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] law-of-demeter-enforces-information-hiding
The Law of Demeter is a specific heuristic that enforces information hiding by restricting which objects a method may interact with.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] info-hiding-primary-benefit-localizes-change
The primary benefit of information hiding is localizing the impact of change so evolutionary modifications stay local rather than global.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] well-designed-interface-allows-whole-component-replacement
A well-designed interface lets a component be replaced entirely as long as the new component supports the same public interface.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Information_hiding.md
- Source URL: https://en.wikipedia.org/wiki/Information_hiding
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-models-is-a-composition-models-has-a
Inheritance models is-a relationships, while composition models has-a relationships.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-derived-classes-do-not-inherit-constructors-destructors-operators-friends
In C++, child objects acquire all parent properties except constructors, destructors, overloaded operators, and friend functions.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] csharp-requires-virtual-abstract-override-java-overrides-by-default
Method overriding rules differ by language: C# requires virtual, abstract, or override; Java allows overriding by default.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] circle-ellipse-problem-exemplifies-lsp-violation
The circle-ellipse problem is a classic example of inheritance modeling difficulties and Liskov Substitution Principle violations.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-three-design-constraints-singleness-static-visibility
Inheritance has three design constraints: singleness (single inheritance limits dual roles), static hierarchy fixed at instantiation, and visibility of superclass data to clients.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gosling-would-not-include-implementation-inheritance-in-java-redesign
James Gosling reportedly said he would not include implementation inheritance if redesigning Java.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] go-decouples-inheritance-from-subtyping
The Go programming language decouples inheritance from subtyping entirely.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inheritance_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] multiple-interface-implementation-avoids-diamond-problem
A single class can implement multiple interfaces, providing a form of multiple behavioral inheritance without the diamond problem of multiple class inheritance.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-interfaces-modeled-as-pure-abstract-classes
In C++, interfaces are typically represented as pure abstract classes with all methods abstract and no state.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] python-duck-typing-provides-implicit-interfaces
In Python, duck typing lets any class that implements the expected methods satisfy an interface contract implicitly.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] python-collections-abc-iterable-provides-explicit-interface
Python supports explicit interfaces through Abstract Base Classes such as collections.abc.Iterable.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interfaces-model-can-do-capabilities-inheritance-models-is-a
Inheritance models is-a relationships between classes, while interfaces model can-do capabilities.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interfaces-enable-subtype-polymorphism
Interfaces enable subtype polymorphism so code written against an interface works with any implementing class.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interface_object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interpreter-terminal-expressions-interpret-directly-nonterminal-delegate
In the Interpreter pattern, terminal expressions interpret directly without delegating to children, while nonterminal expressions delegate interpretation to their child expressions.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interpreter-context-carries-global-state
The Interpreter pattern's Context object carries global state needed during interpretation, such as variable bindings.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interpreter-expressions-expose-replace-and-copy-operations
Interpreter pattern expressions commonly expose replace and copy operations in addition to interpret.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] flyweight-can-share-interpreter-terminal-expressions
Terminal expressions that appear many times in an Interpreter AST can be shared using the Flyweight pattern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] iterator-traverses-interpreter-ast
The Iterator pattern is used to traverse the composite AST structure evaluated by the Interpreter pattern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interpreter-avoids-hard-wiring-expressions-into-classes
The Interpreter pattern avoids hard-wiring expressions directly into classes, which would make adding or changing expressions require modifying the class.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] interpreter-used-for-sql-regex-embedded-dsls
The Interpreter pattern is used in real-world systems such as SQL query languages, regular expressions, and embedded domain-specific languages.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Interpreter_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Interpreter_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ioc-enables-runtime-binding-through-abstractions
Inversion of Control enables dynamic flow through abstractions by determining the concrete object satisfying a dependency at runtime rather than compile time.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ioc-requires-compatible-interfaces-for-runtime-binding
Inversion of Control requires objects to have compatible interfaces for runtime binding, such as class A delegating to interface I implemented by class B.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ioc-enables-independent-development-of-framework-and-application-code
Inversion of Control allows reusable framework code and problem-specific application code to be developed independently while operating together.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] service-locator-alternative-to-di-for-runtime-binding
The Service Locator pattern is an alternative to dependency injection for achieving runtime binding of dependencies.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] callbacks-are-basic-ioc-mechanism
Callbacks are the most basic mechanism for Inversion of Control: passing a function to be called by the framework.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ioc-term-dates-to-1988-related-to-jackson-program-inversion
The term Inversion of Control dates to 1988 and relates to Michael Jackson's program inversion concept from the 1970s.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] html-dom-event-listener-exemplifies-ioc
Registering a DOM event listener with document.addEventListener('click', listener, true) exemplifies Inversion of Control because the browser framework controls the event loop and invokes the supplied handler.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Inversion_of_control.md
- Source URL: https://en.wikipedia.org/wiki/Inversion_of_control
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] iterator-client-interaction-sequence
The typical Iterator interaction sequence is: the client calls createIterator() on an Aggregate, the Aggregate creates and returns a ConcreteIterator, and the client calls hasNext()/next() on the iterator.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-and-python-standardize-iterator-syntax
C++ and Python are notable for standardizing iterator syntax at the language level.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-iterators-model-concepts-enabling-compile-time-polymorphism
In C++, iterators model 'concepts' (named sets of requirements), enabling compile-time polymorphism via templates.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] placing-traversal-operations-in-aggregate-interface-is-inflexible
Placing traversal operations directly in the aggregate interface is inflexible because it commits the aggregate to specific traversal operations and prevents adding new ones without interface changes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] some-algorithms-are-necessarily-container-specific
Not all algorithms can be fully decoupled from containers — some are necessarily container-specific.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Iterator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Iterator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lod-three-summary-rules
The Law of Demeter has three summary rules: (1) each unit should have limited knowledge about other units — only closely related ones; (2) only talk to friends, not strangers; (3) only talk to immediate friends.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lod-named-after-demeter-greek-goddess
The Law of Demeter is named after Demeter, the Greek goddess of agriculture, reflecting a 'growing software' (bottom-up) philosophy rather than 'building software.'
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lod-fix-pattern-modify-collaborator-interface-or-direct-reference
To fix a Law of Demeter violation, either modify the intermediate object's interface to serve the request directly (propagating internally) or give the caller a direct reference to the target object.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lod-and-aop-both-originated-from-demeter-project
The Demeter Project birthed both the Law of Demeter and aspect-oriented programming (AOP) ideas; AOP is proposed as a solution to LoD's wrapper method proliferation.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] tell-dont-ask-idiom-reinforces-lod
The Tell, Don't Ask idiom reinforces the Law of Demeter by pushing behavior to the object that owns the data.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lod-also-known-as-dont-talk-to-strangers
The Law of Demeter is also known as 'Don't talk to strangers' (per Larman's Applying UML and Patterns).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Law_of_Demeter.md
- Source URL: https://en.wikipedia.org/wiki/Law_of_Demeter
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-solves-tight-coupling-problems
The Mediator pattern addresses tight coupling between interacting objects, which otherwise makes them hard to implement, change, test, and reuse.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-enables-independent-interaction-logic
The Mediator pattern allows the interaction logic to be changed independently from the colleague objects themselves.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-is-not-broker-pattern
The Mediator pattern is not the same as the Broker pattern — despite superficial similarity, they solve different problems.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-improves-colleague-reusability-and-testability
The Mediator pattern improves reusability and testability of individual colleague classes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-event-based-variant-uses-subscription
In an event-based Mediator variant (e.g., chat room), the mediator exposes an event, colleagues subscribe to it on construction, sending goes through mediator.Send(), and receiving is handled by event callbacks.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mediator_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Mediator_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] memento-caretaker-can-maintain-list-of-mementos
A Caretaker can maintain a list or stack of mementos, enabling multi-level undo or selective rollback.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] memento-prng-seed-canonical-example
The canonical Memento example is a pseudorandom number generator (PRNG) where the seed acts as the memento — restoring the seed reproduces the same sequence.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] memento-originator-operations-createMemento-restore
The Originator interface in the Memento pattern provides createMemento() to capture current internal state into a new Memento and restore(memento) to reset internal state from a given Memento.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] memento-alternative-implementations-serialization-package-proxy
Beyond inner class, Memento can be implemented via serialization, package-private or module-scoped classes, or proxy-based access.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] memento-can-save-iterator-position
An Iterator's position can be saved and restored via Memento.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] memento-analogous-to-version-control-commit
Conceptually, each version control commit is a memento of repository state.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Memento_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Memento_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-is-interface-with-implemented-methods
A mixin can be viewed as an interface that also provides method implementations, not just a contract.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-enforces-dependency-inversion-principle
The mixin pattern is an example of enforcing the dependency inversion principle.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-scala-uses-with-keyword
In Scala, traits are mixed in using extends for the first trait (or superclass) and with for subsequent traits; per-instance mixin is possible via anonymous types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-rust-traits-default-methods
Rust traits serve as mixins with default method implementations that implementing types can selectively override.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-swift-protocol-extensions-default-implementations
Swift implements mixin-like behavior via protocol extensions with default method implementations.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-vs-traits-linear-composition
Traits are closely related to mixins but do not require linear composition, while mixins typically do.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-aop-with-interfaces-can-produce-full-mixins
Aspect-oriented programming combined with interfaces can produce full-fledged mixins in languages like C# and Java.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mixin-simulated-by-extension-methods-in-csharp-dart
C# and Dart simulate mixin behavior on interfaces using extension methods without modifying the original classes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Mixin.md
- Source URL: https://en.wikipedia.org/wiki/Mixin
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mvc-model-maps-to-database-table-via-orm
In web frameworks, the MVC Model typically maps to a database table via an ORM.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mvc-web-views-are-html-templates
In web MVC frameworks, views are typically HTML templates rather than composable widget objects.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mvc-web-controller-handles-http-requests
In web MVC frameworks, the Controller receives HTTP requests, interacts with models, and selects views for the response.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] rails-view-one-to-one-with-controller-action
In Rails, each view typically has a one-to-one relationship with a controller action.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] fowler-2003-mvc-input-controller
Martin Fowler's Patterns of Enterprise Application Architecture (2003) defined MVC with an 'input controller' that receives requests, messages models, and passes responses to views.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] web-mvc-evolved-from-thin-client-to-ajax
Early web MVC used a thin-client approach with all logic server-side; later frameworks added Ajax for client-side MVC execution.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-ModelE28093viewE28093controller.md
- Source URL: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ooad-conceptual-model-implementation-independent
The OOAD conceptual model is explicitly implementation-independent, containing no concurrency or storage details.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ood-activities-include-class-diagrams-design-patterns-orm
OOD activities include defining objects/attributes, creating class diagrams from conceptual models, applying design patterns, identifying persistent objects, designing an ORM strategy, and identifying remote objects.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] uml-class-diagram-static-structure
A UML class diagram shows static structure with classes, attributes, and relationships, and can be auto-generated from sequence diagram analysis.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] uml-sequence-diagram-object-interactions-over-time
A UML sequence diagram shows object interactions over time as horizontal arrows between parallel vertical lifelines.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unified-process-rup-common-ooad-framework
The Unified Process / RUP is the iterative framework most commonly used to execute OOAD.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] grasp-guides-responsibility-assignment
GRASP (General Responsibility Assignment Software Patterns) is a set of OO design principles that guide responsibility assignment during OOD.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_design.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_design
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] oop-definition-contested-multi-paradigm
OOP is not a single fixed definition but a contested set of features, and most modern languages are multi-paradigm.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] objects-are-class-instances-or-prototype-linked
Objects are instances of classes in class-based OOP or linked to prototypes in prototype-based OOP.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] encapsulation-includes-cohesion-decoupling-data-hiding
Encapsulation bundles related data and methods and involves three related ideas: cohesion, decoupling, and data hiding.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] inheritance-class-based-or-prototype-based
Inheritance can be class-based (subclass extends superclass) or prototype-based (object delegates to prototype).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] object-relational-impedance-mismatch-structural-disconnect
Object-relational impedance mismatch is the structural disconnect between OOP objects and relational database tables, addressed by ORM tools but never perfectly solved.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] smalltalk-introduced-message-passing-dynamic-class-modification
Smalltalk, developed in the 1970s at Xerox PARC under Alan Kay, introduced OOP as message-passing between cell-like objects and fully dynamic class modification.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Object-oriented_programming.md
- Source URL: https://en.wikipedia.org/wiki/Object-oriented_programming
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] observer-one-to-many-dependency
The Observer pattern establishes a one-to-many dependency where a single subject notifies multiple observers of state changes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] observer-subject-knows-only-update-interface
In the Observer pattern, the subject only knows that observers implement the update() interface, not their concrete types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] observer-registration-dynamic-runtime
Observers in the Observer pattern register themselves at runtime and can be added or removed dynamically.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] observer-throttling-polling-for-high-frequency-changes
For high-frequency state changes such as progress bars, observers can poll at intervals rather than reacting to every change, a technique called throttling.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediator-encapsulates-interaction-vs-observer-broadcast
The Mediator pattern centralizes communication between objects by encapsulating interaction logic, whereas Observer broadcasts notifications directly to observers.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ecs-often-uses-observer
Entity-Component-System (ECS) architectures often use the Observer pattern internally.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Observer_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Observer_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] polymorphism-single-interface-multiple-types
Polymorphism allows a single interface, operation, or symbol to work across multiple types; in OOP it is the provision of one interface to entities of different data types.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] coercion-polymorphism-is-ad-hoc
Coercion polymorphism, implicit type conversion, is classified as a form of ad hoc polymorphism.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] parametric-polymorphism-uniform-generic-static-type-safety
Parametric polymorphism writes code generically using abstract type variables, handles values uniformly regardless of type, and maintains full static type safety.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] polymorphic-data-type-parameterized-by-type-variable
A polymorphic data type is a data type parameterized by a type variable, such as List<T>.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] row-polymorphism-operates-on-structural-types
Row polymorphism operates on structural types and allows values whose types have certain properties without losing remaining type information, distinct from subtyping.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] polytypism-more-general-than-polymorphism
Polytypism (data type genericity) is more general than polymorphism because functions are defined over the structure of data types themselves.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Polymorphism_computer_science.md
- Source URL: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] prototype-solves-runtime-type-and-dynamic-loading
The Prototype pattern solves two problems: determining the concrete type at runtime, and instantiating dynamically loaded classes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] clone-over-new-preserves-state
clone() is preferred over new when you need a duplicate that preserves the original object's state (e.g., bank account transaction processing), rather than a default-initialized instance.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] prototype-distinct-from-prototype-based-programming
The Prototype pattern is not the same as prototype-based programming (a language paradigm, e.g., JavaScript) or function prototypes (forward declarations).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] prototype-benefits-composite-decorator-copying
Designs heavy in Composite or Decorator often benefit from Prototype for copying complex object structures.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] prototype-factory-clones-prototypes-on-request
In the Prototype pattern, a client constructs a factory with prototype instances, then calls factory methods which internally delegate to clone().
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Prototype_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Prototype_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] proxy-three-participants-subject-realsubject-proxy
The Proxy pattern structure has three participants: Subject (interface), RealSubject (the actual object), and Proxy (holds a reference to RealSubject and forwards requests to it).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] remote-proxy-translates-calls-to-remote-invocations
In a remote proxy, method calls on the proxy translate to remote method invocations.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] decorator-stacks-wrappers-proxy-stands-alone
Decorator typically stacks multiple wrappers; Proxy usually stands alone as a single wrapper.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-simplifies-subsystem-proxy-wraps-single-object
Facade simplifies a complex subsystem behind a new interface; Proxy wraps a single object with the same interface.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] virtual-proxy-caches-real-object-after-first-load
In a virtual proxy, the first call to the proxy's method triggers the expensive load; subsequent calls reuse the cached real object.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Proxy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Proxy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-semantic-coupling-brittleness
Pub/sub can introduce semantic/format coupling between publishers and subscribers, leading to brittleness over time.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-broker-based-centralized-topology
In broker-based (centralized) pub/sub, a message broker/event bus receives messages from publishers and routes them to subscribers, potentially performing store-and-forward, priority queuing, or routing logic.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-brokerless-decentralized-topology
In brokerless (decentralized) pub/sub, publishers and subscribers discover each other directly (e.g., DDS using IP multicast) and require overlay networks, often Small-World topologies.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-subscription-timing-three-options
Pub/sub subscriptions can be established at build time (hardcoded handlers), initialization time (XML config), or runtime (dynamic add/remove).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-evolved-from-observer-pattern
Pub/sub evolved from the Observer pattern to support distributed, asynchronous use cases.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-component-within-mom
Pub/sub is typically a component within message-oriented middleware (MOM) systems.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pubsub-broker-acts-as-mediator
The broker in pub/sub acts as a mediator between publishers and subscribers.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-PublishE28093subscribe_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] soc-definition-concern-independent-aspect
In SoC, a concern is any aspect or issue of a system that can be considered independently, such as correctness, efficiency, security, presentation, or data flow.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] soc-reduces-complexity-via-independent-analysis
Separation of concerns reduces complexity by allowing independent analysis, design, and modification of each concern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] soc-good-soc-leads-low-coupling-high-cohesion
Good separation of concerns leads to low coupling between modules and high cohesion within them.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] srp-is-soc-at-class-module-level
The Single Responsibility Principle (SRP) is an application of SoC at the class/module level.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] html-css-js-canonical-web-soc-example
The separation of HTML (content), CSS (presentation), and JavaScript (behavior) is a canonical web example of SoC.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] osi-protocol-stack-canonical-soc-example
The OSI/Internet protocol stack (application, transport, internet, link) is a canonical example of SoC where each layer addresses a distinct concern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] marr-levels-of-analysis-apply-soc
David Marr's levels of analysis (computational, algorithmic, implementation) apply SoC in cognitive science/AI.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ghezzi-soc-primary-complexity-technique
Carlo Ghezzi promotes SoC as the primary way to tackle inherent complexity in software production.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Separation_of_concerns.md
- Source URL: https://en.wikipedia.org/wiki/Separation_of_concerns
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] singleton-name-from-mathematical-singleton
The Singleton pattern's name derives from the mathematical concept of a singleton (a set with exactly one element).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] singleton-preferred-over-global-variables
Singleton is preferred over global variables because it does not pollute the global namespace and supports lazy allocation/initialization.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] facade-frequently-singleton
Facade objects are frequently implemented as Singletons since only one facade is typically needed.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] multiton-generalizes-singleton-named-instances
The Multiton pattern generalizes Singleton by managing a map of named instances rather than a single one.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] singleton-lazy-vs-eager-initialization
Singleton lazy initialization defers instance creation until first use, while eager initialization creates the instance at class load time.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cpp-singleton-deletes-copy-constructor-assignment
In C++, the Singleton pattern requires deleting the copy constructor and assignment operator to prevent copying.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] initialization-on-demand-holder-idiom-java-alternative
The initialization-on-demand holder idiom is a Java-specific thread-safe alternative to double-checked locking for Singleton.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Singleton_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Singleton_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gof-pattern-documentation-format-thirteen-sections
The GoF documentation format for a pattern includes Name, Intent, Also Known As, Motivation, Applicability, Structure, Participants, Collaboration, Consequences, Implementation, Sample Code, Known Uses, and Related Patterns.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] portland-pattern-repository-ward-cunningham-documentation-hub
The Portland Pattern Repository (Ward Cunningham) served as a central documentation hub for patterns.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pattern-indirection-can-decrease-runtime-performance
Design patterns introduce indirection that can decrease runtime performance.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] meyer-arnout-componentized-two-thirds-of-patterns-attempted
Meyer and Arnout achieved full or partial componentization of two-thirds of the design patterns they attempted.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] concurrency-patterns-include-active-object-double-checked-locking-monitor-object-reactor-read-write-lock-thread-pool-thread-specific-storage
Concurrency patterns include Active Object, Double-Checked Locking, Monitor Object, Reactor, Read-Write Lock, Thread Pool, and Thread-Specific Storage.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Software_design_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Software_design_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] state-pattern-state-interface-declares-handle-method
In the State pattern, the State interface declares a handle() method for state-specific behavior.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] state-pattern-documented-gof-1995-page-305
The State pattern is documented in Design Patterns: Elements of Reusable Object-Oriented Software (GoF, 1995), page 305ff.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] state-pattern-solves-behavior-change-and-new-state-extensibility
The State pattern solves two problems: objects need behavior that changes with internal state, and new states must be addable without modifying existing state classes.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] state-pattern-eliminates-rigid-conditionals-with-polymorphism
The State pattern eliminates rigid conditionals by replacing if/switch logic with polymorphism.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-State_pattern.md
- Source URL: https://en.wikipedia.org/wiki/State_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] strategy-pattern-also-known-as-policy-pattern
The Strategy pattern is also known as the Policy pattern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] strategy-pattern-implemented-via-function-pointer-first-class-function-class-instance-reflection
A Context can store a Strategy reference via a function pointer, first-class function, class instance, or reflection.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] strategy-pattern-eliminates-conditional-logic-with-polymorphic-dispatch
The Strategy pattern eliminates conditional logic such as if/else or switch on type by replacing it with polymorphic dispatch.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] policy-based-design-is-cpp-template-equivalent-of-strategy
Policy-Based Design is the C++ template-based equivalent of the Strategy pattern, selecting algorithms at compile time rather than runtime.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] higher-order-functions-achieve-strategy-effect-without-class-ceremony
In functional programming, passing a function as an argument achieves the same effect as the Strategy pattern without the class ceremony.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Strategy_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Strategy_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] aggregate-is-specialization-of-composite-adding-aggregation-methods
Aggregate is a specialization of Composite that adds aggregation methods over children.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adapter-pipeline-chains-multiple-adapters
Adapter Pipeline chains multiple adapters and is useful for debugging.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] retrofit-interface-pattern-adapts-new-interface-for-multiple-classes
The Retrofit Interface Pattern is an Adapter variant that adapts a new interface for multiple classes simultaneously.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] tombstone-is-intermediate-lookup-technique-related-to-bridge
Tombstone is an intermediate-lookup technique related to the Bridge pattern.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] marker-interface-is-empty-interface-used-for-metadata-tagging
A Marker Interface is an empty interface used for metadata tagging.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pipes-and-filters-pattern-linear-chain-output-feeds-next-stage
Pipes and Filters is a linear chain where each stage's output feeds the next stage.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] opaque-pointer-hides-implementation-behind-private-type
Opaque Pointer hides implementation behind an undeclared or private type.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Structural_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Structural_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] template-method-defines-algorithm-skeleton-in-superclass-method
The Template Method pattern defines the skeleton of an algorithm in a superclass method, deferring specific steps to subclasses.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] template-method-runtime-uses-self-message-dispatch
At runtime, the Template Method executes via self-message dispatch: the base class sends a message to self, and polymorphism routes it to a subclass's overridden implementation if one exists.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] generation-gap-pattern-splits-generated-abstract-superclass-and-handwritten-subclass
In the Generation Gap pattern, generated code forms the abstract superclass and hand-written customizations go in subclasses, preventing regeneration from overwriting custom code.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] template-method-documented-gof-1994-pages-325-330
Template Method is defined by the Gang of Four in Design Patterns (1994), pages 325–330.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] template-method-distinct-from-template-processor
The Template Method pattern is distinct from the Template processor, an unrelated text-substitution concept.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Template_method_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Template_method_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-pattern-composite-traversal-delegates-accept-to-children
In the Visitor pattern, when an element contains children, its accept method iterates over children calling child.accept(visitor) before or after calling visitor.visit(this).
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-pattern-go-requires-distinct-visit-method-names
In Go, because the language lacks method overloading, Visitor pattern visit methods must have distinct names such as visitWheel and visitEngine instead of being overloaded by element type.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-pattern-enables-public-api-extensibility
The Visitor pattern enables public API extensibility by allowing clients to add operations via visitors without modifying library source code.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-pattern-iterator-substitution-limitations
The Visitor pattern can substitute for iteration over containers but does not provide easy break-out from traversal or concurrent traversal.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-vs-strategy-externalization-difference
Strategy pattern replaces an algorithm within a single class, whereas Visitor pattern adds operations across an entire class hierarchy.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visitor-pattern-supports-srp
In the Visitor pattern, each visitor encapsulates a single cross-cutting operation, supporting the Single Responsibility Principle.
- Source: /home/forge/workspace/entries/2026/06/19/wiki-Visitor_pattern.md
- Source URL: https://en.wikipedia.org/wiki/Visitor_pattern
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

