---
source: https://en.wikipedia.org/wiki/Design_Patterns
fetched: 2026-06-19
---

1994 software engineering book This article is about the book. For the generic articles, see [Software design pattern](./Software_design_pattern) and [Design pattern](./Design_pattern). 
|  | This articlemay be in need of reorganization to comply with Wikipedia'slayout guidelines.Please help byediting the articleto make improvements to the overall structure.(July 2013)(Learn how and when to remove this message) |
| --- | --- |

 

 

 
|  |
| --- |
| Author | Erich GammaRichard HelmRalph JohnsonJohn Vlissides |
| Subject | Design patterns,software engineering,object-oriented programming |
| Publisher | Addison-Wesley |
| Publicationdate | 1994 |
| Publicationplace | United States |
| Pages | 395 |
| ISBN | 0-201-63361-2 |
| OCLC | 31171684 |
| DeweyDecimal | 005.1/2 20 |
| LCClass | QA76.64 .D47 1995 |

 

***Design Patterns: Elements of Reusable Object-Oriented Software*** (1994) is a [software engineering](./Software_engineering) book describing [software design patterns](./Software_design_pattern). The book was written by [Erich Gamma](./Erich_Gamma), [Richard Helm](./Richard_Helm), [Ralph Johnson](./Ralph_Johnson_(computer_scientist)), and [John Vlissides](./John_Vlissides), with a foreword by [Grady Booch](./Grady_Booch). The book is divided into two parts, with the first two chapters exploring the capabilities and pitfalls of [object-oriented programming](./Object-oriented_programming), and the remaining chapters describing 23 classic [software design patterns](./Software_design_pattern). The book includes examples in [C++](./C++) and [Smalltalk](./Smalltalk).

 

It has been influential to the field of software engineering and is regarded as an important source for object-oriented design theory and practice. More than 500,000 copies have been sold in English and in 13 other languages.[[1]](./Design_Patterns#cite_note-copies-sold-1) Both the authors and the book  are often referred to as the *Gang of Four* (GoF).[[2]](./Design_Patterns#cite_note-gof1-2)[[3]](./Design_Patterns#cite_note-gof2-3)[[4]](./Design_Patterns#cite_note-gof3-4)[[5]](./Design_Patterns#cite_note-gof4-5)

 

## Development and publication history

 

The book started at a birds-of-a-feather session at the 1990 [OOPSLA](./OOPSLA) meeting, "Towards an Architecture Handbook", where Erich Gamma and Richard Helm met and discovered their common interest. They were later joined by Ralph Johnson and John Vlissides.[[6]](./Design_Patterns#cite_note-6) The book was originally published on 21 October 1994, with a 1995 copyright, and was made available to the public at the 1994 OOPSLA meeting.

 

## Introduction

 
|  | This sectioncontains an excessive amount of intricatedetail.Please helpimprove itbyspinning offorrelocatingrelevant information and removing excessive detail that goes againstWikipedia's inclusion policy.(October 2020)(Learn how and when to remove this message) |
| --- | --- |

 

Chapter 1 is a discussion of [object-oriented](./Object-oriented_programming) design techniques, based on the authors' experience, which they believe would lead to good object-oriented software design, including:

 
- "Program to an interface, not an implementation." (Gang of Four 1995:18)
- [Composition over inheritance](./Composition_over_inheritance): "Favor '[object composition](./Object_composition)' over '[class inheritance](./Inheritance_(object-oriented_programming))'." (Gang of Four 1995:20)

 

The authors claim the following as advantages of [interfaces](./Interface_(computer_science)) over implementation:

 
- clients remain unaware of the specific types of objects they use, as long as the object adheres to the interface
- clients remain unaware of the classes that implement these objects; clients only know about the abstract class(es) defining the interface

 

Use of an interface also leads to [dynamic binding](./Dynamic_dispatch) and [polymorphism](./Polymorphism_(computer_science)), which are central features of object-oriented programming.

 

The authors refer to [inheritance](./Inheritance_(object-oriented_programming)) as *[white-box](./White_box_(software_engineering)) reuse*, with white-box referring to visibility, because the internals of parent classes are often visible to [subclasses](./Subclass_(computer_science)). In contrast, the authors refer to [object composition](./Object_composition) (in which objects with well-defined interfaces are used dynamically at runtime by objects obtaining references to other objects) as *[black-box](./Black_box) reuse* because no internal details of composed objects need be visible in the code using them.

 

The authors discuss the tension between inheritance and encapsulation at length and state that in their experience, designers overuse inheritance (Gang of Four 1995:20). The danger is stated as follows:

 "Because inheritance exposes a [subclass](./Subclass_(computer_science)) to details of its parent's implementation, it's often said that 'inheritance breaks encapsulation'". (Gang of Four 1995:19) 

They warn that the implementation of a subclass can become so bound up with the implementation of its parent class that any change in the parent's implementation will force the subclass to change. Furthermore, they claim that a way to avoid this is to inherit only from abstract classes—but then, they point out that there is minimal code reuse.

 

Using inheritance is recommended mainly when adding to the functionality of existing components, reusing most of the old code and adding relatively small amounts of new code.

 

To the authors, 'delegation' is an extreme form of object composition that can always be used to replace inheritance. Delegation involves two objects: a 'sender' passes itself to a 'delegate' to let the delegate refer to the sender. Thus the link between two parts of a system are established only at runtime, not at compile-time. The [Callback](./Callback_(computer_programming)) article has more information about delegation.

 

The authors also discuss so-called parameterized types, which are also known as [generics](./Generic_programming) ([Ada](./Ada_(programming_language)), [Eiffel](./Eiffel_(programming_language)), [Java](./Generics_in_Java), [C#](./C_Sharp_(programming_language)), [Visual Basic (.NET)](./Visual_Basic_(.NET)), and [Delphi](./Delphi_(software))) or templates ([C++](./C++)). These allow any type to be defined without specifying all the other types it uses—the unspecified types are supplied as 'parameters' at the point of use.

 

The authors admit that delegation and parameterization are very powerful but add a warning:

 "Dynamic, highly parameterized software is harder to understand and build than more static software." (Gang of Four 1995:21) 

The authors further distinguish between '[Aggregation](./Object_composition#Aggregation)', where one object 'has' or 'is part of' another object (implying that an aggregate object and its owner have identical lifetimes) and acquaintance, where one object merely 'knows of' another object. Sometimes acquaintance is called 'association' or the 'using' relationship. Acquaintance objects may request operations of each other, but they are not responsible for each other. Acquaintance is a weaker relationship than aggregation and suggests much [looser coupling](./Loose_coupling) between objects, which can often be desirable for maximum maintainability in designs.

 

The authors employ the term 'toolkit' where others might today use 'class library', as in C# or Java. In their parlance, toolkits are the object-oriented equivalent of subroutine libraries, whereas a '[framework](./Software_framework)' is a set of cooperating classes that make up a reusable design for a specific class of software. They state that applications are hard to design, toolkits are harder, and frameworks are the hardest to design.

 

## Patterns by type

 

### Creational

 Main article: [Creational pattern](./Creational_pattern) 

[Creational patterns](./Creational_pattern) are ones that create objects, rather than having to instantiate objects directly. This gives the program more flexibility in deciding which objects need to be created for a given case.

 
- [Abstract factory](./Abstract_factory_pattern) groups object factories that have a common theme.
- [Builder](./Builder_pattern) constructs complex objects by separating construction and representation.
- [Factory method](./Factory_method_pattern) creates objects without specifying the exact class to create.
- [Prototype](./Prototype_pattern) creates objects by cloning an existing object.
- [Singleton](./Singleton_pattern) restricts object creation for a class to only one instance.

 

### Structural

 

[Structural patterns](./Structural_pattern) concern class and object composition. They use inheritance to compose interfaces and define ways to compose objects to obtain new functionality.

 
- [Adapter](./Adapter_pattern) allows classes with incompatible interfaces to work together by wrapping its own interface around that of an already existing class.
- [Bridge](./Bridge_pattern) decouples an abstraction from its implementation so that the two can vary independently.
- [Composite](./Composite_pattern) composes zero-or-more similar objects so that they can be manipulated as one object.
- [Decorator](./Decorator_pattern) dynamically adds/overrides behavior in an existing method of an object.
- [Facade](./Facade_pattern) provides a simplified interface to a large body of code.
- [Flyweight](./Flyweight_pattern) reduces the cost of creating and manipulating a large number of similar objects.
- [Proxy](./Proxy_pattern) provides a placeholder for another object to control access, reduce cost, and reduce complexity.

 

### Behavioral

 

Most [behavioral design patterns](./Behavioral_pattern) are specifically concerned with communication between objects.

 
- [Chain of responsibility](./Chain-of-responsibility_pattern) delegates commands to a chain of processing objects.
- [Command](./Command_pattern) creates objects that encapsulate actions and parameters.
- [Interpreter](./Interpreter_pattern) implements a specialized language.
- [Iterator](./Iterator_pattern) accesses the elements of an object sequentially without exposing its underlying representation.
- [Mediator](./Mediator_pattern) allows [loose coupling](./Loose_coupling) between classes by being the only class that has detailed knowledge of their methods.
- [Memento](./Memento_pattern) provides the ability to restore an object to its previous state (undo).
- [Observer](./Observer_pattern) is a publish/subscribe pattern, which allows a number of observer objects to see an event.
- [State](./State_pattern) allows an object to alter its behavior when its internal state changes.
- [Strategy](./Strategy_pattern) allows one of a family of algorithms to be selected on-the-fly at runtime.
- [Template method](./Template_method_pattern) defines the skeleton of an algorithm as an abstract class, allowing its subclasses to provide concrete behavior.
- [Visitor](./Visitor_pattern) separates an algorithm from an object structure by moving the hierarchy of methods into one object.

 

## Reception

 

In 2005 the ACM [SIGPLAN](./SIGPLAN) awarded that year's Programming Languages Achievement Award to the authors, in recognition of the impact of their work "on programming practice and [programming language](./Programming_language) design".[[7]](./Design_Patterns#cite_note-7)

 

Criticism has been directed at the concept of [software design patterns](./Software_design_pattern) generally, and at *Design Patterns* specifically. A primary criticism of *Design Patterns* is that its patterns are simply workarounds for missing features in C++, replacing elegant abstract features with lengthy concrete patterns, essentially becoming a "human compiler". [Paul Graham](./Paul_Graham_(programmer)) wrote:[[8]](./Design_Patterns#cite_note-Graham2002-8)

 

When I see patterns in my programs, I consider it a sign of trouble. The shape of a program should reflect only the problem it needs to solve. Any other regularity in the code is a sign, to me at least, that I'm using abstractions that aren't powerful enough-- often that I'm generating by hand the expansions of some macro that I need to write.

 

[Peter Norvig](./Peter_Norvig) demonstrates that 16 out of the 23 patterns in *Design Patterns* are simplified or eliminated by language features in [Lisp](./Lisp_(programming_language)) or [Dylan](./Dylan_(programming_language)).[[9]](./Design_Patterns#cite_note-Norvig1998-9) Related observations were made by Hannemann and [Kiczales](./Gregor_Kiczales) who implemented several of the 23 design patterns using an [aspect-oriented programming](./Aspect-oriented_programming) language ([AspectJ](./AspectJ)) and showed that code-level dependencies were removed from the implementations of 17 of the 23 design patterns and that aspect-oriented programming could simplify the implementations of design patterns.[[10]](./Design_Patterns#cite_note-10)

 

In an interview with InformIT in 2009, Erich Gamma stated that the book authors had a discussion in 2005 on how they would have refactored the book and concluded that they would have recategorized some patterns and added a few additional ones, such as extension object/interface, dependency injection, type object, and null object. Gamma wanted to remove the singleton pattern, but there was no consensus among the authors to do so.[[11]](./Design_Patterns#cite_note-11)

 

## See also

 
- [Software design pattern](./Software_design_pattern)
- [Enterprise Integration Patterns](./Enterprise_Integration_Patterns)
- [GRASP (object-oriented design)](./GRASP_(object-oriented_design))
- [Pedagogical patterns](./Pedagogical_pattern)

 

## References

  
1. [↑](./Design_Patterns#cite_ref-copies-sold_1-0) Zehoo, Edmund (26 January 2010). Zehoo, Edmund (ed.). *Pro ODP .NET for Oracle Database 11g*. Apress. pp. 351–371. [doi](./Doi_(identifier)):[10.1007/978-1-4302-2821-9_13](https://doi.org/10.1007%2F978-1-4302-2821-9_13) – via Springer Link.
2. [↑](./Design_Patterns#cite_ref-gof1_2-0) Hussain, Shahid; Keung, Jacky; Khan, Arif Ali (2017). "The Effect of Gang-of-Four Design Patterns Usage on Design Quality Attributes". *2017 IEEE International Conference on Software Quality, Reliability and Security (QRS)*. pp. 263–273. [doi](./Doi_(identifier)):[10.1109/QRS.2017.37](https://doi.org/10.1109%2FQRS.2017.37). [ISBN](./ISBN_(identifier)) [978-1-5386-0592-9](./Special:BookSources/978-1-5386-0592-9). [S2CID](./S2CID_(identifier)) [21343926](https://api.semanticscholar.org/CorpusID:21343926).
3. [↑](./Design_Patterns#cite_ref-gof2_3-0) Hunt, John (26 January 2013). Hunt, John (ed.). *Scala Design Patterns: Patterns for Practical Reuse and Design*. Springer International Publishing. pp. 135–136. [doi](./Doi_(identifier)):[10.1007/978-3-319-02192-8_16](https://doi.org/10.1007%2F978-3-319-02192-8_16) – via Springer Link.
4. [↑](./Design_Patterns#cite_ref-gof3_4-0) Almadi, Sara H. S.; Hooshyar, Danial; Ahmad, Rodina Binti (26 January 2021). ["Bad Smells of Gang of Four Design Patterns: A Decade Systematic Literature Review"](https://doi.org/10.3390%2Fsu131810256). *Sustainability*. **13** (18) 10256. [Bibcode](./Bibcode_(identifier)):[2021Sust...1310256A](https://ui.adsabs.harvard.edu/abs/2021Sust...1310256A). [doi](./Doi_(identifier)):[10.3390/su131810256](https://doi.org/10.3390%2Fsu131810256).
5. [↑](./Design_Patterns#cite_ref-gof4_5-0) Monteiro, Miguel Pessoa; Fernandes, João M. (26 January 2004). [*Pitfalls of aspectJ implementations of some of the gang-of-four design patterns*](https://repositorium.sdum.uminho.pt/handle/1822/752). Universidad de Extremadura. [ISBN](./ISBN_(identifier)) [978-84-688-8889-7](./Special:BookSources/978-84-688-8889-7) – via repositorium.uminho.pt.
6. [↑](./Design_Patterns#cite_ref-6) [Richard Helm](http://c2.com/cgi/wiki?RichardHelm)
7. [↑](./Design_Patterns#cite_ref-7) ["SIGPLAN FY '05 Annual Report"](http://www.sigplan.org/sites/default/files/report2005.pdf) (PDF).
8. [↑](./Design_Patterns#cite_ref-Graham2002_8-0) [Graham, Paul](./Paul_Graham_(computer_programmer)) (2002). [*Revenge of the Nerds*](http://www.paulgraham.com/icad.html). Retrieved 11 August 2012. 
9. [↑](./Design_Patterns#cite_ref-Norvig1998_9-0) [Norvig, Peter](./Peter_Norvig) (1998). [*Design Patterns in Dynamic Languages*](http://www.norvig.com/design-patterns/).
10. [↑](./Design_Patterns#cite_ref-10) Hannemann, Jan; Kiczales, Gregor (4 November 2002). ["Design pattern implementation in Java and aspectJ"](https://dl.acm.org/doi/10.1145/583854.582436). *[ACM SIGPLAN Notices](./ACM_SIGPLAN_Notices)*. **37** (11): 161–173. [doi](./Doi_(identifier)):[10.1145/583854.582436](https://doi.org/10.1145%2F583854.582436). [Archived](https://web.archive.org/web/20250309064302/https://dl.acm.org/doi/10.1145/583854.582436) from the original on 9 March 2025 – via [ACM Digital Library](./ACM_Digital_Library).
11. [↑](./Design_Patterns#cite_ref-11) Gamma, Erich; Helm, Richard; Johnson, Ralph (22 October 2009). ["Design Patterns 15 Years Later: An Interview with Erich Gamma, Richard Helm, and Ralph Johnson"](http://www.informit.com/articles/article.aspx?p=1404056). *InformIT* (Interview). Interviewed by Larry O'Brien. [Archived](https://web.archive.org/web/20190220090254/http://www.informit.com/articles/article.aspx?p=1404056) from the original on 20 February 2019. Retrieved 1 September 2019.

 
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