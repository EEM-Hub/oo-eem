---
source: https://en.wikipedia.org/wiki/Facade_pattern
fetched: 2026-06-19
---

Software design pattern 

The **facade pattern** (also spelled *façade*) is a [software design pattern](./Software_design_pattern) commonly used in [object-oriented programming](./Object-oriented_programming). Analogous to a [façade](./Façade) in architecture, it is an [object](./Object_(computer_science)) that serves as a front-facing interface masking more complex underlying or structural code. A facade can:

 
- improve the readability and usability of a [software library](./Software_library) by masking interaction with more complex components behind a single (and often simplified) [application programming interface](./Application_programming_interface) (API)
- provide a context-specific interface to more generic functionality (complete with context-specific input [validation](./Data_validation))
- serve as a launching point for a broader [refactor](./Code_refactoring) of [monolithic](./Monolithic_system) or tightly-coupled systems in favor of more [loosely-coupled](./Loose_coupling) code

 

Developers often use the facade design pattern when a system is very complex or difficult to understand because the system has many interdependent classes or because its source code is unavailable. This pattern hides the complexities of the larger system and provides a simpler interface to the client. It typically involves a single [wrapper class](./Wrapper_class) that contains a set of members required by the client. These members access the system on behalf of the facade client and hide the implementation details.

 

## Overview

 

The Facade
[[1]](./Facade_pattern#cite_note-GoF-1)
design pattern is one of the twenty-three well-known 
*[GoF design patterns](./Design_Patterns)* 
that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

What problems can the Facade design pattern solve?
[[2]](./Facade_pattern#cite_note-2)

 
- To make a complex subsystem easier to use, a simple interface should be provided for a set of interfaces in the subsystem.
- The dependencies on a subsystem should be minimized.

 

Clients that access a complex subsystem directly refer to (depend on) many different objects having different interfaces (tight coupling), which makes the clients hard to implement, change, test, and reuse.

 

What solution does the Facade design pattern describe?

 

Define a `Facade` object that 

 
- implements a simple interface in terms of (by delegating to) the interfaces in the subsystem and
- may perform additional functionality before/after forwarding a request.

 

This enables to work through a `Facade` object to minimize the dependencies on a subsystem.

See also the UML class and sequence diagram below.

 

## Usage

 

A Facade is used when an easier or simpler interface to an underlying object is desired.[[3]](./Facade_pattern#cite_note-3) Alternatively, an [adapter](./Adapter_pattern) can be used when the wrapper must respect a particular interface and must support [polymorphic](./Polymorphism_(computer_science)) behavior. A [decorator](./Decorator_pattern) makes it possible to add or alter behavior of an interface at run-time.

 
| Pattern | Intent |
| --- | --- |
| Adapter | Converts one interface to another so that it matches what the client is expecting |
| Decorator | Dynamically adds responsibility to the interface by wrapping the original code |
| Facade | Provides a simplified interface |

 

The facade pattern is typically used when

 
- a simple interface is required to access a complex system,
- a system is very complex or difficult to understand,
- an entry point is needed to each level of layered software, or
- the abstractions and implementations of a subsystem are tightly coupled.

 

A good example of where a facade is used is in register indexed values like [Modbus](./Modbus), [I2C](./I2C) or [Special function register](./Special_function_register).

 

## Structure

 

### UML class and sequence diagram

 [![Facade Design Pattern Class Diagram](//upload.wikimedia.org/wikipedia/commons/thumb/1/13/Facade_Design_Pattern_Class_Diagram_UML.svg/330px-Facade_Design_Pattern_Class_Diagram_UML.svg.png)](./File:Facade_Design_Pattern_Class_Diagram_UML.svg)[![Facade Design Pattern Sequence Diagram](//upload.wikimedia.org/wikipedia/commons/thumb/3/3d/Facade_Design_Pattern_Sequence_Diagram_UML.svg/500px-Facade_Design_Pattern_Sequence_Diagram_UML.svg.png)](./File:Facade_Design_Pattern_Sequence_Diagram_UML.svg)A sample UML class and sequence diagram for the facade design pattern 

In this [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), 
the `Client` class doesn't access the subsystem classes directly.
Instead, the `Client` works through a `Facade` class that implements a simple interface in terms of (by delegating to) the subsystem classes (`Class1`, `Class2`, and `Class3`).
The `Client` depends only on the simple `Facade` interface
and is independent of the complex subsystem.[[4]](./Facade_pattern#cite_note-4)

 

The sequence diagram 
shows the run-time interactions: The `Client` object 
works through a `Facade` object that delegates the request to
the  `Class1`, `Class2`, and `Class3`
instances that perform the request.

 

### UML class diagram

 

[![](//upload.wikimedia.org/wikipedia/commons/5/57/Example_of_Facade_design_pattern_in_UML.png)](./File:Example_of_Facade_design_pattern_in_UML.png)

 Facade The facade class abstracts Packages 1, 2, and 3 from the rest of the application. Clients The objects are using the facade pattern to access resources from the packages. 

## See also

 
- [Encapsulation (computer programming)](./Encapsulation_(computer_programming))

 

## References

  
1. [↑](./Facade_pattern#cite_ref-GoF_1-0) Gamma, Erich; Helm, Richard; Johnson, Ralph; Vlissides, John (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/185). Addison Wesley. pp. [185ff](https://archive.org/details/designpatternsel00gamm/page/185). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Facade_pattern#cite_ref-2) ["The Facade design pattern - Problem, Solution, and Applicability"](https://web.archive.org/web/20200612203152/http://w3sdesign.com/?gr=s05&ugr=proble). *w3sDesign.com*. Archived from [the original](http://w3sdesign.com/?gr=s05&ugr=proble) on 2020-06-12. Retrieved 2017-08-12.
3. [↑](./Facade_pattern#cite_ref-3) Freeman, Eric; Freeman, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). *Head First Design Patterns*. Vol. 1. O'Reilly. pp. 243, 252, 258, 260. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6).
4. [↑](./Facade_pattern#cite_ref-4) ["The Facade design pattern - Structure and Collaboration"](https://web.archive.org/web/20200612203156/http://w3sdesign.com/?gr=s05&ugr=struct). *w3sDesign.com*. Archived from [the original](http://w3sdesign.com/?gr=s05&ugr=struct) on 2020-06-12. Retrieved 2017-08-12.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Facade implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Facade)***    [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Facade pattern](https://commons.wikimedia.org/wiki/Category:Facade%20pattern).  
- [Description from the Portland Pattern Repository](http://c2.com/cgi/wiki?FacadePattern)

 

 

 
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

 Categories