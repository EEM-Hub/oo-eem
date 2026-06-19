---
source: https://en.wikipedia.org/wiki/Coupling_(computer_programming)
fetched: 2026-06-19
---

Degree of interdependence between software modules 

In [software engineering](./Software_engineering), **coupling** is the degree of interdependence between software [modules](./Modular_programming), a measure of how closely connected two routines or modules are,[[1]](./Coupling_(computer_programming)#cite_note-ISO_24765-1) and the strength of the relationships between modules.[[2]](./Coupling_(computer_programming)#cite_note-ISOIECTR19759_2005-2) Coupling is not binary but multi-dimensional.[[3]](./Coupling_(computer_programming)#cite_note-:0-3)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/09/CouplingVsCohesion.svg/250px-CouplingVsCohesion.svg.png)](./File:CouplingVsCohesion.svg)Coupling and [cohesion](./Cohesion_(computer_science)) 

Coupling is usually contrasted with [cohesion](./Cohesion_(computer_science)). [Low coupling](./Loose_coupling) often correlates with high cohesion, and vice versa. Low coupling is often thought to be a sign of a well-structured [computer system](./Computer_system) and a good design, and when combined with high cohesion, supports the general goals of high [readability](./Computer_programming#Readability_of_source_code) and [maintainability](./Maintainability).[[4]](./Coupling_(computer_programming)#cite_note-4)

 

## History

 

The [software quality metrics](./Software_metric) of coupling and cohesion were invented by [Larry Constantine](./Larry_Constantine) in the late 1960s as part of a [structured design](./Structured_design), based on characteristics of “good” programming practices that reduced maintenance and modification costs. Structured design, including cohesion and coupling, were published in the article *Stevens, Myers & Constantine* (1974)[[5]](./Coupling_(computer_programming)#cite_note-Stevens_1974-5) and the book *Yourdon & Constantine* (1979),[[6]](./Coupling_(computer_programming)#cite_note-Yourdon_1979-6) and the latter subsequently became standard terms.

 

## Coupling versus cohesion

 

Coupling and [cohesion](./Cohesion_(computer_science)) are terms which occur together very frequently. Coupling refers to the interdependencies between modules, while cohesion describes how related the functions within a single module are. Low cohesion implies that a given module performs tasks which are not very related to each other and hence can create problems as the module becomes large.

 

## Degree

 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/9c/Coupling_sketches_cropped_1.svg/330px-Coupling_sketches_cropped_1.svg.png)](./File:Coupling_sketches_cropped_1.svg)Conceptual model of coupling 

Coupling can be "low" (also "[loose](./Loose_coupling)" and "weak") or "high" (also "tight" and "strong"). Some types of coupling, in order of highest to lowest coupling, are as follows:

 

### Procedural programming

 

A module here refers to a subroutine of any kind, i.e. a set of one or more statements having a name and preferably its own set of variable names.

 Content coupling (high)Content coupling is said to occur when one module uses the code of another module, for instance a branch. This violates [information hiding](./Information_hiding) – a basic software design concept. Common couplingCommon coupling is said to occur when several modules have access to the same global data. But it can lead to uncontrolled error propagation and unforeseen side-effects when changes are made. External couplingExternal coupling occurs when two modules share an externally imposed data format, [communication protocol](./Communication_protocol), or device interface. This is basically related to the communication to external tools and devices. Control couplingControl coupling is one module controlling the flow of another, by passing it information on what to do (e.g., passing a what-to-do flag). Stamp coupling (data-structured coupling)Stamp coupling occurs when modules share a composite [data structure](./Data_structure) and use only parts of it, possibly different parts (e.g., passing a whole record to a function that needs only one field of it). In this situation, a modification in a field that a module does not need may lead to changing the way the module reads the record. To illustrate the concept of stamp coupling, consider a scenario involving a `UserProfile` [component](./Software_component). This component is designed to return the entire user profile information in response to [requests](./HTTP), even when [consumers](./User_agent) only require a specific [attribute](./Attribute_(computing)). This practice exemplifies stamp coupling, which can lead to significant [bandwidth](./Bandwidth_(computing)) issues, especially at scale. When any attribute within the `UserProfile` component changes, all consumers that interact with it may need to undergo [testing](./Software_testing), even if they do not utilize the modified attribute.[[7]](./Coupling_(computer_programming)#cite_note-7) Data couplingData coupling occurs when modules share data through, for example, parameters. Each datum is an elementary piece, and these are the only data shared (e.g., passing an integer to a function that computes a square root). 

### Object-oriented programming

 Subclass couplingDescribes the relationship between a child and its parent. The child is connected to its parent, but the parent is not connected to the child. Temporal couplingIt is when two actions are bundled together into one module just because they happen to occur at the same time. 

In recent work various other coupling concepts have been investigated and used as indicators for different modularization principles used in practice.[[8]](./Coupling_(computer_programming)#cite_note-Beck_2011-8)

 

#### Dynamic coupling

  Section title used in redirects  

The goal of defining and measuring this type of coupling is to provide a run-time evaluation of a [software system](./Software_system). It has been argued that static coupling metrics lose precision when dealing with an intensive use of dynamic binding or inheritance.[[9]](./Coupling_(computer_programming)#cite_note-Arisholm_2004-9) In the attempt to solve this issue, dynamic coupling measures have been taken into account.

 

#### Semantic coupling

  Section title used in redirects  

This kind of a coupling metric considers the conceptual similarities between software entities using, for example, comments and identifiers and relying on techniques such as [latent semantic indexing](./Latent_semantic_indexing) (LSI).

 

#### Logical coupling

  Section title used in redirects  

Logical coupling (or evolutionary coupling or change coupling) analysis exploits the release history of a software system to find change patterns among modules or classes: e.g., entities that are likely to be changed together or sequences of changes (a change in a class A is always followed by a change in a class B).

 

## Dimensions of coupling

 

According to Gregor Hohpe, coupling is multi-dimensional:[[3]](./Coupling_(computer_programming)#cite_note-:0-3)

 
- Technology Dependency
- Location Dependency
- Topology Dependency
- Data Format & Type Dependency
- Semantic Dependency
- Conversation Dependency
- Order Dependency
- Temporal Dependency

 

## Disadvantages of tight coupling

 

Tightly coupled systems tend to exhibit the following developmental characteristics, which are often seen as disadvantages:

 
1. A change in one module usually forces a [ripple effect](./Ripple_effect) of changes in other modules.
2. Assembly of modules might require more effort and/or time due to the increased inter-module dependency.
3. A particular module might be harder to [reuse](./Code_reuse) and/or test because dependent modules must be included.

 

## Performance issues

 

Whether loosely or tightly coupled, a system's performance is often reduced by message and parameter creation, transmission, translation (e.g. marshaling) and message interpretation (which might be a reference to a string, array or data structure), which require less overhead than creating a complicated message such as a [SOAP](./SOAP) message. Longer messages require more CPU and memory to produce. To optimize runtime performance, message length must be minimized and message meaning must be maximized.

 Message Transmission Overhead and PerformanceSince a message must be transmitted in full to retain its complete meaning, message transmission must be optimized. Longer messages require more CPU and memory to transmit and receive. Also, when necessary, receivers must reassemble a message into its original state to completely receive it. Hence, to optimize runtime performance, message length must be minimized and message meaning must be maximized. Message Translation Overhead and PerformanceMessage protocols and messages themselves often contain extra information (i.e., packet, structure, definition and language information). Hence, the receiver often needs to translate a message into a more refined form by removing extra characters and structure information and/or by converting values from one type to another. Any sort of translation increases CPU and/or memory overhead. To optimize runtime performance, message form and content must be reduced and refined to maximize its meaning and reduce translation. Message Interpretation Overhead and PerformanceAll messages must be interpreted by the receiver. Simple messages such as integers might not require additional processing to be interpreted. However, complex messages such as [SOAP](./SOAP) messages require a parser and a string transformer for them to exhibit intended meanings. To optimize runtime performance, messages must be refined and reduced to minimize interpretation overhead. 

## Solutions

 

One approach to decreasing coupling is [functional design](./Functional_design), which seeks to limit the responsibilities of modules along functionality. Coupling increases between two classes `A` and `B` if:

 
- `A` has an attribute that refers to (is of type) `B`.
- `A` calls on services of an object `B`.
- `A` has a method that references `B` (via return type or parameter).
- `A` is a subclass of (or implements) class `B`.

 

Low coupling refers to a relationship in which one module interacts with another module through a simple and stable interface and does not need to be concerned with the other module's internal implementation (see [Information Hiding](./Information_Hiding)).

 

Systems such as [CORBA](./CORBA) or [COM](./Component_Object_Model) allow objects to communicate with each other without having to know anything about the other object's implementation. Both of these systems even allow for objects to communicate with objects written in other languages.

 

## Coupling vs Connascence

 

Coupling describes the degree and nature of dependency between software components, focusing on what they share (e.g., data, control flow, technology) and how tightly they are bound. It evaluates two key dimensions: strength, which measures how difficult it is to change the dependency, and scope (or visibility), which indicates how widely the dependency is exposed across modules or boundaries. Traditional coupling types typically include content coupling, common coupling, control coupling, stamp coupling, external coupling, and data coupling.[[10]](./Coupling_(computer_programming)#cite_note-:03-10)[[11]](./Coupling_(computer_programming)#cite_note-:12-11)[[12]](./Coupling_(computer_programming)#cite_note-:2-12)

 

[Connascence](./Connascence), introduced by Meilir Page-Jones, provides a systematic framework for analyzing and measuring coupling dependencies. It evaluates dependencies based on three dimensions: strength, which measures the effort required to refactor or modify the dependency; locality, which considers how physically or logically close dependent components are in the [codebase](./Codebase); and degree, which measures how many components are affected by the dependency. Connascence can be categorized into static (detectable at compile-time) and dynamic (detectable at runtime) forms. Static connascence refers to compile-time dependencies, such as method signatures, while dynamic connascence refers to runtime dependencies, which can manifest in forms like connascence of timing, values, or algorithm.[[10]](./Coupling_(computer_programming)#cite_note-:03-10)[[11]](./Coupling_(computer_programming)#cite_note-:12-11)[[12]](./Coupling_(computer_programming)#cite_note-:2-12)

 

Each coupling flavor can exhibit multiple types of connascence, a specific type, or, in rare cases, none at all, depending on how the dependency is implemented. Common types of connascence include connascence of name, type, position, and meaning. Certain coupling types naturally align with specific connascence types; for example, data coupling often involves connascence of name or type. However, not every combination of coupling and connascence is practically meaningful. Dependencies relying on parameter order in a method signature demonstrate connascence of position, which is fragile and difficult to refactor because reordering parameters breaks the interface. In contrast, connascence of name, which relies on field or parameter names, is generally more resilient to change. Connascence types themselves exhibit a natural hierarchy of strength, with connascence of name typically considered weaker than connascence of meaning.[[10]](./Coupling_(computer_programming)#cite_note-:03-10)[[11]](./Coupling_(computer_programming)#cite_note-:12-11)[[12]](./Coupling_(computer_programming)#cite_note-:2-12)

 

Dependencies spanning module boundaries or distributed systems typically have higher coordination costs, increasing the difficulty of refactoring and propagating changes across distant boundaries. Modern practices, such as [dependency injection](./Dependency_injection) and interface-based programming, are often employed to reduce coupling strength and improve the maintainability of dependencies.[[10]](./Coupling_(computer_programming)#cite_note-:03-10)[[11]](./Coupling_(computer_programming)#cite_note-:12-11)[[12]](./Coupling_(computer_programming)#cite_note-:2-12)

 

While coupling identifies what is shared between components, connascence evaluates how those dependencies behave, how changes propagate, and how difficult they are to refactor. Strength, locality, and degree are interrelated; dependencies with high strength, wide scope, and spanning distant boundaries are significantly harder to refactor and maintain. Together, coupling provides a high-level overview of dependency relationships, while connascence offers a granular framework for analyzing dependency strength, locality, degree, and resilience to change, supporting the design of maintainable and robust systems.[[10]](./Coupling_(computer_programming)#cite_note-:03-10)[[11]](./Coupling_(computer_programming)#cite_note-:12-11)[[12]](./Coupling_(computer_programming)#cite_note-:2-12)

 

## Module coupling

 

Coupling in Software Engineering[[13]](./Coupling_(computer_programming)#cite_note-Pressman_1982-13) describes a version of metrics associated with this concept.

 

For data and control flow coupling:

 
-      d  i     {\displaystyle d_{i}}  ![{\displaystyle d_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/abe3154db7d4f92fb42dd1f80f52f528c6312e4a): number of input data parameters
-      c  i     {\displaystyle c_{i}}  ![{\displaystyle c_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/01acb7953ba52c2aa44264b5d0f8fd223aa178a2): number of input control parameters
-      d  o     {\displaystyle d_{o}}  ![{\displaystyle d_{o}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/db086c421821a5de9a49de753a122c28ad4233c9): number of output data parameters
-      c  o     {\displaystyle c_{o}}  ![{\displaystyle c_{o}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/02f2649d3dd5ca9fbc1de50f8b4c3f22fecbc4d9): number of output control parameters

 

For global coupling:

 
-      g  d     {\displaystyle g_{d}}  ![{\displaystyle g_{d}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c18ec1515fb376629473cad81ac6c4757cdd7da4): number of global variables used as data
-      g  c     {\displaystyle g_{c}}  ![{\displaystyle g_{c}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d79399909e8590ed8f8846b9e88f28ceea4df445): number of global variables used as control

 

For environmental coupling:

 
-     w   {\displaystyle w}  ![{\displaystyle w}](https://wikimedia.org/api/rest_v1/media/math/render/svg/88b1e0c8e1be5ebe69d18a8010676fa42d7961e6): number of modules called (fan-out)
-     r   {\displaystyle r}  ![{\displaystyle r}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d1ecb613aa2984f0576f70f86650b7c2a132538): number of modules calling the module under consideration (fan-in)

 

     C o u p l i n g  ( C ) = 1 − −    1   d  i   + 2 × ×   c  i   +  d  o   + 2 × ×   c  o   +  g  d   + 2 × ×   g  c   + w + r      {\displaystyle \mathrm {Coupling} (C)=1-{\frac {1}{d_{i}+2\times c_{i}+d_{o}+2\times c_{o}+g_{d}+2\times g_{c}+w+r}}}  ![{\displaystyle \mathrm {Coupling} (C)=1-{\frac {1}{d_{i}+2\times c_{i}+d_{o}+2\times c_{o}+g_{d}+2\times g_{c}+w+r}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7972c57de19863495a63d39a3a03d028ba3070ab)

 

`Coupling(C)` makes the value larger the more coupled the module is. This number ranges from approximately 0.67 (low coupling) to 1.0 (highly coupled)

 

For example, if a module has only a single input and output data parameter

 

    C = 1 − −    1  1 + 0 + 1 + 0 + 0 + 0 + 1 + 0    = 1 − −    1 3   = 0.67   {\displaystyle C=1-{\frac {1}{1+0+1+0+0+0+1+0}}=1-{\frac {1}{3}}=0.67}  ![{\displaystyle C=1-{\frac {1}{1+0+1+0+0+0+1+0}}=1-{\frac {1}{3}}=0.67}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dbc88b78f3adb05ad566574219038fcf17ae3bd9)

 

If a module has 5 input and output data parameters, an equal number of control parameters, and accesses 10 items of global data, with a fan-in of 3 and a fan-out of 4,

 

    C = 1 − −    1  5 + 2 × ×  5 + 5 + 2 × ×  5 + 10 + 0 + 3 + 4    = 0.98   {\displaystyle C=1-{\frac {1}{5+2\times 5+5+2\times 5+10+0+3+4}}=0.98}  ![{\displaystyle C=1-{\frac {1}{5+2\times 5+5+2\times 5+10+0+3+4}}=0.98}](https://wikimedia.org/api/rest_v1/media/math/render/svg/86f12badf6ce5c6523900dc9a3562afeeb993664)

 

## See also

 
- [Connascence (computer science)](./Connascence_(computer_science))
- [Coupling (physics)](./Coupling_(physics))
- [Dead code elimination](./Dead_code_elimination)
- [Dependency hell](./Dependency_hell)
- [Efferent coupling](./Efferent_coupling)
- [Inversion of control](./Inversion_of_control)
- [List of object-oriented programming terms](./List_of_object-oriented_programming_terms)
- [Loose coupling](./Loose_coupling)
- [Make (software)](./Make_(software))
- [Static code analysis](./Static_code_analysis)

 

## References

  
1. [↑](./Coupling_(computer_programming)#cite_ref-ISO_24765_1-0) ISO/IEC/IEEE 24765:2010 Systems and software engineering — Vocabulary
2. [↑](./Coupling_(computer_programming)#cite_ref-ISOIECTR19759_2005_2-0) ISO/IEC TR 19759:2005, Software Engineering — Guide to the Software Engineering Body of Knowledge (SWEBOK)
3. [1](./Coupling_(computer_programming)#cite_ref-:0_3-0) [2](./Coupling_(computer_programming)#cite_ref-:0_3-1) Hohpe, Gregor (2004). *Enterprise Integration Patterns: Designing, Building, and Deploying Messaging Solutions*. Addison-Wesley Professional. [ISBN](./ISBN_(identifier)) [978-0321200686](./Special:BookSources/978-0321200686).
4. [↑](./Coupling_(computer_programming)#cite_ref-4) Fregnan, Enrico; Baum, Tobias; Palomba, Fabio; Bacchelli, Alberto (March 2019). ["A survey on software coupling relations and tools"](https://linkinghub.elsevier.com/retrieve/pii/S0950584918302441). *Information and Software Technology*. **107**: 159–178. [doi](./Doi_(identifier)):[10.1016/J.INFSOF.2018.11.008](https://doi.org/10.1016%2FJ.INFSOF.2018.11.008). [ISSN](./ISSN_(identifier)) [0950-5849](https://search.worldcat.org/issn/0950-5849). Retrieved 2026-05-20.
5. [↑](./Coupling_(computer_programming)#cite_ref-Stevens_1974_5-0) [Stevens, Wayne P.](./Wayne_Stevens_(software_engineer)); [Myers, Glenford J.](./Glenford_J._Myers); [Constantine, Larry LeRoy](./Larry_LeRoy_Constantine) (June 1974). "Structured design". *[IBM Systems Journal](./IBM_Systems_Journal)*. **13** (2): 115–139. [doi](./Doi_(identifier)):[10.1147/sj.132.0115](https://doi.org/10.1147%2Fsj.132.0115).
6. [↑](./Coupling_(computer_programming)#cite_ref-Yourdon_1979_6-0) [Yourdon, Edward](./Edward_Yourdon); [Constantine, Larry LeRoy](./Larry_LeRoy_Constantine) (1979) [1975]. *Structured Design: Fundamentals of a Discipline of Computer Program and Systems Design*. Yourdon Press. [Bibcode](./Bibcode_(identifier)):[1979sdfd.book.....Y](https://ui.adsabs.harvard.edu/abs/1979sdfd.book.....Y). [ISBN](./ISBN_(identifier)) [978-0-13-854471-3](./Special:BookSources/978-0-13-854471-3).
7. [↑](./Coupling_(computer_programming)#cite_ref-7) Richards, Mark. *Fundamentals of Software Architecture: An Engineering Approach*. O'Reilly Media. [ISBN](./ISBN_(identifier)) [978-1492043454](./Special:BookSources/978-1492043454).
8. [↑](./Coupling_(computer_programming)#cite_ref-Beck_2011_8-0) Beck, Fabian; Diehl, Stephan (September 2011). "On the Congruence of Modularity and Code Coupling". *In Proceedings of the 19th ACM SIGSOFT Symposium and the 13th European Conference on Foundations of Software Engineering (SIGSOFT/FSE '11)*. Szeged, Hungary. p. 354. [doi](./Doi_(identifier)):[10.1145/2025113.2025162](https://doi.org/10.1145%2F2025113.2025162). [ISBN](./ISBN_(identifier)) [9781450304436](./Special:BookSources/9781450304436). [S2CID](./S2CID_(identifier)) [2413103](https://api.semanticscholar.org/CorpusID:2413103).`{{cite book}}`:  CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
9. [↑](./Coupling_(computer_programming)#cite_ref-Arisholm_2004_9-0) Arisholm, Erik; [Briand, Lionel C.](./Lionel_C._Briand); Føyen, Audun (August 2004). "Dynamic coupling measurement for object-oriented software". *[IEEE Transactions on Software Engineering](./IEEE_Transactions_on_Software_Engineering)*. **30** (8). [IEEE](./IEEE): 491–506. [Bibcode](./Bibcode_(identifier)):[2004ITSEn..30..491A](https://ui.adsabs.harvard.edu/abs/2004ITSEn..30..491A). [doi](./Doi_(identifier)):[10.1109/TSE.2004.41](https://doi.org/10.1109%2FTSE.2004.41). [hdl](./Hdl_(identifier)):[10852/9090](https://hdl.handle.net/10852%2F9090). [S2CID](./S2CID_(identifier)) [3074827](https://api.semanticscholar.org/CorpusID:3074827).
10. [1](./Coupling_(computer_programming)#cite_ref-:03_10-0) [2](./Coupling_(computer_programming)#cite_ref-:03_10-1) [3](./Coupling_(computer_programming)#cite_ref-:03_10-2) [4](./Coupling_(computer_programming)#cite_ref-:03_10-3) [5](./Coupling_(computer_programming)#cite_ref-:03_10-4) Page-Jones, Meilir (1988). *Practical Guide to Structured Systems Design*. Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0136907695](./Special:BookSources/978-0136907695).
11. [1](./Coupling_(computer_programming)#cite_ref-:12_11-0) [2](./Coupling_(computer_programming)#cite_ref-:12_11-1) [3](./Coupling_(computer_programming)#cite_ref-:12_11-2) [4](./Coupling_(computer_programming)#cite_ref-:12_11-3) [5](./Coupling_(computer_programming)#cite_ref-:12_11-4) Kleppmann, Martin (2017). *Designing Data-Intensive Applications: The Big Ideas Behind Reliable, Scalable, and Maintainable Systems*. O'Reilly Media. [ISBN](./ISBN_(identifier)) [978-1449373320](./Special:BookSources/978-1449373320).
12. [1](./Coupling_(computer_programming)#cite_ref-:2_12-0) [2](./Coupling_(computer_programming)#cite_ref-:2_12-1) [3](./Coupling_(computer_programming)#cite_ref-:2_12-2) [4](./Coupling_(computer_programming)#cite_ref-:2_12-3) [5](./Coupling_(computer_programming)#cite_ref-:2_12-4) *Fundamentals of Software Architecture: An Engineering Approach*. [ISBN](./ISBN_(identifier)) [978-1492043454](./Special:BookSources/978-1492043454).
13. [↑](./Coupling_(computer_programming)#cite_ref-Pressman_1982_13-0) [Pressman, Roger S.](./Roger_S._Pressman) (1982). [*Software Engineering - A Practitioner's Approach*](https://archive.org/details/softwareengineer00pres_0) (4 ed.). McGraw-Hill. [ISBN](./ISBN_(identifier)) [0-07-052182-4](./Special:BookSources/0-07-052182-4).

 

## Further reading

 
- [Myers, Glenford J.](./Glenford_J._Myers) (1974). *Reliable Software through Composite Design*. New York: Mason and Lipscomb Publishers.
- Offutt, A. Jefferson; [Harrold, Mary Jean](./Mary_Jean_Harrold); Kolte, Priyadarshan (March 1993). "A Software Metric System for Module Coupling". *[Journal of Systems and Software](./Journal_of_Systems_and_Software)*. **20** (3): 295–308. [doi](./Doi_(identifier)):[10.1016/0164-1212(93)90072-6](https://doi.org/10.1016%2F0164-1212%2893%2990072-6).
- Page-Jones, Meilir (1980). *The Practical Guide to Structured Systems Design*. New York: Yourdon Press. [ISBN](./ISBN_(identifier)) [978-8-12031482-5](./Special:BookSources/978-8-12031482-5).
- *Standard Glossary of Software Engineering Terminology*. New York: [IEEE](./IEEE). 1990. [ISBN](./ISBN_(identifier)) [0-7381-0391-8](./Special:BookSources/0-7381-0391-8). 610.12_1990.
- ["Curriculum for Certified Professional for Software Architecture (CPSA) - Foundation Level"](https://web.archive.org/web/20170329132933/http://www.isaqb.org/wp-content/uploads/2015/05/isaqb-Curriculum-foundation-v3-MAY-2015-EN.pdf) (PDF). 3.01. International Software Architecture Qualification Board e.V. (ISAQB). 2015-05-15 [2009]. Archived from [the original](https://www.isaqb.org/wp-content/uploads/2015/05/isaqb-Curriculum-foundation-v3-MAY-2015-EN.pdf) (PDF) on 2017-03-29. Retrieved 2019-06-23. [](http://www.isaqb.org/wp-content/uploads/2015/05/isaqb-Lehrplan-foundation-v3-MAI-2015-DE.pdf) [Archived](https://web.archive.org/web/20160222052330/http://www.isaqb.org/wp-content/uploads/2015/05/isaqb-Lehrplan-foundation-v3-MAI-2015-DE.pdf) 2016-02-22 at the [Wayback Machine](./Wayback_Machine)