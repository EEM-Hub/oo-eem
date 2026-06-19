---
source: https://en.wikipedia.org/wiki/Object-oriented_programming
fetched: 2026-06-19
---

Programming paradigm based on objects 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/86/Oop-uml-class-example.svg/330px-Oop-uml-class-example.svg.png)](./File:Oop-uml-class-example.svg)[UML](./UML) notation for a class. This Button class has [variables](./Variable_(computer_science)) for data, and [functions](./Method_(computer_programming)). Through inheritance, a subclass can be created as a subset of the Button class. Objects are instances of a class. 

**Object-oriented programming** (**OOP**) is a [programming paradigm](./Programming_paradigm) based on [objects](./Object_(computer_science))[[1]](./Object-oriented_programming#cite_note-alanKayOnOO-1) – [software](./Software) entities that [encapsulate](./Encapsulation_(programming)) [data](./Data) and [function(s)](./Function_(computer_programming)).[*[clarification needed](./Wikipedia:Please_clarify)*] An OOP [computer program](./Computer_program) consists of objects that interact with one another.[[2]](./Object-oriented_programming#cite_note-2)[[3]](./Object-oriented_programming#cite_note-3) An *OOP [language](./Programming_language)* is one that provides object-oriented programming features, but as the set of features that contribute to OOP is contested, classifying a language as OOP – and the degree to which it supports OOP – is debatable. As paradigms are not mutually exclusive, a language can be [multi-paradigm](./Multi-paradigm) (i.e. categorized as more than only OOP).

 

Notable languages with OOP support include [Ada](./Ada_(programming_language)), [ActionScript](./ActionScript), [C++](./C++), [Common Lisp](./Common_Lisp), [C#](./C_Sharp_(programming_language)), [Dart](./Dart_(programming_language)), [Eiffel](./Eiffel_(programming_language)), [Fortran 2003](./Fortran#Fortran_2003), [Haxe](./Haxe), [Java](./Java_(programming_language)),[[4]](./Object-oriented_programming#cite_note-FOOTNOTEBloch2018xi–xiiForeword-4) [JavaScript](./JavaScript), [Kotlin](./Kotlin_(programming_language)), [Logo](./Logo_(programming_language)), [MATLAB](./MATLAB), [Objective-C](./Objective-C), [Object Pascal](./Object_Pascal), [Perl](./Perl), [PHP](./PHP), [Python](./Python_(programming_language)), [R](./R_(programming_language)), [Raku](./Raku_(programming_language)), [Ruby](./Ruby_(programming_language)), [Scala](./Scala_(programming_language)), [SIMSCRIPT](./SIMSCRIPT), [Simula](./Simula), [Smalltalk](./Smalltalk), [Swift](./Swift_(programming_language)), [Vala](./Vala_(programming_language)) and [Visual Basic (.NET)](./Visual_Basic_(.NET)).

 

## History

 

The idea of "objects" in programming began with the [artificial intelligence](./Artificial_intelligence) group at [Massachusetts Institute of Technology](./Massachusetts_Institute_of_Technology) (MIT) in the late 1950s and early 1960s. Here, "object" referred to [LISP](./Lisp_(programming_language)) atoms with identified properties (attributes).[[5]](./Object-oriented_programming#cite_note-5)[[6]](./Object-oriented_programming#cite_note-6)
Another early example was [Sketchpad](./Sketchpad) created by [Ivan Sutherland](./Ivan_Sutherland) at MIT in 1960–1961. In the glossary of his technical report, Sutherland defined terms like "object" and "instance" (with the class concept covered by "master" or "definition"), albeit specialized to graphical interaction.[[7]](./Object-oriented_programming#cite_note-7) Later, in 1968, AED-0, MIT's version of the [ALGOL](./ALGOL) programming language, connected data structures ("plexes") and procedures, prefiguring what were later termed "messages", "methods", and "member functions".[[8]](./Object-oriented_programming#cite_note-simuladev-8)[[9]](./Object-oriented_programming#cite_note-9)
Topics such as [data abstraction](./Data_abstraction) and [modular programming](./Modular_programming) were common points of discussion at this time.

 

Meanwhile, in Norway, [Simula](./Simula) was developed during the years 1961–1967.[[8]](./Object-oriented_programming#cite_note-simuladev-8) Simula introduced essential object-oriented ideas, such as [classes](./Class_(programming)), inheritance, and [dynamic binding](./Dynamic_binding_(computing)).[[10]](./Object-oriented_programming#cite_note-auto-10)
Simula was used mainly by researchers involved with [physical modelling](./Physical_modelling), like the movement of ships and their content through cargo ports.[[10]](./Object-oriented_programming#cite_note-auto-10) Simula is generally accepted as being the first language with the primary features and framework of an object-oriented language.[[11]](./Object-oriented_programming#cite_note-11)

   

I thought of objects being like biological cells and/or individual computers on a network, only able to communicate with messages (so messaging came at the very beginning – it took a while to see how to do messaging in a programming language efficiently enough to be useful).

  — Alan Kay, [[1]](./Object-oriented_programming#cite_note-alanKayOnOO-1)  

Influenced by both MIT and Simula, [Alan Kay](./Alan_Kay) began developing his own ideas in November 1966. He would go on to create [Smalltalk](./Smalltalk), an influential OOP language. By 1967, Kay was already using the term "object-oriented programming" in conversation.[[1]](./Object-oriented_programming#cite_note-alanKayOnOO-1) Although sometimes called the "father" of OOP,[[12]](./Object-oriented_programming#cite_note-12) Kay has said his ideas differ from how OOP is commonly understood, and has implied that the computer science establishment did not adopt his notion.[[1]](./Object-oriented_programming#cite_note-alanKayOnOO-1)
A 1976 MIT memo co-authored by [Barbara Liskov](./Barbara_Liskov) lists [Simula 67](./Simula_67), [CLU](./CLU_(programming_language)), and [Alphard](./Alphard_(programming_language)) as object-oriented languages, but does not mention Smalltalk.[[13]](./Object-oriented_programming#cite_note-13)

 

In the 1970s, the first version of the [Smalltalk](./Smalltalk) programming language was developed at [Xerox PARC](./Xerox_PARC) by [Alan Kay](./Alan_Kay), [Dan Ingalls](./Dan_Ingalls) and [Adele Goldberg](./Adele_Goldberg_(computer_scientist)). Smalltalk-72 was notable for use of objects at the language level and its graphical development environment.[[14]](./Object-oriented_programming#cite_note-Bertrand_Meyer_2009_329-14) Smalltalk was a fully dynamic system, allowing users to create and modify classes as they worked.[[15]](./Object-oriented_programming#cite_note-15) Much of the theory of OOP was developed in the context of Smalltalk, for example multiple inheritance.[[16]](./Object-oriented_programming#cite_note-16)

 

In the late 1970s and 1980s, OOP rose to prominence. The [Flavors](./Flavors_(programming_language)) object-oriented Lisp was developed starting 1979, introducing [multiple inheritance](./Multiple_inheritance) and [mixins](./Mixin).[[17]](./Object-oriented_programming#cite_note-17) In August 1981, [Byte Magazine](./Byte_Magazine) highlighted Smalltalk and OOP, introducing these ideas to a wide audience.[[18]](./Object-oriented_programming#cite_note-18) LOOPS, the object system for [Interlisp](./Interlisp)-D, was influenced by Smalltalk and Flavors, and a paper about it was published in 1982.[[19]](./Object-oriented_programming#cite_note-19) In 1986, the first *Conference on Object-Oriented Programming, Systems, Languages, and Applications* ([OOPSLA](./OOPSLA)) was attended by 1,000 people. This conference marked the start of efforts to consolidate Lisp object systems, eventually resulting in the [Common Lisp Object System](./Common_Lisp_Object_System). In the 1980s, there were a few attempts to design [processor architectures](./Processor_design) that included [hardware](./Computer_hardware) support for objects in [memory](./Computer_memory), but these were not successful. Examples include the [Intel iAPX 432](./Intel_iAPX_432) and the [Linn Smart](./Linn_Products) [Rekursiv](./Rekursiv).

 

In the mid-1980s, new object-oriented languages like [Objective-C](./Objective-C), [C++](./C++), and the [Eiffel language](./Eiffel_language) emerged. Objective-C was developed by [Brad Cox](./Brad_Cox), who had used Smalltalk at [ITT Inc.](./ITT_Inc.) [Bjarne Stroustrup](./Bjarne_Stroustrup) created C++ based on his experience using Simula for his PhD thesis.[[14]](./Object-oriented_programming#cite_note-Bertrand_Meyer_2009_329-14) [Bertrand Meyer](./Bertrand_Meyer) produced the first design of the Eiffel language in 1985, which focused on software quality using a [design by contract](./Design_by_contract) approach.[[20]](./Object-oriented_programming#cite_note-FOOTNOTEMeyer1997-20)

 

In the 1990s, OOP became the main way of programming, especially as more languages supported it. These included [Visual FoxPro](./Visual_FoxPro) 3.0,[[21]](./Object-oriented_programming#cite_note-21)[[22]](./Object-oriented_programming#cite_note-22) [C++](./C++),[[23]](./Object-oriented_programming#cite_note-23) and [Delphi](./Delphi_(software))[*[citation needed](./Wikipedia:Citation_needed)*]. OOP became even more popular with the rise of [graphical user interfaces](./Graphical_user_interface), which used objects for buttons, menus and other elements. One well-known example is Apple's [Cocoa](./Cocoa_(software)) framework, used on [macOS](./MacOS) and written in [Objective-C](./Objective-C). OOP toolkits also enhanced the popularity of [event-driven programming](./Event-driven_programming).[*[citation needed](./Wikipedia:Citation_needed)*]

 

At [ETH Zürich](./ETH_Zürich), [Niklaus Wirth](./Niklaus_Wirth) and his colleagues created new approaches to OOP. [Modula-2](./Modula-2) (1978) and [Oberon](./Oberon_(programming_language)) (1987), included a distinctive approach to object orientation, classes, and type checking across module boundaries. Inheritance is not obvious in Wirth's design since his nomenclature looks in the opposite direction: It is called type extension and the viewpoint is from the parent down to the inheritor.

 

Many programming languages that were initially developed before OOP was popular have been augmented with object-oriented features, including [Ada](./Ada_(programming_language)), [BASIC](./BASIC), [Fortran](./Fortran), [Pascal](./Pascal_(programming_language)), and [COBOL](./COBOL).

 

## Features

 

 See also: [List of object-oriented programming terms](./List_of_object-oriented_programming_terms) 

The OOP features provided by languages varies. Below are some common features of OOP languages.[[24]](./Object-oriented_programming#cite_note-ArmstrongQuarks-24)[[25]](./Object-oriented_programming#cite_note-25)[[26]](./Object-oriented_programming#cite_note-26)[[27]](./Object-oriented_programming#cite_note-pierce-27) Comparing OOP with other styles, like [relational programming](./Relational_programming), is difficult because there isn't a clear, agreed-upon definition of OOP.[[28]](./Object-oriented_programming#cite_note-DatePage650-28)

 

### Encapsulation and information hiding

 

[Information hiding](./Information_hiding) and [encapsulation](./Encapsulation_(computer_programming)) can refer to several related concepts:

 
- [Cohesion](./Cohesion_(computer_science)), keeping related [fields](./Field_(computer_science)) and [methods](./Method_(computer_programming)) together. A field (a.k.a. attribute or property) contains information (a.k.a. state) as a [variable](./Variable_(computer_science)). A method (a.k.a. [function](./Function_(programming)) or action) defines behavior via logic code.
- [Decoupling](./Coupling_(computer_programming)), organizing code so that only certain parts of the data are used by related functions. Decoupling makes it easier to change how an object works on the inside without affecting other parts of the [codebase](./Codebase), such as in [code refactoring](./Code_refactoring).[[29]](./Object-oriented_programming#cite_note-29) Objects act as a boundary between their internal workings and external, consuming code.
- [Data hiding](./Data_hiding), keeping the internal details of an object hidden from outside code. Consuming code can only interact with an object via its public members, due to the language providing [access modifiers](./Access_modifier) that control visibility.

 

Some programming languages, like Java, provide information hiding via visibility key words (`private` and `public`).[[30]](./Object-oriented_programming#cite_note-FOOTNOTEBloch201873–77Chapter_§4_Item15_Minimize_the_accessibility_of_classes_and_members-30) Some languages like Python don't provide a visibility feature, but developers might follow a convention such as starting a private member name with an underscore. Intermediate levels of access also exist, such as Java's `protected` keyword, (which allows access from the same class and its subclasses, but not objects of a different class), and the `internal` keyword in C#, Swift, and Kotlin, which restricts access to files within the same module.[[31]](./Object-oriented_programming#cite_note-31)

 

Supporters of information hiding and data abstraction say it makes code easier to reuse and intuitively represents real-world situations.[[32]](./Object-oriented_programming#cite_note-Luca1985-32)[[33]](./Object-oriented_programming#cite_note-33) However, others argue that OOP does not enhance readability or modularity.[[34]](./Object-oriented_programming#cite_note-badprop-34)[[35]](./Object-oriented_programming#cite_note-armstrongjoe-35) [Eric S. Raymond](./Eric_S._Raymond) has written that OOP languages tend to encourage thickly layered programs that destroy transparency.[[36]](./Object-oriented_programming#cite_note-Eric_S._Raymond_2003-36) Raymond compares this unfavourably to the approach taken with [Unix](./Unix) and the [C](./C_(programming_language)) language.[[36]](./Object-oriented_programming#cite_note-Eric_S._Raymond_2003-36)

 

[SOLID](./SOLID) includes the [open/closed principle](./Open/closed_principle), which says that classes and functions should be "open for extension, but closed for modification". [Luca Cardelli](./Luca_Cardelli) has stated that OOP languages have "extremely poor modularity properties with respect to class extension and modification", and tend to be extremely complex.[[34]](./Object-oriented_programming#cite_note-badprop-34) The latter point is reiterated by [Joe Armstrong](./Joe_Armstrong_(programmer)), the principal inventor of [Erlang](./Erlang_(programming_language)), who is quoted as saying:[[35]](./Object-oriented_programming#cite_note-armstrongjoe-35)

 

The problem with object-oriented languages is they've got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle.

 

Leo Brodie says that information hiding can lead to [duplicate code](./Duplicate_code),[[37]](./Object-oriented_programming#cite_note-37) which goes against the [don't repeat yourself](./Don't_repeat_yourself) rule of software development.[[38]](./Object-oriented_programming#cite_note-38)

 

### Inheritance

 

[Inheritance](./Inheritance_(object-oriented_programming)) can be supported via the [class](./Class_(programming)) or the [prototype](./Prototype-based_programming), which have differences but use similar terms like object and [instance](./Instance_(computer_science)).

 

#### Class-based

 

In [class-based programming](./Class-based_programming), the most common type of OOP, an object is an instance of a class. The class defines the data (variables) and methods (logic). An object is created via the [constructor](./Constructor_(object-oriented_programming)). Every instance of the class has the same set of variables and methods. Elements may include:

 
- [Class variable](./Class_variable) – belongs to the class itself; all objects of the class share one copy
- [Instance variable](./Instance_variable) – belongs to an object; every object has its own version of these variables
- [Member variable](./Member_variable) – refers to both the class and instance variables of a class
- Class method – can only use class variables
- Instance method – belongs to an object; can use both instance and class variables

 

Classes may inherit from other classes, creating a hierarchy of classes: a case of a subclass inheriting from a super-class. For example, an `Employee` class might inherit from a `Person` class which endows the Employee object with the variables from `Person`. The subclass may add variables and methods that do not affect the super-class. Most languages also allow the subclass to override super-class methods. Some languages support [multiple inheritance](./Multiple_inheritance), where a class can inherit from more than one class, and other languages similarly support [mixins](./Mixin) or [traits](./Trait_(computer_programming)). For example, a mixin called UnicodeConversionMixin might add a method unicode_to_ascii() to both a FileReader and a WebPageScraper class.

 

An [abstract class](./Abstract_class) cannot be directly instantiated as an object. It is only used as a super-class. 

 

Other classes are utility classes which contain only class variables and methods and are not meant to be instantiated or subclassed.[[39]](./Object-oriented_programming#cite_note-FOOTNOTEBloch201819Chapter_§2_Item_4_Enforce_noninstantiability_with_a_private_constructor-39)

 

#### Prototype-based

 

Instead of providing a class concept, in [prototype-based programming](./Prototype-based_programming), an object is linked to another object, called its *prototype* or *parent*. In Self, an object may have multiple or no parents,[[40]](./Object-oriented_programming#cite_note-40) but in the most popular prototype-based language, [JavaScript](./JavaScript), an object has exactly one prototype link, up to the base object whose prototype is null.

 

A prototype acts as a model for new objects. For example, if you have an object `fruit`, you can make two objects `apple` and `orange` that share traits of the `fruit` prototype. Prototype-based languages also allow objects to have their own unique properties, so the `apple` object might have an attribute `sugar_content`, while the `orange` or `fruit` objects do not.

 

#### No inheritance

 

In all OOP languages, via [object composition](./Object_composition), an object can contain other objects. For example, an `Employee` object might contain an `Address` object, along with other information like `name` and `position`. Composition is a "has-a" relationships, like "an employee has an address". Some languages, like [Go](./Go_(programming_language)), don't support inheritance.[[41]](./Object-oriented_programming#cite_note-41) Instead, they encourage "[composition over inheritance](./Composition_over_inheritance)", where objects are built using smaller parts instead of parent-child relationships. For example, instead of inheriting from class Person, the Employee class could simply contain a Person object. This lets the Employee class control how much of Person it exposes to other parts of the program. [Delegation](./Delegation_(object-oriented_programming)) is another language feature that can be used as an alternative to inheritance.

 

Programmers have different opinions on inheritance. Bjarne Stroustrup, author of C++, has stated that it is possible to do OOP without inheritance.[[42]](./Object-oriented_programming#cite_note-42) [Rob Pike](./Rob_Pike) has criticized inheritance for creating complex hierarchies instead of simpler solutions.[[43]](./Object-oriented_programming#cite_note-43)

 

#### Inheritance and behavioral subtyping

 

People often think that if one class inherits from another, it means the subclass "[is a](./Is_a)" more specific version of the original class. This presumes the [program semantics](./Program_semantics) are that objects from the subclass can always replace objects from the original class without problems. This concept is known as [behavioral subtyping](./Behavioral_subtyping), more specifically the [Liskov substitution principle](./Liskov_substitution_principle).

 

However, this is often not true, especially in programming languages that allow [mutable](./Mutable) objects, objects that change after they are created. In fact, [subtype polymorphism](./Subtype_polymorphism) as enforced by the [type checker](./Type_checker) in OOP languages cannot guarantee behavioral subtyping in most if not all contexts. For example, the [circle-ellipse problem](./Circle-ellipse_problem) is notoriously difficult to handle using OOP's concept of inheritance. Behavioral subtyping is undecidable in general, so it cannot be easily implemented by a compiler. Because of this, programmers must carefully design class hierarchies to avoid mistakes that the programming language itself cannot catch.

 

### Dynamic dispatch

 

A method may be invoked via [dynamic dispatch](./Dynamic_dispatch) such that the method is selected at runtime instead of compile time. If the method choice depends on more than one type of object (such as other objects passed as parameters), it's called [multiple dispatch](./Multiple_dispatch). In this context, a method call is also known as [message passing](./Message_passing), meaning the method name and its inputs are like a message sent to the object for it to act on.[[44]](./Object-oriented_programming#cite_note-44)

 

Dynamic dispatch works together with inheritance: if an object doesn't have the requested method, it looks up to its parent class ([delegation](./Delegation_(object-oriented_programming))), and continues up the chain to find a matching method.

 

### Polymorphism

 

[Polymorphism](./Polymorphism_(computer_science)) in OOP refers to [subtyping](./Subtyping) or subtype polymorphism, where a function can work with a specific [interface](./Interface_(object-oriented_programming)) and thus manipulate entities of different classes in a uniform manner.[[45]](./Object-oriented_programming#cite_note-45)

 

For example, imagine a program has two shapes: a circle and a square. Both come from a common class called "Shape." Each shape has its own way of drawing itself. With subtype polymorphism, the program doesn't need to know the type of each shape, and can simply call the "Draw" method for each shape. The programming language runtime will ensure the correct version of the "Draw" method runs for each shape. Because the details of each shape are handled inside their own classes, this makes the code simpler and more organized, enabling strong [separation of concerns](./Separation_of_concerns).

 

### Open recursion

 

An object's methods can access the object's data. Many programming languages use a special word, like [`this`](./This_(computer_programming)) or `self`, to refer to the current object. In languages that support [open recursion](./Open_recursion), a method in an object can call other methods in the same object, including itself, using this special word. This allows a method in one class to call another method defined later in a subclass, a feature known as [late binding](./Late_binding).

 

## Design patterns

 

[Design patterns](./Design_pattern_(computer_science)) are common solutions to problems in software design. Some design patterns are especially useful for OOP, and design patterns are typically introduced in an OOP context.

 

### Real-world modeling and relationships

 

Sometimes, objects represent real-world things and processes in digital form.[[46]](./Object-oriented_programming#cite_note-46) For example, a graphics program may have objects such as `circle`, `square`, and `menu`. An online shopping system might have objects such as `shopping cart`, `customer`, and `product`. [Niklaus Wirth](./Niklaus_Wirth) said, "This paradigm [OOP] closely reflects the structure of systems in the real world and is therefore well suited to model complex systems with complex behavior".[[47]](./Object-oriented_programming#cite_note-47)

 

However, more often, objects represent abstract entities, like an open file or a unit converter. Not everyone agrees that OOP makes it easy to copy the real world exactly or that doing so is even necessary. [Bob Martin](./Robert_C._Martin) suggests that because classes are software, their relationships don't match the real-world relationships they represent.[[48]](./Object-oriented_programming#cite_note-48) [Bertrand Meyer](./Bertrand_Meyer) argues that a program is not a model of the world but a model of some part of the world; "Reality is a cousin twice removed".[[49]](./Object-oriented_programming#cite_note-FOOTNOTEMeyer1997230-49) [Steve Yegge](./Steve_Yegge) noted that [natural languages](./Natural_language) lack the OOP approach of naming a thing (object) before an action (method), as opposed to [functional programming](./Functional_programming) which does the reverse.[[50]](./Object-oriented_programming#cite_note-executioniKoN-50) This can make an OOP solution more complex than one written via [procedural programming](./Procedural_programming).[[51]](./Object-oriented_programming#cite_note-executioniKoN2-51)

 

### Object patterns

 

The following are notable [software design patterns](./Software_design_pattern) for OOP objects.[[52]](./Object-oriented_programming#cite_note-R.C.Martin-52)

 
- [Function object](./Function_object): Class with one main method that acts like an [anonymous function](./Anonymous_function) (in C++, the function operator, `operator()`)
- [Immutable object](./Immutable_object): does not change state after creation
- [First-class object](./First-class_object): can be used without restriction
- [Container object](./Container_object): contains other objects
- [Factory object](./Factory_object): creates other objects
- [Metaobject](./Metaobject): Used to create other objects (similar to a [class](./Class_(computer_science)), but an object)
- [Prototype object](./Prototype_pattern): a specialized metaobject that creates new objects by copying itself
- [Singleton object](./Singleton_pattern): only instance of its class for the lifetime of the program
- [Filter object](./Filter_object): receives a stream of data as its input and transforms it into the object's output

 

A common [anti-pattern](./Anti-pattern) is the [God object](./God_object), an object that knows or does too much.

 

### Gang of Four design patterns

 Main article: [Design pattern (computer science)](./Design_pattern_(computer_science)) 

*[Design Patterns: Elements of Reusable Object-Oriented Software](./Design_Patterns:_Elements_of_Reusable_Object-Oriented_Software)* is a famous book published in 1994 by four authors: [Erich Gamma](./Erich_Gamma), [Richard Helm](./Richard_Helm), [Ralph Johnson](./Ralph_Johnson_(computer_scientist)), and [John Vlissides](./John_Vlissides). People often call them the "Gang of Four". The book talks about the strengths and weaknesses of OOP and explains 23 common ways to solve programming problems.

 

These solutions, called "design patterns," are grouped into three types:

 
- *[Creational patterns](./Creational_pattern)* (5): [Factory method pattern](./Factory_method_pattern), [Abstract factory pattern](./Abstract_factory_pattern), [Singleton pattern](./Singleton_pattern), [Builder pattern](./Builder_pattern), [Prototype pattern](./Prototype_pattern)
- *[Structural patterns](./Structural_pattern)* (7): [Adapter pattern](./Adapter_pattern), [Bridge pattern](./Bridge_pattern), [Composite pattern](./Composite_pattern), [Decorator pattern](./Decorator_pattern), [Facade pattern](./Facade_pattern), [Flyweight pattern](./Flyweight_pattern), [Proxy pattern](./Proxy_pattern)
- *[Behavioral patterns](./Behavioral_pattern)* (11): [Chain-of-responsibility pattern](./Chain-of-responsibility_pattern), [Command pattern](./Command_pattern), [Interpreter pattern](./Interpreter_pattern), [Iterator pattern](./Iterator_pattern), [Mediator pattern](./Mediator_pattern), [Memento pattern](./Memento_pattern), [Observer pattern](./Observer_pattern), [State pattern](./State_pattern), [Strategy pattern](./Strategy_pattern), [Template method pattern](./Template_method_pattern), [Visitor pattern](./Visitor_pattern)

 

### Object-orientation and databases

 Main articles: [Object-relational impedance mismatch](./Object-relational_impedance_mismatch), [Object-relational mapping](./Object-relational_mapping), and [Object database](./Object_database) 

Both OOP and [relational database management systems](./Relational_database_management_systems) (RDBMSs) are widely used in software today. However, [relational databases](./Relational_database) don't store objects directly, which creates a challenge when using them together. This issue is called [object-relational impedance mismatch](./Object-relational_impedance_mismatch).

 

To solve this problem, developers use different methods, but none of them are perfect.[[53]](./Object-oriented_programming#cite_note-RDMDBobjectmis-53) One of the most common solutions is [object-relational mapping](./Object-relational_mapping) (ORM), which helps connect object-oriented programs to relational databases. Examples of ORM tools include [Visual FoxPro](./Visual_FoxPro), [Java Data Objects](./Java_Data_Objects), and [Ruby on Rails](./Ruby_on_Rails) ActiveRecord.

 

Some databases, called [object databases](./Object_database), are designed to work with OOP. However, they have not been as popular or successful as relational databases.

 

Date and Darwen have proposed a theoretical foundation that uses OOP as a kind of customizable [type system](./Data_type) to support RDBMSs, but it forbids objects containing pointers to other objects.[[54]](./Object-oriented_programming#cite_note-ThirdManifesto-54)

 

### Responsibility- vs. data-driven design

 

In [responsibility-driven design](./Responsibility-driven_design), classes are built around what they need to do and the information they share, in the form of a contract. This is different from [data-driven design](./Data-driven_programming), where classes are built based on the data they need to store. According to Wirfs-Brock and Wilkerson, the originators of responsibility-driven design, responsibility-driven design is the better approach.[[55]](./Object-oriented_programming#cite_note-Wirfs-Brock1989-55)

 

### SOLID and GRASP guidelines

 

[SOLID](./SOLID) is a set of five rules for designing good software, created by Michael Feathers:

 
- [Single responsibility principle](./Single_responsibility_principle): A class should have only one reason to change.
- [Open/closed principle](./Open/closed_principle): Software entities should be open for extension, but closed for modification.
- [Liskov substitution principle](./Liskov_substitution_principle): Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.
- [Interface segregation principle](./Interface_segregation_principle): Clients should not be forced to depend upon interfaces that they do not use.
- [Dependency inversion principle](./Dependency_inversion_principle): Depend upon abstractions, not concretes.

 

[GRASP](./GRASP_(object-oriented_design)) (General Responsibility Assignment Software Patterns) is another set of software design rules, created by [Craig Larman](./Craig_Larman), that helps developers assign responsibilities to different parts of a program:[[56]](./Object-oriented_programming#cite_note-56)

 
- Creator Principle: allows classes create objects they closely use.
- Information Expert Principle: assigns tasks to classes with the needed information.
- Low Coupling Principle: reduces class dependencies to improve flexibility and maintainability.
- High Cohesion Principle: designing classes with a single, focused responsibility.
- Controller Principle: assigns system operations to separate classes that manage flow and interactions.
- Polymorphism: allows different classes to be used through a common interface, promoting flexibility and reuse.
- Pure Fabrication Principle: create helper classes to improve design, boost cohesion, and reduce coupling.

 

## Formal semantics

 

Researchers have tried to formally define the [semantics](./Semantics_(computer_science)) of OOP. [Inheritance](./Inheritance_(object-oriented_programming)) presents difficulties, particularly with the interactions between open recursion and encapsulated state. Researchers have used [recursive types](./Recursive_type) and [co-algebraic data types](./F-Coalgebra) to incorporate essential features of OOP.[[57]](./Object-oriented_programming#cite_note-poll97-57) Abadi and Cardelli defined several extensions of [System F<:](./System_F-sub) that deal with mutable objects, allowing both [subtype polymorphism](./Subtype_polymorphism) and [parametric polymorphism](./Parametric_polymorphism) (generics), and were able to formally model many OOP concepts and constructs.[[58]](./Object-oriented_programming#cite_note-AbadiCardelli-58) Although far from trivial, static analysis of object-oriented programming languages such as Java is a mature field,[[59]](./Object-oriented_programming#cite_note-59) with several commercial tools.[[60]](./Object-oriented_programming#cite_note-60)

 

## Popularity and reception

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f8/Tiobeindex.png/500px-Tiobeindex.png)](./File:Tiobeindex.png)The [TIOBE](./TIOBE_index) programming language popularity index graph from 2002 to 2023. In the 2000s the object-oriented [Java](./Java_(programming_language)) (orange) and the [procedural](./Procedural_programming) [C](./C_(programming_language)) (dark blue) competed for the top position. 

Many popular programming languages, like C++, Java, and Python, use OOP. In the past, OOP was widely accepted,[[61]](./Object-oriented_programming#cite_note-61) but recently, some programmers have criticized it and prefer functional programming instead.[[62]](./Object-oriented_programming#cite_note-62) A study by Potok et al. found no major difference in productivity between OOP and procedural programming.[[63]](./Object-oriented_programming#cite_note-63)

 

Some believe that OOP places too much focus on using objects rather than on [algorithms](./Algorithm) and [data structures](./Data_structure).[[64]](./Object-oriented_programming#cite_note-stepanov-64)[[65]](./Object-oriented_programming#cite_note-hickey-65) For example, programmer [Rob Pike](./Rob_Pike) pointed out that OOP can make programmers think more about type hierarchy than composition.[[66]](./Object-oriented_programming#cite_note-RobPike-66) He has called OOP "the [Roman numerals](./Roman_numerals) of computing".[[67]](./Object-oriented_programming#cite_note-67) [Rich Hickey](./Rich_Hickey), creator of [Clojure](./Clojure), described OOP as overly simplistic, especially when it comes to representing real-world things that change over time.[[65]](./Object-oriented_programming#cite_note-hickey-65) [Alexander Stepanov](./Alexander_Stepanov) said that OOP tries to fit everything into a single type, which can be limiting. He argued that sometimes we need multisorted algebras: families of interfaces that span multiple types, such as in [generic programming](./Generic_programming). Stepanov also said that calling everything an "object" doesn't add much understanding.[[64]](./Object-oriented_programming#cite_note-stepanov-64)

 

OOP was created to make code easier to [reuse](./Code_reuse) and [maintain](./Software_maintenance).[[68]](./Object-oriented_programming#cite_note-realisticcodereuse-68) However, it was not designed to clearly show the flow of a program's instructions. That was left to the compiler. As computers began using more parallel processing and multiple [threads](./Thread_(computer_science)), it became more important to understand and control how instructions flow. This is difficult to do with OOP.[[69]](./Object-oriented_programming#cite_note-flaws-69)[[70]](./Object-oriented_programming#cite_note-multithreadingisaverb-70)[[71]](./Object-oriented_programming#cite_note-multicore-71)[[72]](./Object-oriented_programming#cite_note-72)

 

[Paul Graham](./Paul_Graham_(computer_programmer)) believes big companies like OOP because it helps manage large teams of average programmers. He argues that OOP adds structure, making it harder for one person to make serious mistakes, but at the same time restrains smart programmers.[[73]](./Object-oriented_programming#cite_note-graham-73) [Eric S. Raymond](./Eric_S._Raymond), a [Unix](./Unix) programmer and [open-source software](./Open-source_software) advocate, argues that OOP is not the best way to write programs.[[36]](./Object-oriented_programming#cite_note-Eric_S._Raymond_2003-36)

 

Richard Feldman says that, while OOP features helped some languages stay organized, their popularity comes from other reasons.[[74]](./Object-oriented_programming#cite_note-74) Lawrence Krubner argues that OOP doesn't offer special advantages compared to other styles, like functional programming, and can complicate coding.[[75]](./Object-oriented_programming#cite_note-lawrence-75) [Luca Cardelli](./Luca_Cardelli) says that OOP is slower and takes longer to compile than procedural programming.[[34]](./Object-oriented_programming#cite_note-badprop-34)

 

## See also

 
- [![icon](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Octicons-terminal.svg/40px-Octicons-terminal.svg.png)](./File:Octicons-terminal.svg)[Computer programming portal](./Portal:Computer_programming)

 
- [CADES](./CADES)
- [Common Object Request Broker Architecture](./Common_Object_Request_Broker_Architecture) (CORBA)
- [Comparison of programming languages (object-oriented programming)](./Comparison_of_programming_languages_(object-oriented_programming))
- [Component-based software engineering](./Component-based_software_engineering)
- [Distributed object](./Distributed_object)
- [Distributed Component Object Model](./Distributed_Component_Object_Model)
- [Interface description language](./Interface_description_language)
- [IDEF4](./IDEF4)
- [Jeroo](./Jeroo)
- [List of object-oriented programming languages](./List_of_object-oriented_programming_languages)
- [Object association](./Object_association)
- [Object-oriented analysis and design](./Object-oriented_analysis_and_design)
- [Object-oriented modeling](./Object-oriented_modeling)
- [Object-oriented ontology](./Object-oriented_ontology)
- [UML](./UML)

 

## References

  
1. [1](./Object-oriented_programming#cite_ref-alanKayOnOO_1-0) [2](./Object-oriented_programming#cite_ref-alanKayOnOO_1-1) [3](./Object-oriented_programming#cite_ref-alanKayOnOO_1-2) [4](./Object-oriented_programming#cite_ref-alanKayOnOO_1-3) Kay, Dr. Alan (23 July 2003). ["Dr. Alan Kay on the Meaning of "Object-Oriented Programming""](https://www.purl.org/stefan_ram/pub/doc_kay_oop_en). [Archived](https://web.archive.org/web/20250304003920/http://userpage.fu-berlin.de/~ram/pub/pub_jf47ht81Ht/doc_kay_oop_en) from the original on 4 March 2025. Retrieved 11 February 2010.
2. [↑](./Object-oriented_programming#cite_ref-2) Kindler, E.; Krivy, I. (2011). "Object-Oriented Simulation of systems with sophisticated control". *International Journal of General Systems*. **40** (3): 313–343. [doi](./Doi_(identifier)):[10.1080/03081079.2010.539975](https://doi.org/10.1080%2F03081079.2010.539975).
3. [↑](./Object-oriented_programming#cite_ref-3) Lewis, John; Loftus, William (2008). "1.6: Object-Oriented Programming". *Java Software Solutions*. Foundations of Programming Design (6th ed.). Pearson Education Inc. [ISBN](./ISBN_(identifier)) [978-0-321-53205-3](./Special:BookSources/978-0-321-53205-3).
4. [↑](./Object-oriented_programming#cite_ref-FOOTNOTEBloch2018xi–xiiForeword_4-0) [Bloch 2018](./Object-oriented_programming#CITEREFBloch2018), pp. xi–xii, Foreword.
5. [↑](./Object-oriented_programming#cite_ref-5) [McCarthy, J.](./John_McCarthy_(computer_scientist)); Brayton, R.; Edwards, D.; [Fox, P.](./Phyllis_Fox); [Hodes, L.](./Louis_Hodes); [Luckham, D.](./David_Luckham); Maling, K.; [Park, D.](./David_Park_(computer_scientist)); [Russell, S.](./Steve_Russell_(computer_scientist)) (March 1969). ["LISP I Programmers Manual"](https://web.archive.org/web/20100717111134/http://history.siam.org/sup/Fox_1960_LISP.pdf) (PDF). *Computation Center and Research Laboratory of Electronics*. [Boston](./Boston), [Massachusetts](./Massachusetts): Artificial Intelligence Group, [M.I.T. Computation Center](./M.I.T._Computation_Center) and Research Laboratory: 88f. Archived from [the original](http://history.siam.org/sup/Fox_1960_LISP.pdf) (PDF) on 17 July 2010. In the local M.I.T. patois, association lists [of atomic symbols] are also referred to as "property lists", and atomic symbols are sometimes called "objects".
6. [↑](./Object-oriented_programming#cite_ref-6) [McCarthy, John](./John_McCarthy_(computer_scientist)); Abrahams, Paul W.; Edwards, Daniel J.; Hart, Swapnil D.; Levin, Michael I. (1962). [*LISP 1.5 Programmer's Manual*](https://archive.org/details/lisp15programmer00john/page/105). [MIT Press](./MIT_Press). p. [105](https://archive.org/details/lisp15programmer00john/page/105). [ISBN](./ISBN_(identifier)) [978-0-262-13011-0](./Special:BookSources/978-0-262-13011-0). Object – a synonym for atomic symbol `{{cite book}}`: ISBN / Date incompatibility ([help](./Help:CS1_errors#invalid_isbn_date))
7. [↑](./Object-oriented_programming#cite_ref-7) [Ivan E. Sutherland](./Ivan_E._Sutherland) (May 1963). *Sketchpad: a man-machine graphical communication system*. AFIPS '63 (Spring): Proceedings of the May 21–23, 1963 Spring Joint Computer Conference. AFIPS Press. pp. 329–346. [doi](./Doi_(identifier)):[10.1145/1461551.1461591](https://doi.org/10.1145%2F1461551.1461591). 
8. [1](./Object-oriented_programming#cite_ref-simuladev_8-0) [2](./Object-oriented_programming#cite_ref-simuladev_8-1) [Nygaard, Kristen](./Kristen_Nygaard); [Dahl, Ole-Johan](./Ole-Johan_Dahl) (1 August 1978). ["The development of the SIMULA languages"](https://doi.org/10.1145%2F960118.808391). *[ACM SIGPLAN Notices](./ACM_SIGPLAN_Notices)*. **13** (8): 245–272. [doi](./Doi_(identifier)):[10.1145/960118.808391](https://doi.org/10.1145%2F960118.808391). 
9. [↑](./Object-oriented_programming#cite_ref-9)  Ross, Doug. ["The first software engineering language"](http://www.csail.mit.edu/timeline/timeline.php?query=event&id=19). *LCS/AI Lab Timeline*. MIT Computer Science and Artificial Intelligence Laboratory. [Archived](https://web.archive.org/web/20110412161429/http://www.csail.mit.edu/timeline/timeline.php?query=event&id=19) from the original on 12 April 2011. Retrieved 13 May 2010. 
10. [1](./Object-oriented_programming#cite_ref-auto_10-0) [2](./Object-oriented_programming#cite_ref-auto_10-1) Holmevik, Jan Rune (Winter 1994). ["Compiling Simula: A historical study of technological genesis"](https://web.archive.org/web/20170830065454/http://www.idi.ntnu.no/grupper/su/publ/simula/holmevik-simula-ieeeannals94.pdf) (PDF). *[IEEE Annals of the History of Computing](./IEEE_Annals_of_the_History_of_Computing)*. **16** (4): 25–37. [doi](./Doi_(identifier)):[10.1109/85.329756](https://doi.org/10.1109%2F85.329756). [S2CID](./S2CID_(identifier)) [18148999](https://api.semanticscholar.org/CorpusID:18148999). Archived from [the original](http://www.idi.ntnu.no/grupper/su/publ/simula/holmevik-simula-ieeeannals94.pdf) (PDF) on 30 August 2017. Retrieved 3 March 2018.
11. [↑](./Object-oriented_programming#cite_ref-11) Madsen, Ole Lehrman. ["Kristen Nygaard"](https://web.archive.org/web/20250201220517/https://amturing.acm.org/award_winners/nygaard_5916220.cfm). *A.M. Turing Award Laureates*. Archived from [the original](https://amturing.acm.org/award_winners/nygaard_5916220.cfm) on 1 February 2025. Retrieved 4 February 2025.
12. [↑](./Object-oriented_programming#cite_ref-12) Butcher, Paul (30 June 2014). [*Seven Concurrency Models in Seven Weeks: When Threads Unravel*](https://books.google.com/books?id=Xg9QDwAAQBAJ&pg=PT204). Pragmatic Bookshelf. p. 204. [ISBN](./ISBN_(identifier)) [978-1-68050-466-8](./Special:BookSources/978-1-68050-466-8).
13. [↑](./Object-oriented_programming#cite_ref-13) Jones, Anita K.; Liskov, Barbara H. (April 1976). [*An Access Control Facility for Programming Languages*](https://web.archive.org/web/20260226005404/https://csg.csail.mit.edu/CSGArchives/memos/Memo-137.pdf) (PDF) (Technical report). MIT. CSG Memo 137. Archived from [the original](https://csg.csail.mit.edu/CSGArchives/memos/Memo-137.pdf) (PDF) on 26 February 2026.
14. [1](./Object-oriented_programming#cite_ref-Bertrand_Meyer_2009_329_14-0) [2](./Object-oriented_programming#cite_ref-Bertrand_Meyer_2009_329_14-1) Meyer, Bertrand (2009). *Touch of Class: Learning to Program Well with Objects and Contracts*. Springer Science & Business Media. p. 329. [Bibcode](./Bibcode_(identifier)):[2009tclp.book.....M](https://ui.adsabs.harvard.edu/abs/2009tclp.book.....M). [ISBN](./ISBN_(identifier)) [978-3-540-92144-8](./Special:BookSources/978-3-540-92144-8).
15. [↑](./Object-oriented_programming#cite_ref-15) [Kay, Alan](./Alan_Kay) (March 1993). ["The early history of Smalltalk"](https://doi.org/10.1145%2F155360.155364). *[ACM SIGPLAN Notices](./ACM_SIGPLAN_Notices)*. **28** (3): 69–95. [doi](./Doi_(identifier)):[10.1145/155360.155364](https://doi.org/10.1145%2F155360.155364). 
16. [↑](./Object-oriented_programming#cite_ref-16) Borning, Alan Hamilton (1979). [Thinglab: a constraint-oriented simulation laboratory](https://constraints.cs.washington.edu/ui/thinglab-tr.pdf) (PDF) (Report). Stanford University.
17. [↑](./Object-oriented_programming#cite_ref-17) [Moon, David A.](./David_A._Moon) (June 1986). ["Object-Oriented Programming with Flavors"](https://www.cs.tufts.edu/comp/150FP/archive/david-moon/flavors.pdf) (PDF). *Conference proceedings on Object-oriented Programming Systems Languages and Applications*. [OOPSLA](./OOPSLA) '86. pp. 1–8. [doi](./Doi_(identifier)):[10.1145/28697.28698](https://doi.org/10.1145%2F28697.28698). [ISBN](./ISBN_(identifier)) [978-0-89791-204-4](./Special:BookSources/978-0-89791-204-4). [S2CID](./S2CID_(identifier)) [17150741](https://api.semanticscholar.org/CorpusID:17150741). Retrieved 17 March 2022.
18. [↑](./Object-oriented_programming#cite_ref-18) Hsu, Hansen (17 December 2020). ["Introducing the Smalltalk Zoo"](https://computerhistory.org/blog/introducing-the-smalltalk-zoo-48-years-of-smalltalk-history-at-chm/). *CHM*. Retrieved 27 May 2021.`{{cite news}}`:  CS1 maint: url-status ([link](./Category:CS1_maint:_url-status))
19. [↑](./Object-oriented_programming#cite_ref-19) Bobrow, D. G.; Stefik, M. J (1982). [*LOOPS: data and object oriented Programming for Interlisp*](https://www.markstefik.com/wp-content/uploads/2011/04/1982-Bobrow-Stefik-Data-Object-Pgming.pdf) (PDF). European AI Conference.
20. [↑](./Object-oriented_programming#cite_ref-FOOTNOTEMeyer1997_20-0) [Meyer 1997](./Object-oriented_programming#CITEREFMeyer1997).
21. [↑](./Object-oriented_programming#cite_ref-21) 1995 (June) [Visual FoxPro](./Visual_FoxPro) 3.0, FoxPro evolves from a procedural language to an object-oriented language. Visual FoxPro 3.0 introduces a database container, seamless client/server capabilities, support for ActiveX technologies, and OLE Automation and null support. [Summary of Fox releases](http://www.foxprohistory.org/foxprotimeline.htm#summary_of_fox_releases)
22. [↑](./Object-oriented_programming#cite_ref-22) 1995 Reviewers Guide to Visual FoxPro 3.0: [DFpug.de](http://www.dfpug.de/loseblattsammlung/migration/whitepapers/vfp_rg.htm)
23. [↑](./Object-oriented_programming#cite_ref-23) Khurana, Rohit (1 November 2009). [*Object Oriented Programming with C++, 1E*](https://books.google.com/books?id=MHmqfSBTXsAC&pg=PA16). Vikas Publishing House Pvt Limited. [ISBN](./ISBN_(identifier)) [978-81-259-2532-3](./Special:BookSources/978-81-259-2532-3).
24. [↑](./Object-oriented_programming#cite_ref-ArmstrongQuarks_24-0) Deborah J. Armstrong. *The Quarks of Object-Oriented Development*. A survey of nearly 40 years of computing literature identified several fundamental concepts found in the large majority of definitions of OOP, in descending order of popularity: Inheritance, Object, Class, Encapsulation, Method, Message Passing, Polymorphism, and Abstraction.
25. [↑](./Object-oriented_programming#cite_ref-25) [John C. Mitchell](./John_C._Mitchell), *Concepts in programming languages*, Cambridge University Press, 2003, [ISBN](./ISBN_(identifier)) [0-521-78098-5](./Special:BookSources/0-521-78098-5), p.278. Lists: Dynamic dispatch, abstraction, subtype polymorphism, and inheritance.
26. [↑](./Object-oriented_programming#cite_ref-26) Michael Lee Scott, *Programming language pragmatics*, Edition 2, Morgan Kaufmann, 2006, [ISBN](./ISBN_(identifier)) [0-12-633951-1](./Special:BookSources/0-12-633951-1), p. 470. Lists encapsulation, inheritance, and dynamic dispatch.
27. [↑](./Object-oriented_programming#cite_ref-pierce_27-0) Pierce, Benjamin (2002). [*Types and Programming Languages*](./Types_and_Programming_Languages). MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-16209-8](./Special:BookSources/978-0-262-16209-8)., section 18.1 "What is Object-Oriented Programming?" Lists: Dynamic dispatch, encapsulation or multi-methods (multiple dispatch), subtype polymorphism, inheritance or delegation, open recursion ("this"/"self")
28. [↑](./Object-oriented_programming#cite_ref-DatePage650_28-0) C. J. Date, Introduction to Database Systems, 6th-ed., Page 650
29. [↑](./Object-oriented_programming#cite_ref-29) McDonough, James E. (2017). "Encapsulation". *Object-Oriented Design with ABAP: A Practical Approach*. [Apress](./Apress). [doi](./Doi_(identifier)):[10.1007/978-1-4842-2838-8](https://doi.org/10.1007%2F978-1-4842-2838-8). [ISBN](./ISBN_(identifier)) [978-1-4842-2837-1](./Special:BookSources/978-1-4842-2837-1) – via [O'Reilly](./O'Reilly_Media).
30. [↑](./Object-oriented_programming#cite_ref-FOOTNOTEBloch201873–77Chapter_§4_Item15_Minimize_the_accessibility_of_classes_and_members_30-0) [Bloch 2018](./Object-oriented_programming#CITEREFBloch2018), pp. 73–77, Chapter §4 Item15 Minimize the accessibility of classes and members.
31. [↑](./Object-oriented_programming#cite_ref-31) ["What is Object Oriented Programming (OOP) In Simple Words? – Software Geek Bytes"](https://web.archive.org/web/20230117082128/https://softwaregeekbytes.com/object-oriented-programming-simple-words/). 5 January 2023. Archived from [the original](https://softwaregeekbytes.com/object-oriented-programming-simple-words/) on 17 January 2023. Retrieved 17 January 2023.
32. [↑](./Object-oriented_programming#cite_ref-Luca1985_32-0) Cardelli, Luca; Wegner, Peter (10 December 1985). ["On understanding types, data abstraction, and polymorphism"](https://doi.org/10.1145%2F6041.6042). *ACM Computing Surveys*. **17** (4): 471–523. [doi](./Doi_(identifier)):[10.1145/6041.6042](https://doi.org/10.1145%2F6041.6042). [ISSN](./ISSN_(identifier)) [0360-0300](https://search.worldcat.org/issn/0360-0300).
33. [↑](./Object-oriented_programming#cite_ref-33) Jacobsen, Ivar; Magnus Christerson; Patrik Jonsson; Gunnar Overgaard (1992). [*Object Oriented Software Engineering*](https://archive.org/details/objectorientedso00jaco/page/43). Addison-Wesley ACM Press. pp. [43–69](https://archive.org/details/objectorientedso00jaco/page/43). [ISBN](./ISBN_(identifier)) [978-0-201-54435-0](./Special:BookSources/978-0-201-54435-0).
34. [1](./Object-oriented_programming#cite_ref-badprop_34-0) [2](./Object-oriented_programming#cite_ref-badprop_34-1) [3](./Object-oriented_programming#cite_ref-badprop_34-2) [Cardelli, Luca](./Luca_Cardelli) (1996). ["Bad Engineering Properties of Object-Oriented Languages"](https://web.archive.org/web/20100510065853/http://lucacardelli.name/Papers/BadPropertiesOfOO.html). *ACM Comput. Surv*. **28** (4es): 150–es. [doi](./Doi_(identifier)):[10.1145/242224.242415](https://doi.org/10.1145%2F242224.242415). [ISSN](./ISSN_(identifier)) [0360-0300](https://search.worldcat.org/issn/0360-0300). [S2CID](./S2CID_(identifier)) [12105785](https://api.semanticscholar.org/CorpusID:12105785). Archived from [the original](http://lucacardelli.name/Papers/BadPropertiesOfOO.html) on 10 May 2010. Retrieved 21 April 2010.
35. [1](./Object-oriented_programming#cite_ref-armstrongjoe_35-0) [2](./Object-oriented_programming#cite_ref-armstrongjoe_35-1) [Armstrong, Joe](./Joe_Armstrong_(programmer)). Seibel, Peter (ed.). [*Coders at Work: Reflections on the Craft of Programming*](https://web.archive.org/web/20100305165150/http://www.codersatwork.com/). Codersatwork.com. Archived from [the original](http://www.codersatwork.com/) on 5 March 2010. Retrieved 13 November 2009.
36. [1](./Object-oriented_programming#cite_ref-Eric_S._Raymond_2003_36-0) [2](./Object-oriented_programming#cite_ref-Eric_S._Raymond_2003_36-1) [3](./Object-oriented_programming#cite_ref-Eric_S._Raymond_2003_36-2) Raymond, Eric S. (2003). ["The Art of Unix Programming: Unix and Object-Oriented Languages"](https://web.archive.org/web/20140915191746/http://www.catb.org/esr/writings/taoup/html/unix_and_oo.html). Archived from [the original](http://www.catb.org/esr/writings/taoup/html/unix_and_oo.html) on 15 September 2014. Retrieved 6 August 2014.
37. [↑](./Object-oriented_programming#cite_ref-37) Brodie, Leo (1984). [*Thinking Forth*](https://thinking-forth.sourceforge.net/thinking-forth-ans.pdf) (PDF). pp. 92–93. Retrieved 4 May 2018.
38. [↑](./Object-oriented_programming#cite_ref-38) Hunt, Andrew. ["Don't Repeat Yourself"](https://web.archive.org/web/20180505021505/http://wiki.c2.com/?DontRepeatYourself). *Category Extreme Programming*. Archived from [the original](http://wiki.c2.com/?DontRepeatYourself) on 5 May 2018. Retrieved 4 May 2018.
39. [↑](./Object-oriented_programming#cite_ref-FOOTNOTEBloch201819Chapter_§2_Item_4_Enforce_noninstantiability_with_a_private_constructor_39-0) [Bloch 2018](./Object-oriented_programming#CITEREFBloch2018), p. 19, Chapter §2 Item 4 Enforce noninstantiability with a private constructor.
40. [↑](./Object-oriented_programming#cite_ref-40) Dony, C; Malenfant, J; Bardon, D (1999). ["Classifying prototype-based programming languages"](https://www.lirmm.fr/~dony/postscript/proto-book.pdf) (PDF). *Prototype-based programming: concepts, languages and applications*. Singapore Berlin Heidelberg: Springer. [ISBN](./ISBN_(identifier)) [9789814021258](./Special:BookSources/9789814021258).
41. [↑](./Object-oriented_programming#cite_ref-41) ["Is Go an object-oriented language?"](https://golang.org/doc/faq#Is_Go_an_object-oriented_language). [Archived](https://web.archive.org/web/20190413152706/https://golang.org/doc/faq#Is_Go_an_object-oriented_language) from the original on 13 April 2019. Retrieved 13 April 2019. Although Go has types and methods and allows an object-oriented style of programming, there is no type hierarchy.
42. [↑](./Object-oriented_programming#cite_ref-42) [Stroustrup, Bjarne](./Bjarne_Stroustrup) (2015). [*Object-Oriented Programming without Inheritance (Invited Talk)*](https://www.youtube.com/watch?v=xcpSLRpOMJM). 29th European Conference on Object-Oriented Programming (ECOOP 2015). 1:34. [doi](./Doi_(identifier)):[10.4230/LIPIcs.ECOOP.2015.1](https://doi.org/10.4230%2FLIPIcs.ECOOP.2015.1).
43. [↑](./Object-oriented_programming#cite_ref-43) Pike, Rob (14 November 2012). ["A few years ago I saw this page"](https://web.archive.org/web/20180814173134/http://plus.google.com/+RobPikeTheHuman/posts/hoJdanihKwb). Archived from [the original](https://plus.google.com/+RobPikeTheHuman/posts/hoJdanihKwb) on 14 August 2018. Retrieved 1 October 2016.
44. [↑](./Object-oriented_programming#cite_ref-44) Naik, Mayur; Kumar, Rajeev (March 2000). "Efficient message dispatch in object-oriented systems". *ACM SIGPLAN Notices*. **35** (3): 49–58. [doi](./Doi_(identifier)):[10.1145/351159.351174](https://doi.org/10.1145%2F351159.351174).
45. [↑](./Object-oriented_programming#cite_ref-45) [Stroustrup, Bjarne](./Bjarne_Stroustrup) (19 February 2007). ["Bjarne Stroustrup's C++ Glossary"](https://www.stroustrup.com/glossary.html#Gpolymorphism). *www.stroustrup.com*. [Archived](https://web.archive.org/web/20120720203948/https://www.stroustrup.com/glossary.html#Gpolymorphism) from the original on 20 July 2012. Retrieved 9 June 2011. polymorphism – providing a single interface to entities of different types.
46. [↑](./Object-oriented_programming#cite_ref-46) [Booch, Grady](./Grady_Booch) (1986). [*Software Engineering with Ada*](https://en.wikiquote.org/wiki/Grady_Booch). Addison Wesley. p. 220. [ISBN](./ISBN_(identifier)) [978-0-8053-0608-8](./Special:BookSources/978-0-8053-0608-8). Perhaps the greatest strength of an object-oriented approach to development is that it offers a mechanism that captures a model of the real world.
47. [↑](./Object-oriented_programming#cite_ref-47) [Wirth, Niklaus](./Niklaus_Wirth) (23 January 2006). ["Good ideas, through the looking glass"](https://web.archive.org/web/20161012215755/https://pdfs.semanticscholar.org/10bd/dc49b85196aaa6715dd46843d9dcffa38358.pdf) (PDF). *[IEEE Computer](./IEEE_Computer)*. Cover Feature. **39** (1): 28–39. [Bibcode](./Bibcode_(identifier)):[2006Compr..39a..28W](https://ui.adsabs.harvard.edu/abs/2006Compr..39a..28W). [doi](./Doi_(identifier)):[10.1109/MC.2006.20](https://doi.org/10.1109%2FMC.2006.20). [S2CID](./S2CID_(identifier)) [6582369](https://api.semanticscholar.org/CorpusID:6582369). Archived from [the original](https://pdfs.semanticscholar.org/10bd/dc49b85196aaa6715dd46843d9dcffa38358.pdf) (PDF) on 12 October 2016.
48. [↑](./Object-oriented_programming#cite_ref-48) ["Uncle Bob SOLID principles"](https://www.youtube.com/watch?v=zHiWqnTWsn4). *[YouTube](./YouTube)*. 2 August 2018.
49. [↑](./Object-oriented_programming#cite_ref-FOOTNOTEMeyer1997230_49-0) [Meyer 1997](./Object-oriented_programming#CITEREFMeyer1997), p. 230.
50. [↑](./Object-oriented_programming#cite_ref-executioniKoN_50-0) Yegge, Steve (30 March 2006). ["Execution in the Kingdom of Nouns"](https://steve-yegge.blogspot.com/2006/03/execution-in-kingdom-of-nouns.html). steve-yegge.blogspot.com. Retrieved 3 July 2010.
51. [↑](./Object-oriented_programming#cite_ref-executioniKoN2_51-0) Boronczyk, Timothy (11 June 2009). ["What's Wrong with OOP"](https://zaemis.blogspot.com/2009/06/whats-wrong-with-oop.html). zaemis.blogspot.com. Retrieved 3 July 2010.
52. [↑](./Object-oriented_programming#cite_ref-R.C.Martin_52-0) [Martin, Robert C.](./Robert_Cecil_Martin) ["Design Principles and Design Patterns"](https://web.archive.org/web/20150906155800/http://www.objectmentor.com/resources/articles/Principles_and_Patterns.pdf) (PDF). Archived from [the original](http://www.objectmentor.com/resources/articles/Principles_and_Patterns.pdf) (PDF) on 6 September 2015. Retrieved 28 April 2017.
53. [↑](./Object-oriented_programming#cite_ref-RDMDBobjectmis_53-0) Neward, Ted (26 June 2006). ["The Vietnam of Computer Science"](https://web.archive.org/web/20060704030226/http://blogs.tedneward.com/2006/06/26/The+Vietnam+Of+Computer+Science.aspx). Interoperability Happens. Archived from [the original](http://blogs.tedneward.com/2006/06/26/The+Vietnam+Of+Computer+Science.aspx) on 4 July 2006. Retrieved 2 June 2010.
54. [↑](./Object-oriented_programming#cite_ref-ThirdManifesto_54-0) C. J. Date, Hugh Darwen. *Foundation for Future Database Systems: The Third Manifesto* (2nd Edition)
55. [↑](./Object-oriented_programming#cite_ref-Wirfs-Brock1989_55-0) Wirfs-Brock, Rebecca; Wilkerson, Brian (1989). ["Object-Oriented Design: A Responsibility-Driven Approach"](https://doi.org/10.1145%2F74878.74885). *ACM SIGPLAN Notices*. **24** (10): 74. [doi](./Doi_(identifier)):[10.1145/74878.74885](https://doi.org/10.1145%2F74878.74885).
56. [↑](./Object-oriented_programming#cite_ref-56) Karsh, Patrick (19 July 2023). ["GRASP Principles: Object-Oriented Design Patterns"](https://patrickkarsh.medium.com/object-oriented-design-with-grasp-principles-8049fa63e52). *Medium*. Retrieved 30 March 2025.
57. [↑](./Object-oriented_programming#cite_ref-poll97_57-0) Poll, Erik. ["Subtyping and Inheritance for Categorical Datatypes"](https://www.cs.ru.nl/E.Poll/papers/kyoto97.pdf) (PDF). Retrieved 5 June 2011.
58. [↑](./Object-oriented_programming#cite_ref-AbadiCardelli_58-0) [Abadi, Martin](./Martin_Abadi); Cardelli, Luca (1996). [*A Theory of Objects*](http://portal.acm.org/citation.cfm?id=547964&dl=ACM&coll=portal). Springer-Verlag New York, Inc. [ISBN](./ISBN_(identifier)) [978-0-387-94775-4](./Special:BookSources/978-0-387-94775-4). Retrieved 21 April 2010.
59. [↑](./Object-oriented_programming#cite_ref-59) Tan, Tian; Li, Yue (12 July 2023). *Tai-e: A Developer-Friendly Static Analysis Framework for Java by Harnessing the Good Designs of Classics*. ISSTA 2023. pp. 1093–1105. [doi](./Doi_(identifier)):[10.1145/3597926.3598120](https://doi.org/10.1145%2F3597926.3598120).
60. [↑](./Object-oriented_programming#cite_ref-60) Bhutani, Vikram; Toosi, Farshad Ghassemi; Buckley, Jim (1 June 2024). "Analysing the Analysers: An Investigation of Source Code Analysis Tools". *Applied Computer Systems*. **29** (1): 98–111. [doi](./Doi_(identifier)):[10.2478/acss-2024-0013](https://doi.org/10.2478%2Facss-2024-0013).
61. [↑](./Object-oriented_programming#cite_ref-61) Brucker, Achim D.; Wolff, Burkhart (2008). "Extensible Universes for Object-Oriented Data Models". *ECOOP 2008 – Object-Oriented Programming*. Lecture Notes in Computer Science. Vol. 5142. pp. 438–462. [doi](./Doi_(identifier)):[10.1007/978-3-540-70592-5_19](https://doi.org/10.1007%2F978-3-540-70592-5_19). [ISBN](./ISBN_(identifier)) [978-3-540-70591-8](./Special:BookSources/978-3-540-70591-8). object-oriented programming is a widely accepted programming paradigm
62. [↑](./Object-oriented_programming#cite_ref-62) Cassel, David (21 August 2019). ["Why Are So Many Developers Hating on Object-Oriented Programming?"](https://thenewstack.io/why-are-so-many-developers-hating-on-object-oriented-programming/). *The New Stack*.
63. [↑](./Object-oriented_programming#cite_ref-63) Potok, Thomas; Vouk, Mladen; Rindos, Andy (1999). ["Productivity Analysis of Object-Oriented Software Developed in a Commercial Environment"](https://www.csm.ornl.gov/~v8q/Homepage/Papers%20Old/spetep-%20printable.pdf) (PDF). *Software: Practice and Experience*. **29** (10): 833–847. [doi](./Doi_(identifier)):[10.1002/(SICI)1097-024X(199908)29:10<833::AID-SPE258>3.0.CO;2-P](https://doi.org/10.1002%2F%28SICI%291097-024X%28199908%2929%3A10%3C833%3A%3AAID-SPE258%3E3.0.CO%3B2-P). [S2CID](./S2CID_(identifier)) [57865731](https://api.semanticscholar.org/CorpusID:57865731). Retrieved 21 April 2010.
64. [1](./Object-oriented_programming#cite_ref-stepanov_64-0) [2](./Object-oriented_programming#cite_ref-stepanov_64-1) [Stepanov, Alexander](./Alexander_Stepanov) (2001–2008). ["STLport: An Interview with A. Stepanov"](http://www.stlport.org/resources/StepanovUSA.html). Retrieved 21 April 2010.
65. [1](./Object-oriented_programming#cite_ref-hickey_65-0) [2](./Object-oriented_programming#cite_ref-hickey_65-1) Hickey, Rich (November 2009). [*Are We There Yet? (keynote)*](https://www.infoq.com/presentations/Are-We-There-Yet-Rich-Hickey). JVM Languages Summit.
66. [↑](./Object-oriented_programming#cite_ref-RobPike_66-0) Pike, Rob (25 June 2012). ["Less is exponentially more"](https://commandcenter.blogspot.com/2012/06/less-is-exponentially-more.html). Retrieved 1 October 2016.
67. [↑](./Object-oriented_programming#cite_ref-67) [Pike, Rob](./Rob_Pike) (2 March 2004). ["[9fans] Re: Threads: Sewing badges of honor onto a Kernel"](https://groups.google.com/group/comp.os.plan9/msg/006fec195aeeff15). *comp.os.plan9* (Mailing list). Retrieved 17 November 2016.
68. [↑](./Object-oriented_programming#cite_ref-realisticcodereuse_68-0) Ambler, Scott (1 January 1998). ["A Realistic Look at Object-Oriented Reuse"](http://www.drdobbs.com/184415594). drdobbs.com. Retrieved 5 August 2025.
69. [↑](./Object-oriented_programming#cite_ref-flaws_69-0) Shelly, Asaf (22 August 2008). ["Flaws of Object Oriented Modeling"](http://software.intel.com/en-us/blogs/2008/08/22/flaws-of-object-oriented-modeling/). Intel Software Network. Retrieved 4 July 2010.
70. [↑](./Object-oriented_programming#cite_ref-multithreadingisaverb_70-0) James, Justin (1 October 2007). ["Multithreading is a verb not a noun"](https://web.archive.org/web/20071010105117/http://blogs.techrepublic.com.com/programming-and-development/?p=518). techrepublic.com. Archived from [the original](http://blogs.techrepublic.com.com/programming-and-development/?p=518) on 10 October 2007. Retrieved 4 July 2010.
71. [↑](./Object-oriented_programming#cite_ref-multicore_71-0) Shelly, Asaf (22 August 2008). ["HOW TO: Multicore Programming (Multiprocessing) Visual C++ Class Design Guidelines, Member Functions"](http://support.microsoft.com/?scid=kb%3Ben-us%3B558117). support.microsoft.com. Retrieved 4 July 2010.
72. [↑](./Object-oriented_programming#cite_ref-72) [Harper, Robert](./Robert_Harper_(computer_scientist)) (17 April 2011). ["Some thoughts on teaching FP"](https://web.archive.org/web/20111106043055/https://existentialtype.wordpress.com/2011/04/17/some-advice-on-teaching-fp/). Existential Type Blog. Archived from [the original](https://existentialtype.wordpress.com/2011/04/17/some-advice-on-teaching-fp/) on 6 November 2011. Retrieved 5 December 2011.
73. [↑](./Object-oriented_programming#cite_ref-graham_73-0) [Graham, Paul](./Paul_Graham_(computer_programmer)). ["Why ARC isn't especially Object-Oriented"](https://web.archive.org/web/20091124043505/https://www.paulgraham.com/noop.html). PaulGraham.com. Archived from [the original](https://www.paulgraham.com/noop.html) on 24 November 2009. Retrieved 13 November 2009.
74. [↑](./Object-oriented_programming#cite_ref-74) Feldman, Richard (30 September 2019). ["Why Isn't Functional Programming the Norm?"](https://web.archive.org/web/20220822023726/https://www.youtube.com/watch?v=QyJZzq0v7Z4&t=2069s). *[YouTube](./YouTube)*. Archived from [the original](https://www.youtube.com/watch?v=QyJZzq0v7Z4&t=2069s) on 22 August 2022.
75. [↑](./Object-oriented_programming#cite_ref-lawrence_75-0) Krubner, Lawrence. ["Object Oriented Programming is an expensive disaster which must end"](https://web.archive.org/web/20141014233854/http://www.smashcompany.com/technology/object-oriented-programming-is-an-expensive-disaster-which-must-end). smashcompany.com. Archived from [the original](http://www.smashcompany.com/technology/object-oriented-programming-is-an-expensive-disaster-which-must-end) on 14 October 2014. Retrieved 14 October 2014.

 

## Further reading

 
- [Abadi, Martin](./Martin_Abadi); [Luca Cardelli](./Luca_Cardelli) (1998). *A Theory of Objects*. [Springer Verlag](./Springer_Verlag). [ISBN](./ISBN_(identifier)) [978-0-387-94775-4](./Special:BookSources/978-0-387-94775-4).
- [Abelson, Harold](./Harold_Abelson); [Gerald Jay Sussman](./Gerald_Jay_Sussman) (1997). [*Structure and Interpretation of Computer Programs*](https://web.archive.org/web/20171226134539/http://mitpress.mit.edu/sicp/). [MIT Press](./MIT_Press). [ISBN](./ISBN_(identifier)) [978-0-262-01153-2](./Special:BookSources/978-0-262-01153-2). Archived from [the original](http://mitpress.mit.edu/sicp/) on 26 December 2017. Retrieved 22 January 2006.
- Armstrong, Deborah J. (February 2006). "The Quarks of Object-Oriented Development". *Communications of the ACM*. **49** (2): 123–128. [doi](./Doi_(identifier)):[10.1145/1113034.1113040](https://doi.org/10.1145%2F1113034.1113040). [ISSN](./ISSN_(identifier)) [0001-0782](https://search.worldcat.org/issn/0001-0782). [S2CID](./S2CID_(identifier)) [11485502](https://api.semanticscholar.org/CorpusID:11485502).
- Bloch, Joshua (2018). *"Effective Java: Programming Language Guide"* (third ed.). Addison-Wesley. [ISBN](./ISBN_(identifier)) [978-0134685991](./Special:BookSources/978-0134685991).
- [Booch, Grady](./Grady_Booch) (1997). [*Object-Oriented Analysis and Design with Applications*](https://archive.org/details/objectorientedan00booc). [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [978-0-8053-5340-2](./Special:BookSources/978-0-8053-5340-2).
- Eeles, Peter; [Oliver Sims](./Oliver_Sims) (1998). [*Building Business Objects*](https://archive.org/details/buildingbusiness0000eele). [John Wiley & Sons](./John_Wiley_&_Sons). [ISBN](./ISBN_(identifier)) [978-0-471-19176-6](./Special:BookSources/978-0-471-19176-6).
- [Gamma, Erich](./Erich_Gamma); [Richard Helm](./Richard_Helm); [Ralph Johnson](./Ralph_Johnson_(computer_scientist)); [John Vlissides](./John_Vlissides) (1995). [*Design Patterns: Elements of Reusable Object Oriented Software*](https://archive.org/details/designpatternsel00gamm). Addison-Wesley. [Bibcode](./Bibcode_(identifier)):[1995dper.book.....G](https://ui.adsabs.harvard.edu/abs/1995dper.book.....G). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0).
- [Harmon, Paul](./Paul_Harmon_(management_author)); William Morrissey (1996). [*The Object Technology Casebook – Lessons from Award-Winning Business Applications*](https://archive.org/details/objecttechnology00harm). John Wiley & Sons. [ISBN](./ISBN_(identifier)) [978-0-471-14717-6](./Special:BookSources/978-0-471-14717-6).
- [Jacobson, Ivar](./Ivar_Jacobson) (1992). [*Object-Oriented Software Engineering: A Use Case-Driven Approach*](./Use_case). Addison-Wesley. [Bibcode](./Bibcode_(identifier)):[1992oose.book.....J](https://ui.adsabs.harvard.edu/abs/1992oose.book.....J). [ISBN](./ISBN_(identifier)) [978-0-201-54435-0](./Special:BookSources/978-0-201-54435-0).
- [Kay, Alan](./Alan_Kay). [*The Early History of Smalltalk*](https://web.archive.org/web/20050404075821/http://gagne.homedns.org/~tgagne/contrib/EarlyHistoryST.html). Archived from [the original](http://gagne.homedns.org/%7etgagne/contrib/EarlyHistoryST.html) on 4 April 2005. Retrieved 18 April 2005.
- [Meyer, Bertrand](./Bertrand_Meyer) (1997). [*Object-Oriented Software Construction*](https://bertrandmeyer.com/OOSC2/). [Prentice Hall](./Prentice_Hall). [ISBN](./ISBN_(identifier)) [978-0-13-629155-8](./Special:BookSources/978-0-13-629155-8).
- Pecinovsky, Rudolf (2013). [*OOP – Learn Object Oriented Thinking & Programming*](https://pub.bruckner.cz/titles/oop). Bruckner Publishing. [ISBN](./ISBN_(identifier)) [978-80-904661-8-0](./Special:BookSources/978-80-904661-8-0).
- [Rumbaugh, James](./James_Rumbaugh); Blaha, Michael; Premerlani, William; Eddy, Frederick; Lorensen, William (1991). [*Object-Oriented Modeling and Design*](https://archive.org/details/objectorientedmo00rumb). Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-629841-0](./Special:BookSources/978-0-13-629841-0).
- Schach, Stephen (2006). *Object-Oriented and Classical Software Engineering, Seventh Edition*. [McGraw-Hill](./McGraw-Hill). [ISBN](./ISBN_(identifier)) [978-0-07-319126-3](./Special:BookSources/978-0-07-319126-3).
- Schreiner, Axel-Tobias (1993). *Object oriented programming with ANSI-C*. Hanser. [hdl](./Hdl_(identifier)):[1850/8544](https://hdl.handle.net/1850%2F8544). [ISBN](./ISBN_(identifier)) [978-3-446-17426-9](./Special:BookSources/978-3-446-17426-9).
- Taylor, David A. (1992). [*Object-Oriented Information Systems – Planning and Implementation*](https://archive.org/details/objectorientedin00tayl). John Wiley & Sons. [ISBN](./ISBN_(identifier)) [978-0-471-54364-0](./Special:BookSources/978-0-471-54364-0).
- Weisfeld, Matt (2009). *The Object-Oriented Thought Process, Third Edition*. [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [978-0-672-33016-2](./Special:BookSources/978-0-672-33016-2).
- West, David (2004). *Object Thinking (Developer Reference)*. [Microsoft Press](./Microsoft_Press). [ISBN](./ISBN_(identifier)) [978-0-7356-1965-4](./Special:BookSources/978-0-7356-1965-4).

 

## External links

   ![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikiquote-logo.svg/40px-Wikiquote-logo.svg.png) Wikiquote has quotations related to ***[Object-orientation](https://en.wikiquote.org/wiki/Object-orientation)***.    [![Wikiversity logo](//upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Wikiversity_logo_2017.svg/40px-Wikiversity_logo_2017.svg.png)](./File:Wikiversity_logo_2017.svg) Wikiversity has learning resources about ***[Object-oriented programming](https://en.wikiversity.org/wiki/Special:Search/Object-oriented%20programming)*** at [Topic:Object-Oriented Programming](https://en.wikiversity.org/wiki/Topic:Object-Oriented%20Programming)    [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) Wikibooks has a book on the topic of: ***[Object Oriented Programming](https://en.wikibooks.org/wiki/Object%20Oriented%20Programming)***  
- [Introduction to Object Oriented Programming Concepts (OOP) and More](https://www.codeproject.com/Articles/22769/Introduction-to-Object-Oriented-Programming-Concep) by L.W.C. Nirosh
- [Discussion on Cons of OOP](https://thenewstack.io/why-are-so-many-developers-hating-on-object-oriented-programming/)
- [OOP Concepts (Java Tutorials)](https://java.sun.com/docs/books/tutorial/java/concepts/)

 
| vteProgramming paradigms |
| --- |
| Imperative | StructuredJackson structuresBlock-structuredModularNon-structuredProceduralProgramming in the large and in the smallDesign by contractInvariant-basedNested functionObject-orientedClass-based,Prototype-based,Object-basedAgentImmutable objectPersistentUniform function call syntax | Structured | Jackson structuresBlock-structuredModularNon-structuredProceduralProgramming in the large and in the smallDesign by contractInvariant-basedNested function | Object-oriented | Class-based,Prototype-based,Object-basedAgentImmutable objectPersistentUniform function call syntax |
| Structured | Jackson structuresBlock-structuredModularNon-structuredProceduralProgramming in the large and in the smallDesign by contractInvariant-basedNested function |
| Object-oriented | Class-based,Prototype-based,Object-basedAgentImmutable objectPersistentUniform function call syntax |
| Declarative | FunctionalRecursiveAnonymous function(Partial application)Higher-orderPurely functionalTotalStrictGADTsDependent typesFunctional logicPoint-free styleExpression-orientedApplicative,ConcatenativeFunction-level,Value-levelMonadDataflowFlow-basedReactive(Functional reactive)SignalsStreamsSynchronousLogicAbductive logicAnswer setConstraint(Constraint logic)Inductive logicNondeterministicOntologyProbabilistic logicQueryDomain-specificlanguage(DSL)Algebraic modelingArrayAutomata-based(Action)Command(Spacecraft)DifferentiableEnd-userGrammar-orientedInterface descriptionLanguage-orientedList comprehensionLow-codeModelingNatural languageNon-English-basedPage descriptionPipesandfiltersProbabilisticQuantumScientificScriptingSet-theoreticSimulationStack-basedSystemTactileTemplatingTransformation(Graph rewriting,Production,Pattern)Visual | Functional | RecursiveAnonymous function(Partial application)Higher-orderPurely functionalTotalStrictGADTsDependent typesFunctional logicPoint-free styleExpression-orientedApplicative,ConcatenativeFunction-level,Value-levelMonad | Dataflow | Flow-basedReactive(Functional reactive)SignalsStreamsSynchronous | Logic | Abductive logicAnswer setConstraint(Constraint logic)Inductive logicNondeterministicOntologyProbabilistic logicQuery | Domain-specificlanguage(DSL) | Algebraic modelingArrayAutomata-based(Action)Command(Spacecraft)DifferentiableEnd-userGrammar-orientedInterface descriptionLanguage-orientedList comprehensionLow-codeModelingNatural languageNon-English-basedPage descriptionPipesandfiltersProbabilisticQuantumScientificScriptingSet-theoreticSimulationStack-basedSystemTactileTemplatingTransformation(Graph rewriting,Production,Pattern)Visual |
| Functional | RecursiveAnonymous function(Partial application)Higher-orderPurely functionalTotalStrictGADTsDependent typesFunctional logicPoint-free styleExpression-orientedApplicative,ConcatenativeFunction-level,Value-levelMonad |
| Dataflow | Flow-basedReactive(Functional reactive)SignalsStreamsSynchronous |
| Logic | Abductive logicAnswer setConstraint(Constraint logic)Inductive logicNondeterministicOntologyProbabilistic logicQuery |
| Domain-specificlanguage(DSL) | Algebraic modelingArrayAutomata-based(Action)Command(Spacecraft)DifferentiableEnd-userGrammar-orientedInterface descriptionLanguage-orientedList comprehensionLow-codeModelingNatural languageNon-English-basedPage descriptionPipesandfiltersProbabilisticQuantumScientificScriptingSet-theoreticSimulationStack-basedSystemTactileTemplatingTransformation(Graph rewriting,Production,Pattern)Visual |
| Concurrent,parallel | Actor-basedAutomatic mutual exclusionChoreographic programmingConcurrent logic(Concurrent constraint logic)Concurrent OOMacroprogrammingMultitier programmingOrganic computingParallel programming modelsPartitioned global address spaceProcess-orientedRelativistic programmingService-orientedStructured concurrency |
| Metaprogramming | Attribute-orientedAutomatic(Inductive)DynamicExtensibleGenericHomoiconicityInteractiveMacro(Hygienic)Metalinguistic abstractionMulti-stageProgram synthesis(Bayesian,by demonstration,by example,vibe coding)ReflectiveSelf-modifying codeSymbolicTemplate |
| Separationof concerns | AspectsComponentsData-drivenData-orientedEvent-drivenFeaturesLiterateRolesSubjects |
| Comparisons/Lists | Comparison(multi-paradigm,object-oriented,functional),List(OO,by type) |

 
| vteTypes of programming languages |
| --- |
| Level | MachineAssemblyCompiledInterpretedLow-levelHigh-levelVery high-levelEsoteric |
| Generation | FirstSecondThirdFourthFifth |

 
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

 
| Authority control databases |
| --- |
| International | GNDFAST |
| National | United StatesFranceBnF dataJapanCzech RepublicSpainIsrael |
| Other | Yale LUX |

     Hidden categories below