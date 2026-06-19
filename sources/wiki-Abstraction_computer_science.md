---
source: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
fetched: 2026-06-19
---

Software that provides access that hides details 

 

In [software](./Software), an **abstraction** provides access while hiding details that otherwise might make access more challenging.[[1]](./Abstraction_(computer_science)#cite_note-:1-1) It focuses attention on details of greater importance.[[2]](./Abstraction_(computer_science)#cite_note-:0-2)[[3]](./Abstraction_(computer_science)#cite_note-3) Examples include the [abstract data type](./Abstract_data_type) which separates use from the representation of [data](./Data_(computer_science))[[4]](./Abstraction_(computer_science)#cite_note-4) and [functions](./Function_(computer_programming)) that form a call tree that is more general at the base and more specific towards the leaves.

 

## Rationale

   

The essence of abstraction is preserving information that is relevant in a given context, and forgetting information that is irrelevant in that context.

  — [John V. Guttag](./John_Guttag)[[5]](./Abstraction_(computer_science)#cite_note-5)  

Computing mostly operates independently of the concrete world. The hardware implements a [model of computation](./Model_of_computation) that is interchangeable with others.[[6]](./Abstraction_(computer_science)#cite_note-6) The software is structured in [architectures](./Software_architecture) to enable humans to create the enormous systems by concentrating on a few issues at a time. These architectures are made of specific choices of abstractions. [Greenspun's tenth rule](./Greenspun's_tenth_rule) is an [aphorism](./Aphorism) on how such an architecture is both inevitable and complex.

 

Language abstraction is a central form of abstraction in computing: new artificial languages are developed to express specific aspects of a system. *[Modeling languages](./Modeling_languages)* help in planning. *[Computer languages](./Computer_language)* can be processed with a computer. An example of this abstraction process is the generational development of [programming language](./Programming_language) from the [first-generation programming language](./First-generation_programming_language) ([machine language](./Machine_language)) to the [second-generation programming language](./Second-generation_programming_language) ([assembly language](./Assembly_language)) and the [third-generation programming language](./Third-generation_programming_language) ([high-level programming language](./High-level_programming_language)). Each stage can be used as a stepping stone for the next stage. The language abstraction continues for example in [scripting languages](./Scripting_language) and [domain-specific languages](./Domain-specific_language).

 

Within a programming language, some features let the programmer create new abstractions. These include [subroutines](./Subroutine), [modules](./Modular_programming), [polymorphism](./Polymorphism_(computer_science)), and [software components](./Software_component). Some other abstractions such as [software design patterns](./Software_design_pattern) and [architectural styles](./Software_architecture#Architectural_styles_and_patterns) remain invisible to a [translator](./Translator_(computing)) and operate only in the design of a system.

 

Some abstractions try to limit the range of concepts a programmer needs to be aware of, by completely hiding the abstractions they are built on. The software engineer and writer [Joel Spolsky](./Joel_Spolsky) has criticized these efforts by claiming that all abstractions are *[leaky](./Leaky_abstraction)* – that they can never completely hide the details below;[[7]](./Abstraction_(computer_science)#cite_note-7) however, this does not negate the usefulness of abstraction.

 

Some abstractions are designed to inter-operate with other abstractions – for example, a programming language may contain a [foreign function interface](./Foreign_function_interface) for making calls to the lower-level language.

 

## Abstraction features

 

### Programming languages

 Further information: [Programming language](./Programming_language) 

Different programming languages provide different types of abstraction, depending on the intended applications for the language. For example:

 
- In [object-oriented programming](./Object-oriented_programming) languages such as [C++](./C++), [Object Pascal](./Object_Pascal), or [Java](./Java_(programming_language)), the concept of *abstraction* has become a declarative statement – using the [syntax](./Syntax_(programming_languages)) `function(parameters) = 0;` (in [C++](./C++)) or the [reserved words](./Reserved_word) (keywords) *`abstract`*[[8]](./Abstraction_(computer_science)#cite_note-Oracle_Java_abstract-8) and *`interface`*[[9]](./Abstraction_(computer_science)#cite_note-Oracle_Java_interface-9) (in [Java](./Java_(programming_language))). After such a declaration, it is the responsibility of the programmer to implement a [class](./Class_(computer_science)) to instantiate the [object](./Object_(computer_science)) of the declaration.
- [Functional programming](./Functional_programming) languages commonly exhibit abstractions related to functions, such as [lambda abstractions](./Lambda_abstraction) (making a term into a function of some variable) and [higher-order functions](./Higher-order_function) (parameters are functions).[[10]](./Abstraction_(computer_science)#cite_note-10) This has to be merged in the following sections. 
- Modern members of the [Lisp programming language family](./List_of_Lisp-family_programming_languages) such as [Clojure](./Clojure), [Scheme](./Scheme_(programming_language)) and [Common Lisp](./Common_Lisp) support [macro systems](./Macro_(computer_science)#Syntactic_macros) to allow syntactic abstraction. Other programming languages such as [Scala](./Scala_(programming_language)) also have macros, or very similar [metaprogramming](./Metaprogramming) features (for example, [Haskell](./Haskell) has [Template Haskell](./Template_Haskell), [OCaml](./OCaml) has [MetaOCaml](./MetaOCaml)). These can allow programs to omit [boilerplate code](./Boilerplate_code), abstract away tedious function call sequences, implement new [control flow](./Control_flow) structures, and implement [domain-specific languages](./Domain-specific_language) (DSLs), which allow domain-specific concepts to be expressed in concise and elegant ways. All of these, when used correctly, improve both the programmer's efficiency and the clarity of [source code](./Source_code) by making the intended purpose more explicit. A consequence of syntactic abstraction is also that any Lisp dialect, and almost any programming language, can in principle, be implemented in any modern Lisp with significantly reduced (but still non-trivial in most cases) effort when compared to "more traditional" programming languages such as [Python](./Python_(programming_language)), [C](./C_(programming_language)) or [Java](./Java_(programming_language)).

 

### Specification methods

 Further information: [Formal specification](./Formal_specification) 

Analysts have developed various methods to formally specify software systems. Some known methods include:

 
- Abstract-model based method (VDM, Z);
- Algebraic techniques (Larch, CLEAR, OBJ, ACT ONE, CASL);
- Process-based techniques (LOTOS, SDL, Estelle);
- Trace-based techniques (SPECIAL, TAM);
- Knowledge-based techniques (Refine, Gist).

 

### Specification languages

 Further information: [Specification language](./Specification_language) 

Specification languages generally rely on abstractions of one kind or another, since specifications are typically defined earlier in a project, (and at a more abstract level) than an eventual implementation. The [Unified Modeling Language](./Unified_Modeling_Language) (UML) specification language, for example, allows the definition of *abstract* classes, which in a waterfall project, remain abstract during the architecture and specification phase of the project.

 

## Control abstraction

 Further information: [Control flow](./Control_flow) 

Programming languages offer control abstraction as one of the main purposes of their use. Computer machines understand operations at the very low level such as moving some bits from one location of the memory to another location and producing the sum of two sequences of bits. Programming languages allow this to be done in the higher level. For example, consider this statement written in a [Pascal](./Pascal_(programming_language))-like fashion:

 `a := (1 + 2) * 5` 

To a human, this seems a fairly simple and obvious calculation (*"one plus two is three, times five is fifteen"*). However, the low-level steps necessary to carry out this evaluation, and return the value "15", and then assign that value to the variable "a", are actually quite subtle and complex. The values need to be converted to binary representation (often a much more complicated task than one would think) and the calculations decomposed (by the compiler or interpreter) into assembly instructions (again, which are much less intuitive to the programmer: operations such as shifting a binary register left, or adding the binary complement of the contents of one register to another, are simply not how humans think about the abstract arithmetical operations of addition or multiplication). Finally, assigning the resulting value of "15" to the variable labeled "a", so that "a" can be used later, involves additional 'behind-the-scenes' steps of looking up a variable's label and the resultant location in physical or virtual memory, storing the binary representation of "15" to that memory location, etc.

 

Without control abstraction, a programmer would need to specify *all* the register/binary-level steps each time they simply wanted to add or multiply a couple of numbers and assign the result to a variable. Such duplication of effort has two serious negative consequences:

 
1. it forces the programmer to constantly repeat fairly common tasks every time a similar operation is needed
2. it forces the programmer to program for the particular hardware and instruction set

 

### Structured programming

 Further information: [Structured programming](./Structured_programming) 

Structured programming involves the splitting of complex program tasks into smaller pieces with clear flow-control and interfaces between components, with a reduction of the complexity potential for side-effects.

 

In a simple program, this may aim to ensure that loops have single or obvious exit points and (where possible) to have single exit points from functions and procedures.

 

In a larger system, it may involve breaking down complex tasks into many different modules. Consider a system which handles payroll on ships and at shore offices:

 
- The uppermost level may feature a menu of typical end-user operations.
- Within that could be standalone executables or libraries for tasks such as signing on and off employees or printing checks.
- Within each of those standalone components there could be many different source files, each containing the program code to handle a part of the problem, with only selected interfaces available to other parts of the program. A sign on program could have source files for each data entry screen and the database interface (which may itself be a standalone third party library or a statically linked set of library routines).
- Either the database or the payroll application also has to initiate the process of exchanging data with between ship and shore, and that data transfer task will often contain many other components.

 

These layers produce the effect of isolating the implementation details of one component and its assorted internal methods from the others. Object-oriented programming embraces and extends this concept.

 

## Data abstraction

 Further information: [Abstract data type](./Abstract_data_type) 

Data abstraction enforces a clear separation between the *abstract* properties of a [data type](./Data_type) and the *concrete* details of its implementation. The abstract properties are those that are visible to client code that makes use of the data type—the *interface* to the data type—while the concrete implementation is kept entirely private, and indeed can change, for example to incorporate efficiency improvements over time. The idea is that such changes are not supposed to have any impact on client code, since they involve no difference in the abstract behaviour.

 

For example, one could define an [abstract data type](./Abstract_data_type) called *lookup table* which uniquely associates *keys* with *values*, and in which values may be retrieved by specifying their corresponding keys. Such a lookup table may be implemented in various ways: as a [hash table](./Hash_table), a [binary search tree](./Binary_search_tree), or even a simple linear [list](./List_(computing)) of (key:value) pairs. As far as client code is concerned, the abstract properties of the type are the same in each case.

 

Of course, this all relies on getting the details of the interface right in the first place, since any changes there can have major impacts on client code. As one way to look at this: the interface forms a *contract* on agreed behaviour between the data type and client code; anything not spelled out in the contract is subject to change without notice.

 

## Manual data abstraction

 

While much of data abstraction occurs through computer science and automation, there are times when this process is done manually and without programming intervention. One way this can be understood is through data abstraction within the process of conducting a [systematic review](./Systematic_review) of the literature. In this methodology, data is abstracted by one or several abstractors when conducting a [meta-analysis](./Meta-analysis), with errors reduced through dual data abstraction followed by independent checking, known as [adjudication](./Adjudication).[[11]](./Abstraction_(computer_science)#cite_note-11)

 

## Abstraction in object-oriented programming

 Further information: [Object (computer science)](./Object_(computer_science)) 

In [object-oriented programming](./Object-oriented_programming) theory, *abstraction* involves the facility to define objects that represent abstract "actors" that can perform work, report on and change their state, and "communicate" with other objects in the system. The term [encapsulation](./Encapsulation_(object-oriented_programming)) refers to the hiding of [state](./State_(computer_science)) details, but extending the concept of *data type* from earlier programming languages to associate *behavior* most strongly with the data, and standardizing the way that different data types interact, is the beginning of *abstraction*. When abstraction proceeds into the operations defined, enabling objects of different types to be substituted, it is called [polymorphism](./Polymorphism_(computer_science)). When it proceeds in the opposite direction, inside the types or classes, structuring them to simplify a complex set of relationships, it is called [delegation](./Delegation_(object-oriented_programming)) or [inheritance](./Inheritance_(object-oriented_programming)).

 

Various object-oriented programming languages offer similar facilities for abstraction, all to support a general strategy of [polymorphism](./Polymorphism_(computer_science)) in object-oriented programming, which includes the substitution of one [data type](./Data_type) for another in the same or similar role. Although not as generally supported, a [configuration](./Computer_configuration) or image or package may predetermine a great many of these [bindings](./Name_binding) at [compile time](./Compile_time), [link time](./Linker_(computing)), or [load time](./Loader_(computing)). This would leave only a minimum of such bindings to change at [run-time](./Run_time_(program_lifecycle_phase)).

 

[Common Lisp Object System](./Common_Lisp_Object_System) or [Self](./Self_(programming_language)), for example, feature less of a class-instance distinction and more use of delegation for [polymorphism](./Polymorphism_(computer_science)). Individual objects and functions are abstracted more flexibly to better fit with a shared functional heritage from [Lisp](./Lisp_(programming_language)).

 

C++ exemplifies another extreme: it relies heavily on [templates](./Generic_programming) and [overloading](./Method_overloading) and other static bindings at compile-time, which in turn has certain flexibility problems.

 

Although these examples offer alternate strategies for achieving the same abstraction, they do not fundamentally alter the need to support abstract nouns in code – all programming relies on an ability to abstract verbs as functions, nouns as data structures, and either as processes.

 

Consider for example a sample [Java](./Java_(programming_language)) fragment to represent some common farm "animals" to a level of abstraction suitable to model simple aspects of their hunger and feeding. It defines an `Animal` class to represent both the state of the animal and its functions:

 
```
public class Animal extends LivingThing
{
     private Location loc;
     private double energyReserves;

     public boolean isHungry() {
         return energyReserves < 2.5;
     }
     public void eat(Food food) {
         // Consume food
         energyReserves += food.getCalories();
     }
     public void moveTo(Location location) {
         // Move to new location
         this.loc = location;
     }
}

```
 

With the above definition, one could create objects of type Animal and call their methods like this:

 
```
thePig = new Animal();
theCow = new Animal();
if (thePig.isHungry()) {
    thePig.eat(tableScraps);
}
if (theCow.isHungry()) {
    theCow.eat(grass);
}
theCow.moveTo(theBarn);

```
 

In the above example, the class *`Animal`* is an abstraction used in place of an actual animal, *`LivingThing`* is a further abstraction (in this case a generalisation) of *`Animal`*.

 

If one requires a more differentiated hierarchy of animals – to differentiate, say, those who provide milk from those who provide nothing except meat at the end of their lives – that is an intermediary level of abstraction, probably DairyAnimal (cows, goats) who would eat foods suitable to giving good milk, and MeatAnimal (pigs, steers) who would eat foods to give the best meat-quality.

 

Such an abstraction could remove the need for the application coder to specify the type of food, so they could concentrate instead on the feeding schedule. The two classes could be related using [inheritance](./Inheritance_(object-oriented_programming)) or stand alone, and the programmer could define varying degrees of [polymorphism](./Polymorphism_(computer_science)) between the two types. These facilities tend to vary drastically between languages, but in general each can achieve anything that is possible with any of the others. A great many operation overloads, data type by data type, can have the same effect at compile-time as any degree of inheritance or other means to achieve polymorphism. The class notation is simply a coder's convenience.

 

### Object-oriented design

 Further information: [Object-oriented design](./Object-oriented_design) 

Decisions regarding what to abstract and what to keep under the control of the coder become the major concern of object-oriented design and [domain analysis](./Domain_analysis)—actually determining the relevant relationships in the real world is the concern of [object-oriented analysis](./Object-oriented_analysis_and_design) or [legacy analysis](./Legacy_analysis?action=edit&redlink=1).

 

In general, to determine appropriate abstraction, one must make many small decisions about scope (domain analysis), determine what other systems one must cooperate with (legacy analysis), then perform a detailed object-oriented analysis which is expressed within project time and budget constraints as an object-oriented design. In our simple example, the domain is the barnyard, the live pigs and cows and their eating habits are the legacy constraints, the detailed analysis is that coders must have the flexibility to feed the animals what is available and thus there is no reason to code the type of food into the class itself, and the design is a single simple Animal class of which pigs and cows are instances with the same functions. A decision to differentiate DairyAnimal would change the detailed analysis but the domain and legacy analysis would be unchanged—thus it is entirely under the control of the programmer, and it is called an abstraction in object-oriented programming as distinct from abstraction in domain or legacy analysis.

 

## Considerations

 

When discussing [formal semantics of programming languages](./Formal_semantics_of_programming_languages), [formal methods](./Formal_methods) or [abstract interpretation](./Abstract_interpretation), *abstraction* refers to the act of considering a less detailed, but safe, definition of the observed program behaviors. For instance, one may observe only the final result of program executions instead of considering all the intermediate steps of executions. Abstraction is defined to a *concrete* (more precise) model of execution.

 

Abstraction may be *exact* or *faithful* with respect to a property if one can answer a question about the property equally well on the concrete or abstract model. For instance, if one wishes to know what the result of the evaluation of a mathematical expression involving only integers +, -, ×, is worth [modulo](./Modular_arithmetic) *n*, then one needs only perform all operations modulo *n* (a familiar form of this abstraction is [casting out nines](./Casting_out_nines)).

 

Abstractions, however, though not necessarily *exact*, should be *sound*. That is, it should be possible to get sound answers from them—even though the abstraction may simply yield a result of [undecidability](./Undecidable_problem). For instance, students in a class may be abstracted by their minimal and maximal ages; if one asks whether a certain person belongs to that class, one may simply compare that person's age with the minimal and maximal ages; if his age lies outside the range, one may safely answer that the person does not belong to the class; if it does not, one may only answer "I don't know".

 

The level of abstraction included in a programming language can influence its overall [usability](./Usability). The [Cognitive dimensions](./Cognitive_dimensions) framework includes the concept of *abstraction gradient* in a formalism. This framework allows the designer of a programming language to study the trade-offs between abstraction and other characteristics of the design, and how changes in abstraction influence the language usability.

 

Abstractions can prove useful when dealing with computer programs, because non-trivial properties of computer programs are essentially [undecidable](./Undecidable_problem) (see [Rice's theorem](./Rice's_theorem)). As a consequence, automatic methods for deriving information on the behavior of computer programs either have to drop termination (on some occasions, they may fail, crash or never yield out a result), soundness (they may provide false information), or precision (they may answer "I don't know" to some questions).

 

Abstraction is the core concept of [abstract interpretation](./Abstract_interpretation). [Model checking](./Model_checking) generally takes place on abstract versions of the studied systems.

 

## Levels of abstraction

 Further information: [Abstraction layer](./Abstraction_layer) 

Computer science commonly presents *levels* (or, less commonly, *layers*) of abstraction, wherein each level represents a different model of the same information and processes, but with varying amounts of detail. Each level uses a system of expression involving a unique set of objects and compositions that apply only to a particular domain.[[12]](./Abstraction_(computer_science)#cite_note-12)
Each relatively abstract, "higher" level builds on a relatively concrete, "lower" level, which tends to provide an increasingly "granular" representation. For example, gates build on electronic circuits, binary on gates, machine language on binary, programming language on machine language, applications and operating systems on programming languages. Each level is embodied, but not determined, by the level beneath it, making it a language of description that is somewhat self-contained.

 

### Database systems

 Further information: [Database management system](./Database_management_system) 

Since many users of database systems lack in-depth familiarity with computer data-structures, database developers often hide complexity through the following levels:

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/09/Data_abstraction_levels.png/250px-Data_abstraction_levels.png)](./File:Data_abstraction_levels.png)Data abstraction levels of a database system 

*Physical level* – The lowest level of abstraction describes *how* a system actually stores data. The physical level describes complex low-level data structures in detail.

 

*Logical level* – The next higher level of abstraction describes *what* data the database stores, and what relationships exist among those data. The logical level thus describes an entire database in terms of a small number of relatively simple structures. Although implementation of the simple structures at the logical level may involve complex physical level structures, the user of the logical level does not need to be aware of this complexity. This is referred to as [physical data independence](./Physical_data_independence). [Database administrators](./Database_administrator), who must decide what information to keep in a database, use the logical level of abstraction.

 

*View level* – The highest level of abstraction describes only part of the entire database. Even though the logical level uses simpler structures, complexity remains because of the variety of information stored in a large database. Many users of a database system do not need all this information; instead, they need to access only a part of the database. The view level of abstraction exists to simplify their interaction with the system. The system may provide many [views](./View_(database)) for the same database.

 

### Layered architecture

 Further information: [Abstraction layer](./Abstraction_layer) 

The ability to provide a [design](./Design) of different levels of abstraction can

 
- simplify the design considerably
- enable different role players to effectively work at various levels of abstraction
- support the portability of [software artifacts](./Software_artifact) (model-based ideally)

 

[Systems design](./Systems_design) and [business process design](./Business_process_modeling) can both use this. Some [design processes](./Software_modeling) specifically generate designs that contain various levels of abstraction.

 

Layered architecture partitions the concerns of the application into stacked groups (layers).
It is a technique used in designing computer software, hardware, and communications in which system or network components are isolated in layers so that changes can be made in one layer without affecting the others.

 

## See also

  
- [Abstraction principle (computer programming)](./Abstraction_principle_(computer_programming))
- [Abstraction inversion](./Abstraction_inversion) for an anti-pattern of one danger in abstraction
- [Abstract data type](./Abstract_data_type) for an abstract description of a set of data
- [Algorithm](./Algorithm) for an abstract description of a computational procedure
- [Data modeling](./Data_modeling) for structuring data independent of the processes that use it
- [Decomposition (computer science)](./Decomposition_(computer_science))
- [Encapsulation](./Encapsulation_(object-oriented_programming)) for abstractions that hide implementation details
- [Greenspun's Tenth Rule](./Greenspun's_Tenth_Rule) for an aphorism about an (the?) optimum point in the space of abstractions
- [Higher-order function](./Higher-order_function) for abstraction where functions produce or consume other functions
- [Lambda abstraction](./Lambda_abstraction) for making a term into a function of some variable
- [List of abstractions (computer science)](./List_of_abstractions_(computer_science))
- [Refinement](./Program_refinement) for the opposite of abstraction in computing
- [Indirection](./Indirection)
- [Integer (computer science)](./Integer_(computer_science))
- [Heuristic (computer science)](./Heuristic_(computer_science))

 

## References

  
1. [↑](./Abstraction_(computer_science)#cite_ref-:1_1-0) Colburn, Timothy; Shute, Gary (5 June 2007). "Abstraction in Computer Science". *Minds and Machines*. **17** (2): 169–184. [doi](./Doi_(identifier)):[10.1007/s11023-007-9061-7](https://doi.org/10.1007%2Fs11023-007-9061-7). [ISSN](./ISSN_(identifier)) [0924-6495](https://search.worldcat.org/issn/0924-6495). [S2CID](./S2CID_(identifier)) [5927969](https://api.semanticscholar.org/CorpusID:5927969).
2. [↑](./Abstraction_(computer_science)#cite_ref-:0_2-0) Kramer, Jeff (1 April 2007). "Is abstraction the key to computing?". *Communications of the ACM*. **50** (4): 36–42. [doi](./Doi_(identifier)):[10.1145/1232743.1232745](https://doi.org/10.1145%2F1232743.1232745). [ISSN](./ISSN_(identifier)) [0001-0782](https://search.worldcat.org/issn/0001-0782). [S2CID](./S2CID_(identifier)) [12481509](https://api.semanticscholar.org/CorpusID:12481509).
3. [↑](./Abstraction_(computer_science)#cite_ref-3) Ben-Ari, Mordechai (1 March 1998). ["Constructivism in computer science education"](https://doi.org/10.1145%2F274790.274308). *ACM SIGCSE Bulletin*. **30** (1): 257, 257–261. [doi](./Doi_(identifier)):[10.1145/274790.274308](https://doi.org/10.1145%2F274790.274308). [ISSN](./ISSN_(identifier)) [0097-8418](https://search.worldcat.org/issn/0097-8418).
4. [↑](./Abstraction_(computer_science)#cite_ref-4) Liskov, Barbara (1 May 1988). "Keynote address - data abstraction and hierarchy". *Addendum to the proceedings on Object-oriented programming systems, languages and applications (Addendum) - OOPSLA '87*. Vol. 23. ACM. pp. 17–34. [doi](./Doi_(identifier)):[10.1145/62138.62141](https://doi.org/10.1145%2F62138.62141). [ISBN](./ISBN_(identifier)) [0897912667](./Special:BookSources/0897912667). [S2CID](./S2CID_(identifier)) [14219043](https://api.semanticscholar.org/CorpusID:14219043). `{{cite book}}`: `|journal=` ignored ([help](./Help:CS1_errors#periodical_ignored))
5. [↑](./Abstraction_(computer_science)#cite_ref-5) Guttag, John V. (18 January 2013). *Introduction to Computation and Programming Using Python* (Spring 2013 ed.). Cambridge, Massachusetts: The MIT Press. [ISBN](./ISBN_(identifier)) [978-0262519632](./Special:BookSources/978-0262519632).
6. [↑](./Abstraction_(computer_science)#cite_ref-6) Floridi, Luciano (September 2008). ["The Method of Levels of Abstraction"](http://link.springer.com/10.1007/s11023-008-9113-7). *Minds and Machines*. **18** (3): 303–329. [doi](./Doi_(identifier)):[10.1007/s11023-008-9113-7](https://doi.org/10.1007%2Fs11023-008-9113-7). [hdl](./Hdl_(identifier)):[2299/2998](https://hdl.handle.net/2299%2F2998). [ISSN](./ISSN_(identifier)) [0924-6495](https://search.worldcat.org/issn/0924-6495). [S2CID](./S2CID_(identifier)) [7522925](https://api.semanticscholar.org/CorpusID:7522925).
7. [↑](./Abstraction_(computer_science)#cite_ref-7) [Spolsky, Joel](./Joel_Spolsky) (11 November 2002). ["The Law of Leaky Abstractions"](http://www.joelonsoftware.com/articles/LeakyAbstractions.html).
8. [↑](./Abstraction_(computer_science)#cite_ref-Oracle_Java_abstract_8-0) ["Abstract Methods and Classes"](http://docs.oracle.com/javase/tutorial/java/IandI/abstract.html). *The Java Tutorials*. Oracle. Retrieved 4 September 2014.
9. [↑](./Abstraction_(computer_science)#cite_ref-Oracle_Java_interface_9-0) ["Using an Interface as a Type"](http://docs.oracle.com/javase/tutorial/java/IandI/interfaceAsType.html). *The Java Tutorials*. Oracle. Retrieved 4 September 2014.
10. [↑](./Abstraction_(computer_science)#cite_ref-10) This article is based on material taken from [Abstraction](https://foldoc.org/Abstraction) at the *[Free On-line Dictionary of Computing](./Free_On-line_Dictionary_of_Computing)*  prior to 1 November 2008 and incorporated under the "relicensing" terms of the [GFDL](./GNU_Free_Documentation_License), version 1.3 or later.
11. [↑](./Abstraction_(computer_science)#cite_ref-11) E, Jian-Yu; Saldanha, Ian J.; Canner, Joseph; Schmid, Christopher H.; Le, Jimmy T.; Li, Tianjing (2020). "Adjudication rather than experience of data abstraction matters more in reducing errors in abstracting data in systematic reviews". *Research Synthesis Methods*. **11** (3): 354–362. [doi](./Doi_(identifier)):[10.1002/jrsm.1396](https://doi.org/10.1002%2Fjrsm.1396). [ISSN](./ISSN_(identifier)) [1759-2879](https://search.worldcat.org/issn/1759-2879). [PMID](./PMID_(identifier)) [31955502](https://pubmed.ncbi.nlm.nih.gov/31955502). [S2CID](./S2CID_(identifier)) [210829764](https://api.semanticscholar.org/CorpusID:210829764).
12. [↑](./Abstraction_(computer_science)#cite_ref-12) [Luciano Floridi](./Luciano_Floridi), [*Levellism and the Method of Abstraction*](http://www.cs.ox.ac.uk/activities/ieg/research_reports/ieg_rr221104.pdf)
IEG – Research Report 22.11.04

 

## Further reading

  
- [Abelson, Harold](./Hal_Abelson); [Sussman, Gerald Jay](./Gerald_Jay_Sussman); [Sussman, Julie](./Julie_Sussman) (25 July 1996). [*Structure and Interpretation of Computer Programs*](https://web.archive.org/web/20090226050622/http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-10.html) (2 ed.). MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-01153-2](./Special:BookSources/978-0-262-01153-2). Archived from [the original](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-10.html) on 26 February 2009. Retrieved 22 June 2012.
- [Spolsky, Joel](./Joel_Spolsky) (11 November 2002). ["The Law of Leaky Abstractions"](http://www.joelonsoftware.com/articles/LeakyAbstractions.html). *Joel on Software*.
- [Abstraction/information hiding](https://www.cs.cornell.edu/courses/cs211/2006sp/Lectures/L08-abstraction/08_abstraction.html) – CS211 course, Cornell University.
- Roberts, Eric S. (1997). *Programming Abstractions in C A Second Course in Computer Science*.
- Palermo, Jeffrey (29 July 2008). ["The Onion Architecture"](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/). *Jeffrey Palermo*.
- Vishkin, Uzi (January 2011). ["Using simple abstraction to reinvent computing for parallelism"](https://doi.org/10.1145%2F1866739.1866757). *Communications of the ACM*. **54** (1): 75–85. [doi](./Doi_(identifier)):[10.1145/1866739.1866757](https://doi.org/10.1145%2F1866739.1866757).

  

## External links

 
- [SimArch](https://sites.google.com/site/simulationarchitecture/) example of layered architecture for distributed simulation systems.

 
| vteSoftware engineering |
| --- |
| Fields | Computer programmingDevOpsEmpirical software engineeringExperimental software engineeringFormal methodsRequirements engineeringSearch-based software engineeringSite reliability engineeringSocial software engineeringSoftware deploymentSoftware designSoftware maintenanceSoftware testingSystems analysis |
| Concepts | AbstractionCI/CDCompatibilityBackward compatibilityCompatibility layerCompatibility modeForward compatibilitySoftware incompatibilityComponent-based software engineeringData modelingEnterprise architectureFunctional specificationModeling languageProgramming paradigmSoftwareSoftware archaeologySoftware architectureSoftware configuration managementSoftware development process/methodologySoftware qualitySoftware quality assuranceSoftware systemSoftware verification and validationStructured analysisEssential analysis |
| Orientations | AgileAspect-orientedObject orientationOntologySDLCService orientation |
| Models | DevelopmentalAgileEUPExecutable UMLIncremental modelIterative modelPrototype modelRADScrumSpiral modelUPV-modelWaterfall modelXPModel-driven engineeringRound-trip engineeringOtherCMMIData modelER modelFunction modelInformation modelMetamodelingObject modelSPICESystems modelView modelLanguagesIDEFSysMLUMLUSL | Developmental | AgileEUPExecutable UMLIncremental modelIterative modelPrototype modelRADScrumSpiral modelUPV-modelWaterfall modelXPModel-driven engineeringRound-trip engineering | Other | CMMIData modelER modelFunction modelInformation modelMetamodelingObject modelSPICESystems modelView model | Languages | IDEFSysMLUMLUSL |
| Developmental | AgileEUPExecutable UMLIncremental modelIterative modelPrototype modelRADScrumSpiral modelUPV-modelWaterfall modelXPModel-driven engineeringRound-trip engineering |
| Other | CMMIData modelER modelFunction modelInformation modelMetamodelingObject modelSPICESystems modelView model |
| Languages | IDEFSysMLUMLUSL |
| Related fields | Computer engineeringComputer scienceInformation scienceProject managementRisk managementSystems engineering |
| CategoryCommons |

       Hidden categories below