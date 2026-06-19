---
source: https://en.wikipedia.org/wiki/Structural_pattern
fetched: 2026-06-19
---

A **structural pattern** is a [software design pattern](./Software_design_pattern) that encapsulates relationships between entities.

 

## Examples

 

Examples include:

 [Adapter pattern](./Adapter_pattern)Adapts one interface for a class into one that a client expects.
Adapter pipelineUse multiple adapters for debugging purposes.[[1]](./Structural_pattern#cite_note-1) Retrofit Interface PatternAn adapter used as a new interface for multiple classes at the same time.[[2]](./Structural_pattern#cite_note-2)[[3]](./Structural_pattern#cite_note-3) [Aggregate pattern](./Aggregate_pattern)A version of the [Composite pattern](./Composite_pattern) with methods for aggregation of children. [Bridge pattern](./Bridge_pattern)decouple an abstraction from its implementation so that the two can vary independently.
TombstoneAn intermediate lookup object contains the real location of an object.[[4]](./Structural_pattern#cite_note-4) [Composite pattern](./Composite_pattern)A tree structure of objects where every object has the same interface. [Decorator pattern](./Decorator_pattern)Supports adding additional functionality to an object at runtime. Prevents issue where subclassing would result in an exponential rise of new classes. [Extensibility pattern](./Extensibility_pattern)a.k.a. framework, Hides complex code behind a simple interface. [Facade pattern](./Facade_pattern)Creates a simplified interface of an existing interface to ease usage for common tasks. [Flyweight pattern](./Flyweight_pattern)A large quantity of objects share a common properties object to save space. [Marker interface pattern](./Marker_interface_pattern)An empty interface to associate metadata with a class. [Pipes and filters](./Pipes_and_filters)A chain of processes where the output of each process is the input of the next. [Opaque pointer](./Opaque_pointer)A pointer to an undeclared or private type, to hide implementation details. [Proxy pattern](./Proxy_pattern)A class functioning as an interface to another thing. 

## See also

 
- [Behavioral pattern](./Behavioral_pattern)
- [Concurrency pattern](./Concurrency_pattern)
- [Creational pattern](./Creational_pattern)

 

## References

   [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Structural software design patterns](https://commons.wikimedia.org/wiki/Category:Structural%20software%20design%20patterns).   
1. [↑](./Structural_pattern#cite_ref-1) ["Adapter Pipeline"](http://c2.com/cgi/wiki?AdapterPipeline). Cunningham & Cunningham, Inc. 2010-12-31. Archived from [the original](http://c2.com/) on 2010-12-31. Retrieved 2012-07-20.
2. [↑](./Structural_pattern#cite_ref-2) BobbyWoolf (2002-06-19). ["Retrofit Interface Pattern"](http://c2.com/cgi/wiki?RetrofitInterfacePattern). Cunningham & Cunningham, Inc. Archived from [the original](http://c2.com/) on 2002-06-19. Retrieved 2012-07-20.
3. [↑](./Structural_pattern#cite_ref-3) MartinZarate (2010-12-31). ["External Polymorphism"](http://c2.com/cgi/wiki?ExternalPolymorphism). Cunningham & Cunningham, Inc. Archived from [the original](http://c2.com/) on 2010-12-31. Retrieved 2012-07-20.
4. [↑](./Structural_pattern#cite_ref-4) ["Tomb Stone"](http://c2.com/cgi/wiki?AdapterPipeline). Cunningham & Cunningham, Inc. 2007-06-17. Archived from [the original](http://c2.com/) on 2007-06-17. Retrieved 2012-07-20.

 
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