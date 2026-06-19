---
source: https://en.wikipedia.org/wiki/Behavioral_pattern
fetched: 2026-06-19
---

Type of software design pattern 

A **behavioral pattern** is a [software design pattern](./Software_design_pattern) for collaboration between [objects](./Object_(computer_science)).

 

## Examples

 

Examples include:

 [Blackboard design pattern](./Blackboard_design_pattern)Provides a computational framework for the design and implementation of systems that integrate large and diverse specialized modules, and implement complex, non-deterministic control strategies. [Chain-of-responsibility pattern](./Chain-of-responsibility_pattern)Command objects are handled or passed on to other objects by logic-containing processing objects. [Command pattern](./Command_pattern)Command objects encapsulate an action and its parameters. Externalize the stackTurn a [recursive function](./Recursion_(computer_science)) into an [iterative function](./Iterative_function) that uses a [stack](./Call_stack)[[1]](./Behavioral_pattern#cite_note-1) [Interpreter pattern](./Interpreter_pattern)Implement a specialized computer language to rapidly solve a specific set of problems. [Iterator pattern](./Iterator_pattern)[Iterators](./Iterator) are used to access the elements of an aggregate object sequentially without exposing its underlying representation. [Mediator pattern](./Mediator_pattern)Provides a unified interface to a set of interfaces in a subsystem. [Memento pattern](./Memento_pattern)Provides the ability to restore an object to its previous state (rollback). [Null object pattern](./Null_object_pattern)Acts as a default value of an object. [Observer pattern](./Observer_pattern)Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically. The variant **weak reference pattern** decouples an observer from an observable to avoid memory leaks in environments without automatic weak references.[[2]](./Behavioral_pattern#cite_note-2) [Protocol stack](./Protocol_stack)Communications are handled by multiple layers, which form an encapsulation hierarchy[[3]](./Behavioral_pattern#cite_note-3) [Publish–subscribe pattern](./Publish–subscribe_pattern)A messaging pattern where senders (publishers) and receivers (subscribers) are decoupled via message topics and brokers. Commonly used in distributed systems, this pattern supports asynchronous, many-to-many communication. [Scheduled-task pattern](./Scheduled-task_pattern)A task is scheduled to be performed at a particular interval or clock time (used in [real-time computing](./Real-time_computing)). [Single-serving visitor pattern](./Single-serving_visitor_pattern)Optimise the implementation of a visitor that is allocated, used only once, and then deleted. [Specification pattern](./Specification_pattern)Recombinable [business logic](./Business_logic) in a [boolean](./Boolean_algebra) fashion. [State pattern](./State_pattern)A clean way for an object to partially change its type at runtime. [Strategy pattern](./Strategy_pattern)Algorithms can be selected on the fly, using composition. [Template method pattern](./Template_method_pattern)Describes the [skeleton](./Program_skeleton) of a program; algorithms can be selected on the fly, using [inheritance](./Inheritance_(object-oriented_programming)). [Visitor pattern](./Visitor_pattern)A way to separate an algorithm from an object. 

## See also

 
- [Concurrency pattern](./Concurrency_pattern)
- [Creational pattern](./Creational_pattern)
- [Structural pattern](./Structural_pattern)

 

## References

  
1. [↑](./Behavioral_pattern#cite_ref-1) ["Externalize The Stack"](https://web.archive.org/web/20110303085751/http://c2.com/). c2.com. 2010-01-19. Archived from the original on 2011-03-03. Retrieved 2012-05-21.`{{cite web}}`:  CS1 maint: bot: original URL status unknown ([link](./Category:CS1_maint:_bot:_original_URL_status_unknown))
2. [↑](./Behavioral_pattern#cite_ref-2) Nakashian, Ashod (2004-04-11). ["Weak Reference Pattern"](https://web.archive.org/web/20110303085751/http://c2.com/). c2.com. Archived from the original on 2011-03-03. Retrieved 2012-05-21.`{{cite web}}`:  CS1 maint: bot: original URL status unknown ([link](./Category:CS1_maint:_bot:_original_URL_status_unknown))
3. [↑](./Behavioral_pattern#cite_ref-3) ["Protocol Stack"](https://web.archive.org/web/20110303085751/http://c2.com/). c2.com. 2006-09-05. Archived from the original on 2011-03-03. Retrieved 2012-05-21.`{{cite web}}`:  CS1 maint: bot: original URL status unknown ([link](./Category:CS1_maint:_bot:_original_URL_status_unknown))

 
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