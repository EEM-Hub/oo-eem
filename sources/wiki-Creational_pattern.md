---
source: https://en.wikipedia.org/wiki/Creational_pattern
fetched: 2026-06-19
---

Software design pattern for object creation 

A **creational pattern** is a [software design pattern](./Software_design_pattern) for creating [objects](./Object_(computer_science)) in a manner suitable to a particular situation. As object creation that is otherwise available (i.e. via the [programming language](./Programming_language)) can sometimes result in [ design](./Software_design) limitations, a custom mechanism for creation can provide for better design. A creational pattern aims to separate a system from how its objects are created, composed, and represented. They increase the system's flexibility in terms of the what, who, how, and when of object creation.[[1]](./Creational_pattern#cite_note-CS3DP-1)

 

A creational pattern encapsulates two main aspects. One is encapsulating knowledge about which concrete [classes](./Class_(programming)) the system uses. Another is hiding how [instances](./Instance_(computer_science)) of these concrete classes are created and combined.[[2]](./Creational_pattern#cite_note-2)

 

Creational design patterns are categorized into object-creational patterns and class-creational patterns. Object-creational patterns defer part of its object creation to another object, while class-creational patterns defer its object creation to subclasses.[[3]](./Creational_pattern#cite_note-3)

 

## Usage

 

As modern software engineering depends more on [object composition](./Object_composition) than class inheritance, emphasis shifts away from hard-coding behaviors toward defining a smaller set of basic behaviors that can be composed into more complex ones.[[4]](./Creational_pattern#cite_note-4) Hard-coding behaviors are inflexible because they require overriding or re-implementing the whole thing in order to change parts of the design. Additionally, hard-coding does not promote reuse and makes it difficult to keep track of errors. For these reasons, creational patterns are more useful than hard-coding behaviors. Creational patterns make design become more flexible. They provide different ways to remove explicit references in the concrete classes from the code that needs to instantiate them.[[5]](./Creational_pattern#cite_note-5) In other words, they create independency for objects and classes.

 

Consider applying creational patterns when: 

 
- A system should be independent of how its objects and products are created.
- A set of related objects is designed to be used together.
- Hiding the implementations of a class library or product, revealing only their interfaces.
- Constructing different representation of independent complex objects.
- A class wants its subclass to implement the object it creates.
- The class instantiations are specified at run-time.
- There must be a single instance and client can access this instance at all times.
- Instance should be extensible without being modified.

 

## Structure

 [![](//upload.wikimedia.org/wikipedia/commons/f/f6/Creational_Pattern_Simple_Structure.png)](./File:Creational_Pattern_Simple_Structure.png)Creational Pattern class diagram. 

Below is a simple class diagram that most creational patterns have in common. Note that different creational patterns require additional and different participated classes.

 

**Participants**: 

 
- **Creator**: Declares object interface. Returns object.
- **ConcreteCreator**: Implements object's interface.

 

## Examples

 

Some examples of creational design patterns include:

 [Abstract factory pattern](./Abstract_factory_pattern)a class requests the objects it requires from a factory object instead of creating the objects directly.[[6]](./Creational_pattern#cite_note-6) [Factory method pattern](./Factory_method_pattern)centralize creation of an object of a specific type choosing one of several implementations.[[7]](./Creational_pattern#cite_note-7) [Builder pattern](./Builder_pattern)separate the construction of a complex object from its representation so that the same construction process can create different representations. [ Dependency injection pattern](./Dependency_injection)a class accepts the objects it requires from an injector instead of creating the objects directly [Lazy initialization pattern](./Lazy_initialization_pattern)tactic of delaying the creation of an object, the calculation of a value, or some other expensive process until the first time it is needed. [Object pool pattern](./Object_pool_pattern)avoid expensive acquisition and release of resources by recycling objects that are no longer in use. [Prototype pattern](./Prototype_pattern)used when the type of objects to create is determined by a prototypical instance, which is cloned to produce new objects. [Singleton pattern](./Singleton_pattern)restrict instantiation of a class to one object.[[8]](./Creational_pattern#cite_note-8) 

## See also

 
- [Constructor](./Constructor_(object-oriented_programming))
- [Behavioral pattern](./Behavioral_pattern)
- [Concurrency pattern](./Concurrency_pattern)
- [Structural pattern](./Structural_pattern)

 

## References

  
1. [↑](./Creational_pattern#cite_ref-CS3DP_1-0) Judith, Bishop (2007). [*C# 3.0 Design Patterns*](https://archive.org/details/c30designpattern0000bish/page/336). California: O'Reilly Media. p. [336](https://archive.org/details/c30designpattern0000bish/page/336). [ISBN](./ISBN_(identifier)) [978-0-596-52773-0](./Special:BookSources/978-0-596-52773-0). Retrieved 2015-05-22.
2. [↑](./Creational_pattern#cite_ref-2) Gamma, Erich; Helm, Richard; Johnson, Ralph; Vlissides, John (1995). [*Design Patterns*](https://archive.org/details/designpatternsel00gamm/page/81). Massachusetts: Addison-Wesley. p. [81](https://archive.org/details/designpatternsel00gamm/page/81). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0). Retrieved 2015-05-22.
3. [↑](./Creational_pattern#cite_ref-3) Gamma, Erich; Helm, Richard; Johnson, Ralph; Vlissides, John (1995). [*Design Patterns*](https://archive.org/details/designpatternsel00gamm). Massachusetts: Addison-Wesley. [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0). Retrieved 2015-05-22.
4. [↑](./Creational_pattern#cite_ref-4) Gamma, Erich; Helm, Richard; Johnson, Ralph; Vlissides, John (1995). [*Design Patterns*](https://archive.org/details/designpatternsel00gamm/page/84). Massachusetts: Addison-Wesley. p. [84](https://archive.org/details/designpatternsel00gamm/page/84). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0). Retrieved 2015-05-22.
5. [↑](./Creational_pattern#cite_ref-5) Gamma, Erich; Helm, Richard; Johnson, Ralph; Vlissides, John (1995). [*Design Patterns*](https://archive.org/details/designpatternsel00gamm/page/85). Massachusetts: Addison-Wesley. p. [85](https://archive.org/details/designpatternsel00gamm/page/85). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0). Retrieved 2015-05-22.
6. [↑](./Creational_pattern#cite_ref-6)  Freeman, Eric; Freeman, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). [*Head First Design Patterns*](http://shop.oreilly.com/product/9780596007126.do). California: O'Reilly Media. p. 156. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6). Retrieved 2015-05-22.
7. [↑](./Creational_pattern#cite_ref-7)  Freeman, Eric; Freeman, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). [*Head First Design Patterns*](http://shop.oreilly.com/product/9780596007126.do). California: O'Reilly Media. p. 134. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6). Retrieved 2015-05-22.
8. [↑](./Creational_pattern#cite_ref-8)  Freeman, Eric; Freeman, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). [*Head First Design Patterns*](http://shop.oreilly.com/product/9780596007126.do). California: O'Reilly Media. p. 177. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6). Retrieved 2015-05-22.

 
| vteSoftware design patterns |
| --- |
| Gang of Fourpatterns | CreationalAbstract factoryBuilderFactory methodPrototypeSingletonStructuralAdapterBridgeCompositeDecoratorFacadeFlyweightProxyBehavioralChain of responsibilityCommandInterpreterIteratorMediatorMementoObserverStateStrategyTemplate methodVisitor | Creational | Abstract factoryBuilderFactory methodPrototypeSingleton | Structural | AdapterBridgeCompositeDecoratorFacadeFlyweightProxy | Behavioral | Chain of responsibilityCommandInterpreterIteratorMediatorMementoObserverStateStrategyTemplate methodVisitor |
| Creational | Abstract factoryBuilderFactory methodPrototypeSingleton |
| Structural | AdapterBridgeCompositeDecoratorFacadeFlyweightProxy |
| Behavioral | Chain of responsibilityCommandInterpreterIteratorMediatorMementoObserverStateStrategyTemplate methodVisitor |
| Concurrencypatterns | Active objectBalkingBinding propertiesDouble-checked lockingEvent-based asynchronousGuarded suspensionJoinLockMonitorProactorReactorRead–write lockSchedulerScheduled-task patternSemaphoreThread poolThread-local storage |
| Architecturalpatterns | Front controllerInterceptorMVCMVPMVVMADRECSn-tierSpecificationPublish–subscribeNaked objectsService locatorActive recordIdentity mapData access object (DAO)Data transfer object (DTO)Inversion of controlModel 2Broker |
| Otherpatterns | BlackboardBusiness delegateComposite entityComposition over inheritanceDependency injectionGuard clauseIntercepting filterLazy loadingMock objectNull objectObject poolServantTwinType tunnelMethod chainingDelegation |
| Books | Design PatternsEnterprise Integration Patterns |
| People | Christopher AlexanderErich GammaRalph JohnsonJohn VlissidesGrady BoochKent BeckWard CunninghamMartin FowlerRobert MartinJim CoplienDouglas SchmidtLinda Rising |
| Communities | The Hillside GroupPortland Pattern Repository |
| See also | Anti-patternArchitectural pattern |