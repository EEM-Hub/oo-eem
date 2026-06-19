---
source: https://en.wikipedia.org/wiki/Class_(computer_programming)
fetched: 2026-06-19
---

Syntactic specification of an object 

In [programming](./Computer_programming), a **class** is a [ syntactic](./Syntax_(programming_languages)) [entity](./Entity) [structure](./Class_(programming)#Structure) used to create [objects](./Object_(computer_science)).[[1]](./Class_(programming)#cite_note-CommonBase-1): 1.3.3  The capabilities of a class differ between [programming languages](./Programming_language), but generally the shared aspects consist of state ([variables](./Variable_(high-level_programming_language))) and behavior ([methods](./Method_(computer_programming))) that are each either associated with a particular object or with all objects of that class.[[2]](./Class_(programming)#cite_note-FOOTNOTEGammaHelmJohnsonVlissides199514-2)[[3]](./Class_(programming)#cite_note-FOOTNOTEBruce20022.1_Objects,_classes,_and_object_types,_https://books.google.com/books?id=9NGWq3K1RwUC&pg=PA18-3)

 

Object state can differ between each instance of the class whereas the class state is shared by all of them. The object methods include access to the object state (via an implicit or explicit parameter that references the object) whereas class methods do not.

 

If the language supports [inheritance](./Inheritance_(object-oriented_programming)), a class can be defined based on another class with all of its state and behavior plus additional state and behavior that further specializes the class. The specialized class is a *sub-class*, and the class it is based on is its *superclass*.

 

In purely object-oriented programming languages, such as [ Java](./Java_(programming_language)) and [C#](./C_Sharp_(programming_language)), all classes might be part of an inheritance tree such that the root class is `Object`, meaning all objects instances are of `Object` or implicitly extend `Object`, which is called a [top type](./Top_type).

 

## History

 

The concept was primarily introduced in [object-oriented programming](./Object-oriented_programming) by the [Simula](./Simula) language in the 1960's and has been in continuous use in many programming languages since.[[1]](./Class_(programming)#cite_note-CommonBase-1): 1.3.3  Its creation was based in similar concept as [block](./Block_(programming)) used in previous-based [ALGOL](./ALGOL_68) programming language.[[1]](./Class_(programming)#cite_note-CommonBase-1): 1.3.2 

 

## Attributes

 

### Object lifecycle

 Main article: [Object lifetime](./Object_lifetime) 

As an [instance](./Instance_(computer_science)) of a class, an object is constructed from a class via *instantiation*. Memory is allocated and initialized for the object state and a [reference](./Reference_(computer_science)) to the object is provided to consuming code. The object is usable until it is destroyed – its state memory is de-allocated.

 

Most languages allow for custom logic at lifecycle events via a [constructor](./Constructor_(object-oriented_programming)) and a [destructor](./Destructor_(computer_programming)). 

 

### Type

 

An object expresses [data type](./Data_type) as an interface – the type of each member variable and the signature of each [member function](./Member_function) (method). A class defines an implementation of an interface, and instantiating the class results in an object that exposes the implementation via the interface.[[4]](./Class_(programming)#cite_note-FOOTNOTEGammaHelmJohnsonVlissides199517-4) In the terms of type theory, a class is an implementation‍—‌a *concrete* [data structure](./Data_structure) and collection of subroutines‍—‌while a type is an [interface](./Protocol_(object-oriented_programming)). Different (concrete) classes can produce objects of the same ([abstract](./Abstract_type)) type (depending on type system). For example, the type (interface) Stack might be implemented by SmallStack that is fast for small stacks but scales poorly and ScalableStack that scales well but has high overhead for small stacks.

 

### Structure

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/86/Oop-uml-class-example.svg/330px-Oop-uml-class-example.svg.png)](./File:Oop-uml-class-example.svg)[UML](./Unified_Modeling_Language) notation for classes 

A class contains [data](./Data_(computing)) [field](./Field_(computer_science)) syntactically described (or *[properties](./Property_(programming))*, *[fields](./Field_(computer_science))*, *data [members](./Member_variable)*, or *[attributes](./Attribute_(computing))*).[[1]](./Class_(programming)#cite_note-CommonBase-1) These are usually field types and names that will be associated with state variables at program run time; these state variables either belong to the class or specific instances of the class. In most languages, the structure defined by the class determines the layout of the memory used by its instances. Other implementations are possible: for example, objects in [Python](./Python_(programming_language)) use associative key-value containers.[[5]](./Class_(programming)#cite_note-pythondata_model-5)

 

Some programming languages such as Eiffel support specification of [invariants](./Class_invariant) as part of the definition of the class, and enforce them through the type system. [Encapsulation](./Encapsulation_(object-oriented_programming)) of state is necessary for being able to enforce the invariants of the class.

 

### Behavior

 Main article: [Method (computer programming)](./Method_(computer_programming))  This section used to contain info on Java interfaces. If you wish to view it (to, say, move to another page), the last revision before the removal of this info is http://en.wikipedia.org/w/index.php?title=Class_(computer_science)&#x26;oldid=165562113  

The behavior (or action[[1]](./Class_(programming)#cite_note-CommonBase-1)) of a class or its instances is defined using [methods](./Method_(computer_programming)). Methods are [subroutines](./Subroutine) with the ability to operate on objects or classes. These operations may alter the state of an object or simply provide ways of accessing it.[[6]](./Class_(programming)#cite_note-FOOTNOTEBooch199486-88-6) (Note: Some languages allow direct access to instance variables ([[C++]])).  Many kinds of methods exist, but support for them varies across languages. Some types of methods are created and called by programmer code, while other special methods—such as constructors, destructors, and conversion operators—are created and called by compiler-generated code. A language may also allow the programmer to define and call these special methods.[[7]](./Class_(programming)#cite_note-7)[[8]](./Class_(programming)#cite_note-8)

 

### Interface

 Main article: [Interface (object-oriented programming)](./Interface_(object-oriented_programming)) Further information: [Interface (computing)](./Interface_(computing)) 

Every class *implements* (or *realizes*) an interface by providing [structure](./Class_(programming)#Structure) and behavior. Structure consists of data and state, and behavior consists of code that specifies how methods are implemented.[[9]](./Class_(programming)#cite_note-FOOTNOTEBooch1994105-9) There is a distinction between the definition of an interface and the implementation of that interface; however, this line is blurred in many programming languages because class declarations both define and implement an interface. Some languages, however, provide features that separate interface and implementation. For example, an [abstract class](./Class_(programming)#Abstract_and_Concrete) can define an interface without providing an implementation.

 

Languages that support class inheritance also allow classes to inherit interfaces from the classes that they are derived from.

 

For example, if "`class Z`" inherits from "`class Y`" and if "`class Y`" implements the interface "`interface X`" then "`class Z`" also implements the functionality(constants and methods declaration) provided by "`interface X`".

 

In languages that support [access specifiers](./Class_(programming)#Information_hiding_and_encapsulation), the interface of a class is considered to be the set of public members of the class, including both methods and attributes (via implicit [getter and setter methods](./Mutator_method)); any private members or internal data structures are not intended to be depended on by externalclient code and thus are not part of the interface.

 

Object-oriented programming methodologyis designed in such a way dictates that the operations of any interface of a class are to be independent of each other. It results in a layered design where clients of an interface use the methods declared in the interface. An interface places no requirements for clients to invoke the operations of one interface in any particular order. This approach has the benefit that client code can assume that the operations of an interface are available for use whenever the clientholds a valid reference has access to the object.[[10]](./Class_(programming)#cite_note-10)

 

#### Interface example

 

The buttons on the front of your television set are the interface between you and the electrical wiring on the other side of its plastic casing. You press the "power" button to toggle the television on and off. In this example, your particular television is the instance, each method is represented by a button, and all the buttons together compose the interface (other television sets that are the same model as yours would have the same interface). In its most common form, an interface is a specification of a group of related methods without any associated implementation of the methods.

 

A television set also has a myriad of *attributes*, such as size and whether it supports color, which together comprise its structure. A class represents the full description of a television, including its attributes (structure) and buttons (interface).

 

Getting the total number of televisions manufactured could be a *static method* of the television class. This method is associated with the class, yet is outside the domain of each instance of the class. A static method that finds a particular instance out of the set of all television objects is another example.

 

### Member accessibility

 "Private member" redirects here. For other uses, see [Private members club](./Private_members_club) and [Private member's bill](./Private_member's_bill). Further information: [Information hiding](./Information_hiding) 

The following is a common set of [access specifiers](./Access_specifiers):[[11]](./Class_(programming)#cite_note-JavaAccessControl-11)

 
- *Private* (or *class-private*) restricts access to the class itself. Only methods that are part of the same class can access private members.
- *Protected* (or *class-protected*) allows the class itself and all its subclasses to access the member.
- *Public* means that any code can access the member by its name.

 

Although many object-oriented languages support the above access specifiers, {{Citation needed|reason=This is fairly obvious, but it needs to be cited&#x2D;&#x2D;could even use a few links even to articles within Wikipedia.|date=April 2012}}  their semantics may differ.

 

Object-oriented design uses the access specifiers in conjunction with careful design of public method implementations to enforce class invariants—constraints on the state of the objects. A common usage of access specifiers is to separate the internal data of a class from its interface: the internal structure is made private, while public [accessor methods](./Accessor_method) can be used to inspect or alter such private data.

 

Access specifiers do not necessarily control *visibility*, in that even private members may be visible to client external code. In some languages, an inaccessible but visible member may be referred to at runtime (for example, by a pointer returned from a member function), but an attempt to use it by referring to the name of the member from the client code will be prevented by the type checker.[[12]](./Class_(programming)#cite_note-12)

 

The various object-oriented programming languages enforce member accessibility and visibility to various degrees, and depending on the language's [type system](./Type_system) and compilation policies, enforced at either [compile time](./Compile_time) or [runtime](./Runtime_(program_lifecycle_phase)). For example, the [Java](./Java_(programming_language)) language does not allow client code that accesses the private data of a class to compile.[[13]](./Class_(programming)#cite_note-13) whereas in languages like [[Objective&#x2D;C]] or [[Perl]] client code is not restricted. In the [C++](./C++) language, private methods are visible, but not accessible in the interface; however, they may be made invisible by explicitly declaring fully abstract classes that represent the interfaces of the class.[[14]](./Class_(programming)#cite_note-cppinterface-14)

 

Some languages feature other accessibility schemes:

 
- *Instance vs. class accessibility*: [Ruby](./Ruby_(programming_language)) supports *instance-private* and *instance-protected* access specifiers in lieu of class-private and class-protected, respectively. They differ in that they restrict access based on the instance itself, rather than the instance's class.[[15]](./Class_(programming)#cite_note-15)
- *Friend*: C++ supports a mechanism where a function explicitly declared as a [friend function](./Friend_function) of the class may access the members designated as private or protected.[[16]](./Class_(programming)#cite_note-16)
- *Path-based*: Java supports restricting access to a member within a [Java package](./Java_syntax#Access_modifiers), which is the logical path of the file. However, it is a common practice when extending a Java framework to implement classes in the same package as a framework class to access protected members. The source file may exist in a completely different location, and may be deployed to a different .jar file, yet still be in the same logical path as far as the JVM is concerned.[[11]](./Class_(programming)#cite_note-JavaAccessControl-11)

 

#### Inheritance

 Main articles: [Inheritance (object-oriented programming)](./Inheritance_(object-oriented_programming)) and [Inheritance (object-oriented programming) § Subclasses and superclasses](./Inheritance_(object-oriented_programming)#Subclasses_and_superclasses) 

Conceptually, a superclass is a [superset](./Superset) of its subclasses. For example, `GraphicObject` could be a superclass of `Rectangle` and `Ellipse`, while `Square` would be a subclass of `Rectangle`. These are all [subset relations](./Subset) in set theory as well, i.e., all squares are rectangles but not all rectangles are squares.

 

A common conceptual error is to mistake a *part of* relation with a subclass. For example, a car and truck are both kinds of vehicles and it would be appropriate to model them as subclasses of a vehicle class. However, it would be an error to model the parts of the car as subclass relations. For example, a car is composed of an engine and body, but it would not be appropriate to model an engine or body as a subclass of a car.

 

In [object-oriented modeling](./Object-oriented_modeling) these kinds of relations are typically modeled as object properties. In this example, the `Car` class would have a property called `parts`. `parts` would be typed to hold a collection of objects, such as instances of `Body`, `Engine`, `Tires`, etc.
Object modeling languages such as [UML](./Unified_Modeling_Language) include capabilities to model various aspects of "part of" and other kinds of relations – data such as the cardinality of the objects, constraints on input and output values, etc. This information can be utilized by developer tools to generate additional code besides the basic data definitions for the objects, such as error checking on [get and set methods](./Mutator_method).[[17]](./Class_(programming)#cite_note-17)

 

One important question when modeling and implementing a system of object classes is whether a class can have one or more superclasses. In the real world with actual sets, it would be rare to find sets that did not intersect with more than one other set. However, while some systems such as Flavors and CLOS provide a capability for more than one parent to do so at run time introduces complexity that many in the object-oriented community consider antithetical to the goals of using object classes in the first place. Understanding which class will be responsible for handling a message can get complex when dealing with more than one superclass. If used carelessly this feature can introduce some of the same system complexity and ambiguity classes were designed to avoid.[[18]](./Class_(programming)#cite_note-18)

 

Most modern object-oriented languages such as Smalltalk and Java require single inheritance at run time. For these languages, multiple inheritance may be useful for modeling but not for an implementation.

 

However, [semantic web](./Semantic_web) application objects do have multiple superclasses. The volatility of the Internet requires this level of flexibility and the technology standards such as the [Web Ontology Language (OWL)](./Web_Ontology_Language) are designed to support it.

 

A similar issue is whether or not the class hierarchy can be modified at run time. Languages such as Flavors, CLOS, and Smalltalk all support this feature as part of their [meta-object protocols](./Meta-object_protocol). Since classes are themselves first-class objects, it is possible to have them dynamically alter their structure by sending them the appropriate messages. Other languages that focus more on strong typing such as Java and C++ do not allow the class hierarchy to be modified at run time. Semantic web objects have the capability for run time changes to classes. The rationale is similar to the justification for allowing multiple superclasses, that the Internet is so dynamic and flexible that dynamic changes to the hierarchy are required to manage this volatility.[[19]](./Class_(programming)#cite_note-19)

 

Although many class-based languages support inheritance, inheritance is not an intrinsic aspect of classes.[*[dubious](./Wikipedia:Accuracy_dispute#Disputed_statement) – [discuss](./Talk:Class_(programming)#Dubious)*][*[*non sequitur*](./Wikipedia:Please_clarify)*] An [object-based language](./Object-based_language) (i.e. [Classic Visual Basic](./Classic_Visual_Basic)) supports classes yet does not support inheritance.

 do not provide the structural benefits of statically type&#x2D;checked interfaces for objects. This is because, in object&#x2D;based languages, it is possible to use and extend data structures and attach methods to them at runtime. This precludes the compiler or interpreter from being able to check the type information specified in the source code as the type is built dynamically and not defined statically. Most of these languages allow for ''instance behavior'' and complex ''operational polymorphism'' (see [[dynamic dispatch]] and [[Polymorphism (computer science)|polymorphism]]).  

## Inter-class relationships

 

A programming language may support various class relationship features.

 

### Compositional

 

Classes can be composed of other classes, thereby establishing a compositional relationship between the enclosing class and its embedded classes. Compositional relationship between classes is also commonly known as a *[has-a](./Has-a)* relationship.[[20]](./Class_(programming)#cite_note-FOOTNOTEBooch1994180-20) For example, a class `Car` could be composed of and contain a class `Engine`. Therefore, a `Car` *has an* `Engine`. One aspect of composition is containment, which is the enclosure of component instances by the instance that has them. If an enclosing object contains component instances by value, the components and their enclosing object have a similar [lifetime](./Object_lifetime). If the components are contained by reference, they may not have a similar lifetime.[[21]](./Class_(programming)#cite_note-FOOTNOTEBooch1994128-129-21) For example, in Objective-C 2.0:

 
```
@interface Car : NSObject

@property NSString *name;
@property Engine *engine
@property NSArray *tires;

@end

```
 

This Car class *has* an instance of NSString (a [string](./String_(computer_science)) object), Engine, and NSArray (an array object).

 

### Hierarchical

 

Classes can be *derived* from one or more existing classes, thereby establishing a hierarchical relationship between the derived-from classes (*base classes*, *parent classes* or *superclasses*) and the derived class (*child class* or *subclass*) . The relationship of the derived class to the derived-from classes is commonly known as an *[is-a](./Is-a)* relationship.[[22]](./Class_(programming)#cite_note-FOOTNOTEBooch1994112-22) For example, a class 'Button' could be derived from a class 'Control'. Therefore, a Button *is a* Control. Structural and behavioral members of the parent classes are *inherited* by the child class. Derived classes can define additional structural members (data fields) and behavioral members (methods) in addition to those that they *inherit* and are therefore *specializations* of their superclasses. Also, derived classes can [override](./Method_overriding) inherited methods if the language allows.

 

Not all languages support multiple inheritance. For example, Java allows a class to implement multiple interfaces, but only inherit from one class.[[23]](./Class_(programming)#cite_note-javainterface-23) If multiple inheritance is allowed, the hierarchy is a [directed acyclic graph](./Directed_acyclic_graph) (or DAG for short), otherwise it is a [tree](./Tree_(graph_theory)). The hierarchy has classes as nodes and inheritance relationships as links. Classes in the same level are more likely to be [associated](./Association_(object-oriented_programming)) than classes in different levels. The levels of this hierarchy are called [layers](./Layer_(object-oriented_design)) or levels of abstraction.

 

Example (Simplified Objective-C 2.0 code, from iPhone SDK):

 
```
@interface UIResponder : NSObject //...
@interface UIView : UIResponder //...
@interface UIScrollView : UIView //...
@interface UITableView : UIScrollView //...

```
 

In this example, a UITableView *is a* UIScrollView *is a* UIView *is a* UIResponder *is an* NSObject.

 

### Modeling

 

In [object-oriented analysis](./Object-oriented_analysis_and_design) and in [Unified Modelling Language](./Unified_Modelling_Language) (UML), an [association](./Association_(object-oriented_programming)) between two classes represents a collaboration between the classes or their corresponding instances. Associations have direction; for example, a bi-directional association between two classes indicates that both of the classes are aware of their relationship.[[24]](./Class_(programming)#cite_note-ibmuml-24) Associations may be labeled according to their name or purpose.[[25]](./Class_(programming)#cite_note-FOOTNOTEBooch1994179-25)

 

An association role is given end of an association and describes the role of the corresponding class. For example, a "subscriber" role describes the way instances of the class "Person" participate in a "subscribes-to" association with the class "Magazine". Also, a "Magazine" has the "subscribed magazine" role in the same association. Association role multiplicity describes how many instances correspond to each instance of the other class of the association. Common multiplicities are "0..1", "1..1", "1..*" and "0..*", where the "*" specifies any number of instances.[[24]](./Class_(programming)#cite_note-ibmuml-24)

 

## Taxonomy

 

There are many categories of classes, some of which overlap.

 

### Abstract and concrete 

 

 See also: [Abstract type](./Abstract_type) 

In a language that supports inheritance, an **abstract class**, or **abstract base class** (**ABC**), is a class that cannot be directly instantiated. By contrast, a **concrete class** is a class that *can* be directly instantiated. Instantiation of an abstract class can occur only indirectly, via a concrete *sub*class.

 

An abstract class is either labeled as such explicitly or it may simply specify *[abstract methods](./Abstract_method)* (or *[virtual methods](./Virtual_method)*). An abstract class may provide implementations of some methods, and may also specify virtual methods via [signatures](./Type_signature) that are to be implemented by direct or indirect descendants of the abstract class. Before a class derived from an abstract class can be instantiated, all abstract methods of its parent classes must be implemented by some class in the derivation chain.[[26]](./Class_(programming)#cite_note-cpppoly-26)

 

Most object-oriented programming languages allow the programmer to specify which classes are considered abstract and will not allow these to be instantiated. For example, in [Java](./Java_(programming_language)), [C#](./C_Sharp_(programming_language)) and [PHP](./PHP), the keyword `abstract` is used.[[27]](./Class_(programming)#cite_note-27)[[28]](./Class_(programming)#cite_note-28) In [C++](./C++), an abstract class is a class having at least one abstract method given by the appropriate syntax in that language (a pure virtual function in C++ parlance).[[26]](./Class_(programming)#cite_note-cpppoly-26)

 

A class consisting of only pure virtual methods is called a *pure abstract base class* (or *pure ABC*) in C++ and is also known as an *interface* by users of the language.[[14]](./Class_(programming)#cite_note-cppinterface-14) Other languages, notably Java and C#, support a variant of abstract classes called an [interface](./Interface_(Java)) via a keyword in the language. In these languages, [multiple inheritance](./Multiple_inheritance) is not allowed, but a class can implement multiple interfaces. Such a class can only contain abstract publicly accessible methods.[[23]](./Class_(programming)#cite_note-javainterface-23)[[29]](./Class_(programming)#cite_note-29)[[30]](./Class_(programming)#cite_note-30)

 Abstract classes defined as interfaces are a much more specific use of the more general meaning of the term ''interface'', even as used in computer science, and the concept of interfaces has seen much use and popularity within the realm of languages that support object&#x2D;orientation. 

### Local and inner

 

In some languages, classes can be declared in [scopes](./Scope_(programming)) other than the global scope. There are various types of such classes.

 

An *[inner class](./Inner_class)* is a class defined within another class. The relationship between an inner class and its containing class can also be treated as another type of class association. An inner class is typically neither associated with instances of the enclosing class nor instantiated along with its enclosing class. Depending on the language, it may or may not be possible to refer to the class from outside the enclosing class. A related concept is *inner types*, also known as *inner data type* or *nested type*, which is a generalization of the concept of inner classes. [C++](./C++) is an example of a language that supports both inner classes and inner types (via *[typedef](./Typedef)* declarations).[[31]](./Class_(programming)#cite_note-31)[[32]](./Class_(programming)#cite_note-32)

 

A *local class* is a class defined within a procedure or function. Such structure limits references to the class name to within the scope where the class is declared. Depending on the semantic rules of the language, there may be additional restrictions on local classes compared to non-local ones. One common restriction is to disallow local class methods to access local variables of the enclosing function. For example, in C++, a local class may refer to [static variables](./Static_variable) declared within its enclosing function, but may not access the function's [automatic variables](./Automatic_variable).[[33]](./Class_(programming)#cite_note-33)

 

### Metaclass

 Main article: [Metaclass](./Metaclass) 

A metaclass is a class where instances are classes.[[34]](./Class_(programming)#cite_note-FOOTNOTEBooch1994133-134-34) A metaclass describes a common structure of a collection of classes and can implement a [design pattern](./Design_pattern_(computer_science)) or describe particular kinds of classes. Metaclasses are often used to describe [frameworks](./Software_framework).[[35]](./Class_(programming)#cite_note-35)

 

In some languages, such as [Python](./Python_(programming_language)), [Ruby](./Ruby_(programming_language)) or [Smalltalk](./Smalltalk), a class is also an object; thus each class is an instance of a unique metaclass that is built into the language.[[5]](./Class_(programming)#cite_note-pythondata_model-5)[[36]](./Class_(programming)#cite_note-36) [[37]](./Class_(programming)#cite_note-FOOTNOTEBooch1994134-37)
The [Common Lisp Object System](./Common_Lisp_Object_System) (CLOS) provides [metaobject protocols](./Metaobject) (MOPs) to implement those classes and metaclasses.[[38]](./Class_(programming)#cite_note-38)

 

### Final

 

A **final class** cannot be subclassed. It is basically the opposite of an abstract class, which must be subclassed to be used and cannot be [instantiated](./Instance_(computer_science)) directly. A final class is implicitly a concrete class, *can* be instantiated directly.

 

A class is declared as final via the keyword `final` in Java, C++ or PHP, or `sealed` in C#. However, this concept should not be confused with classes in Java qualified with the keyword `sealed`, that only allow inheritance from selected subclasses.[[39]](./Class_(programming)#cite_note-39)[[40]](./Class_(programming)#cite_note-40)[[41]](./Class_(programming)#cite_note-41)[[42]](./Class_(programming)#cite_note-42) In languages like [Kotlin](./Kotlin_(programming_language)), all classes are final by default, while to allow a class to be inherited from, it must instead be marked `open`.[[43]](./Class_(programming)#cite_note-43)

 

For example, Java's `String`  class is marked as `final`.[[44]](./Class_(programming)#cite_note-44)

 

Final classes may allow a compiler to perform optimizations that are not available for classes that can be subclassed.[[45]](./Class_(programming)#cite_note-45)

  The following goes without saying, i.e., it says nothing but to hint that "abstract" and "concrete" are an "either but not both" concept. 'abstract' and 'concrete' are defined already above.  While it is impossible in any object&#x2D;oriented language to have a class that is both abstract and concrete, it may be possible to have an abstract partial class   The following seemingly belongs in the 'method' article   It is also possible not to declare the whole class as such, but only the [[Override (object&#x2D;oriented programming)|override]] as sealed. This classes are used because of efficiency concerns (can be called like static classes) and security (avoids inadvertent modification of the class semantics).<ref&#x3E;{{cite web |access&#x2D;date=2011&#x2D;08&#x2D;03 |date=2002&#x2D;03&#x2D;25 |first=Hanspeter |last=Mössenböck |page=17 |publisher=Institut für Systemsoftware, Johannes Kepler Universität Linz, Fachbereich Informatik |title=Advanced C#: Overriding of Methods |url=http://ssw.jku.at/Teaching/Lectures/CSharp/Tutorial/Part2.pdf}}
</ref&#x3E;  

### Sealed

 

A "sealed class" is a class that restricts inheritance to a selected list of classes. It should not be confused with the `sealed` keyword in C#, which denotes a final class. The list of permitted classes the sealed class may inherit is specified using a `permits` clause.[[46]](./Class_(programming)#cite_note-46)

 
```
public sealed class Quadrilateral 
    extends Shape 
    implements Renderable, Transformable, Comparable<Quadrilateral>, Measurable
    permits Parallelogram, Trapezoid, Kite {
    // ...
}

```
 

`non-sealed` is another keyword used to declare that a class or interface which extends a sealed class can be extended by unknown classes.[[47]](./Class_(programming)#cite_note-47)

 
```
sealed class Parallelogram extends Quadrilateral { /* ... */ }
sealed class Rectangle extends Parallelogram { /* ... */ }

non-sealed class Square extends Rectangle { /* ... */ }

// Because Square is non-sealed, any class can inherit from it
class RedSquare extends Square { /* ... */ }

```
 

### Open

 

An open class can be changed. Typically, an [executable program](./Executable_program) cannot be changed by customers. Developers can often change some classes, but typically cannot change standard or built-in ones. In [Ruby](./Ruby_(programming_language)#Open_classes), all classes are open. In [Python](./Python_(programming_language)), classes can be created at runtime, and all can be modified afterward.[[48]](./Class_(programming)#cite_note-48) [Objective-C categories](./Objective-C#Categories) permit the programmer to add methods to an existing class without the need to recompile that class or even have access to its source code.

 

### Mixin

 

Some languages have special support for [mixins](./Mixin), though, in any language with multiple inheritance, a mixin is simply a class that does not represent an is-a-type-of relationship. Mixins are typically used to add the same methods to multiple classes; for example, a class `UnicodeConversionMixin` might provide a method called `unicodeToAscii()` when included in classes `FileReader` and `WebPageScraper` that do not share a common parent.

 

### Partial

 

In languages supporting the feature, a *partial class* is a class whose definition may be split into multiple pieces, within a single [source-code](./Source_code) file or across multiple files.[[49]](./Class_(programming)#cite_note-mspartial-49) The pieces are merged at compile time, making compiler output the same as for a non-partial class.

 

The primary motivation for the introduction of partial classes is to facilitate the implementation of [code generators](./Automatic_programming), such as [visual designers](./Visual_designer).[[49]](./Class_(programming)#cite_note-mspartial-49) It is otherwise a challenge or compromise to develop code generators that can manage the generated code when it is interleaved within developer-written code. Using partial classes, a code generator can process a separate file or coarse-grained partial class within a file, and is thus alleviated from intricately interjecting generated code via extensive parsing, increasing compiler efficiency and eliminating the potential risk of corrupting developer code. In a simple implementation of partial classes, the compiler can perform a phase of [precompilation](./Precompilation) where it "unifies" all the parts of a partial class. Then, compilation can proceed as usual.[[50]](./Class_(programming)#cite_note-50)

 

Other benefits and effects of the partial class feature include:

 
- Enables separation of a class's interface and implementation code in a unique way.
- Eases navigation through large classes within an [editor](./Source_code_editor).
- Enables [separation of concerns](./Separation_of_concerns), in a way similar to [aspect-oriented programming](./Aspect-oriented_programming) but without using any extra tools.
- Enables multiple developers to work on a single class concurrently without the need to merge individual code into one file at a later time. (This enabling may be considered by some or most to be a detriment rather than a benefit for SoC can apply to programmers also).

 

Partial classes have existed in [Smalltalk](./Smalltalk) under the name of *Class Extensions* for considerable time. With the arrival of the [.NET framework 2](./.NET_Framework), [Microsoft](./Microsoft) introduced partial classes, supported in both [C#](./C_Sharp_(programming_language)) 2.0 and [Visual Basic 2005](./Visual_Basic_.NET). [WinRT](./WinRT) also supports partial classes.[[51]](./Class_(programming)#cite_note-51)

 

### Uninstantiable

 

*Uninstantiable classes* allow programmers to group together per-class fields and methods that are accessible at runtime without an instance of the class. Indeed, instantiation is prohibited for this kind of class.

 

For example, in C#, a class marked `static` can not be instantiated, can only have static members (fields, methods, other), may not have *instance constructors*, and is `sealed` (is final).
[[52]](./Class_(programming)#cite_note-52)

 

### Unnamed

 

An *unnamed class* or *anonymous class* is not bound to a name or identifier upon definition.[[53]](./Class_(programming)#cite_note-53)[[54]](./Class_(programming)#cite_note-54) This is analogous to named versus [unnamed functions](./Anonymous_function).

 
```
interface Greeting {
    void sayHello();
}

// Anonymous class that implements Greeting
Greeting myGreeting = new Greeting() {
    @Override
    public void sayHello() {
        System.out.println("Hello from an anonymous class!");
    }
};

myGreeting.sayHello();

```
 

## Benefits

 

The benefits of organizing software into object classes fall into three categories:[[55]](./Class_(programming)#cite_note-55)

 
- Rapid development
- Ease of maintenance
- Reuse of code and designs

 

Object classes facilitate rapid development because they lessen the semantic gap between the code and the users. System analysts can talk to both developers and users using essentially the same vocabulary, talking about accounts, customers, bills, etc. Object classes often facilitate rapid development because most object-oriented environments come with powerful debugging and testing tools. Instances of classes can be inspected at run time to verify that the system is performing as expected. Also, rather than get dumps of core memory, most object-oriented environments have interpreted debugging capabilities so that the developer can analyze exactly where in the program the error occurred and can see which methods were called to which arguments and with what arguments.[[56]](./Class_(programming)#cite_note-56)

 

Object classes facilitate ease of maintenance via encapsulation. When developers need to change the behavior of an object they can localize the change to just that object and its component parts. This reduces the potential for unwanted side effects from maintenance enhancements.

 

Software reuse is also a major benefit of using Object classes. Classes facilitate re-use via inheritance and interfaces. When a new behavior is required it can often be achieved by creating a new class and having that class inherit the default behaviors and data of its superclass and then tailoring some aspect of the behavior or data accordingly. Re-use via interfaces (also known as methods) occurs when another object wants to invoke (rather than create a new kind of) some object class. This method for re-use removes many of the common errors that can make their way into software when one program re-uses code from another.[[57]](./Class_(programming)#cite_note-57)

 

## Runtime representation

 
|  | This Runtime representationneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sourcesin this Runtime representation. Unsourced material may be challenged and removed.Find sources:"Class"programming–news·newspapers·books·scholar·JSTOR(May 2024)(Learn how and when to remove this message) |
| --- | --- |

 

As a data type, a class is usually considered as a compile time construct.[[58]](./Class_(programming)#cite_note-58) A language or library may also support [prototype](./Prototype-based_programming) or [factory](./Factory_method_pattern) [metaobjects](./Metaobject) that represent runtime information about classes, or even represent metadata that provides access to [reflective programming](./Reflective_programming) (reflection) facilities and ability to manipulate data structure formats at runtime. Many languages distinguish this kind of [run-time type information](./Run-time_type_information) about classes from a class on the basis that the information is not needed at runtime. Some dynamic languages do not make strict distinctions between runtime and compile time constructs, and therefore may not distinguish between metaobjects and classes.

 

For example, if Human is a [metaobject](./Metaobject) representing the class Person, then instances of class Person can be created by using the facilities of the Human [metaobject](./Metaobject).

 

## Class-based programming

 Programming which all objects are created by classes Content from [Class-based programming](./Class-based_programming) was merged into this article following talk page consensus. See [Talk:Class-based_programming#Merger_proposal_(2008)](./Talk:Class-based_programming#Merger_proposal_(2008)) 

**Class-based programming**, or more commonly **class-orientated**, is a style of [object-oriented programming](./Object-oriented_programming) which all [objects](./Object_(computer_science)) are created by a [class](./Class_(programming)) and without [inheritance](./Inheritance_(object-oriented_programming)) between them.[[59]](./Class_(programming)#cite_note-59)[[60]](./Class_(programming)#cite_note-CLU's_history-60)

 

The most popular and developed model of OOP is a class-based model, instead of an object-based model. In this model, objects are entities that combine *[state](./State_(computer_science))* (i.e., data), *[behavior](./Behavior)* (i.e., procedures, or *[methods](./Method_(computer_science))*) and *[identity](./Identity_(object-oriented_programming))* (unique existence among all other objects). The structure and behavior of an object are defined by a [class](./Class_(programming)), which is a [syntactic](./Syntactic) structure, or [blueprint](./Blueprint), of all objects of a specific type. An object must be explicitly created based on a class and an object thus created is considered to be an [instance](./Instantiation_(computer_science)) of that class. An object is similar to a [structure](./Data_structure), with the addition of method pointers, member access control, and an implicit data member which locates instances of the class (i.e., objects of the class) in the class hierarchy (essential for runtime inheritance features).

 

### Encapsulation

 

[Encapsulation](./Information_hiding) prevents users from breaking the [invariants](./Invariant_(computer_science)) of the class, which is useful because it allows the implementation of a class of objects to be changed for aspects not exposed in the interface without impact to user code. The definitions of encapsulation focus on the grouping and packaging of related information ([cohesion](./Cohesion_(computer_science))) rather than security issues.

 

### Critique

 

Class-based languages, or, to be more precise, [typed languages](./Typed_language), where [subclassing](./Subclass_(computer_science)) is the only way of [subtyping](./Subtyping), have been criticized for mixing up implementations and interfaces—the essential principle in object-oriented programming. The critics say one might create a bag class that stores a [collection](./Collection_class) of objects, then extend it to make a new class called a set class where the duplication of objects is eliminated.[[61]](./Class_(programming)#cite_note-61)[[62]](./Class_(programming)#cite_note-62)  Now, a function that takes an object of the bag class may expect that adding two objects increases the size of a bag by two, yet if one passes an object of a set class, then adding two objects may or may not increase the size of a bag by two. The problem arises precisely because subclassing implies subtyping even in the instances where the principle of subtyping, known as the [Liskov substitution principle](./Liskov_substitution_principle), does not hold. [Barbara Liskov](./Barbara_Liskov) and [Jeannette Wing](./Jeannette_Wing) formulated the principle succinctly in a 1994 paper as follows:

  inline math as LaTeX has poor baseline alignment (better with MathJaX HTML/CSS rendering of LaTeX)     
:''Let <math&#x3E;q(x)</math&#x3E; be a property provable about objects <math&#x3E;x</math&#x3E; of type <math&#x3E;T</math&#x3E;. Then <math&#x3E;q(y)</math&#x3E; should be provable for objects <math&#x3E;y</math&#x3E; of type <math&#x3E;S</math&#x3E;, where <math&#x3E;S</math&#x3E; is a subtype of <math&#x3E;T</math&#x3E;.''
 inline math as HTML  

*Subtype Requirement*: Let ⁠    ϕ ϕ  ( x )   {\displaystyle \phi (x)}  ![{\displaystyle \phi (x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/546b660b2f3cfb5f34be7b3ed8371d54f5c74227)⁠ be a property provable about objects ⁠    x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4)⁠ of type ⁠    T   {\displaystyle T}  ![{\displaystyle T}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0)⁠.  Then ⁠    ϕ ϕ  ( y )   {\displaystyle \phi (y)}  ![{\displaystyle \phi (y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/db7ffe2f7daf9bae8d3f2711b2fd67348aceb3dc)⁠ should be true for objects ⁠    y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d)⁠ of type ⁠    S   {\displaystyle S}  ![{\displaystyle S}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4611d85173cd3b508e67077d4a1252c9c05abca2)⁠ where ⁠    S   {\displaystyle S}  ![{\displaystyle S}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4611d85173cd3b508e67077d4a1252c9c05abca2)⁠ is a subtype of ⁠    T   {\displaystyle T}  ![{\displaystyle T}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0)⁠. 

  inline math as HTML bold
:''Let {{math| '''q(x)''' }} be a property provable about objects {{math| '''x''' }} of type {{math| '''T'''. }} Then {{math| '''q(y)''' }} should be provable for objects {{math| '''y''' }} of type {{math| '''S''', }} where {{math| '''S''' }} is a subtype of {{math| '''T'''. }}''
  

Thus, normally one must distinguish subtyping and subclassing. Most current object-oriented languages distinguish subtyping and subclassing, however some approaches to design do not.

 

Also, another common example is that a person object created from a [child class](./Subclass_(computer_science)) cannot become an object of [parent class](./Parent_class) because a child class and a parent class inherit a person class but class-based languages mostly do not allow to change the kind of class of the object at runtime. For class-based languages, this restriction is essential in order to preserve unified view of the class to its users. The users should not need to care whether one of the implementations of a method happens to cause changes that break the [invariants](./Invariant_(computer_science)) of the class. Such changes can be made by destroying the object and constructing another in its place. Polymorphism can be used to preserve the relevant interfaces even when such changes are done, because the objects are viewed as black box abstractions and accessed via object [identity](./Identity_(object-oriented_programming)). However, usually the value of object references referring to the object is changed, which causes effects to client code.

 

### Example languages

 See also: [Category:Class-based programming languages](./Category:Class-based_programming_languages) 

Although [Simula](./Simula) introduced the class abstraction, the canonical example of a class-based language is [Smalltalk](./Smalltalk). Others include [PHP](./PHP), [C++](./C++), [Java](./Java_(programming_language)), [C#](./C_Sharp_(programming_language)), and [Objective-C](./Objective-C).
 [*[dubious](./Wikipedia:Accuracy_dispute#Disputed_statement) – [discuss](./Talk:Class_(programming)#Dubious)*][*[*non sequitur*](./Wikipedia:Please_clarify)*]

 

## Prototype-based programming

 

In contrast to creating an object from a class, some programming contexts support object creation by copying (cloning) a [prototype](./Prototype-based_programming) object.[[63]](./Class_(programming)#cite_note-63)

 

## See also

  
- [Block (programming)](./Block_(programming)) – Demarcated group of source code statements that run in sequence
- [Class diagram](./Class_diagram) – Diagram that describes the static structure of a software system
- [Class invariant](./Class_invariant) – Unchanging property for all objects of a class
- [Class variable](./Class_variable) – Variable defined in a class whose objects all possess the same copy
- [Function (computer science)](./Function_(computer_science)) – Sequence of program instructions invokable by other softwarePages displaying short descriptions of redirect targets
- [Instance variable](./Instance_variable) – Member variable of a class that all its objects possess a their own copy of
- [Metaclass](./Metaclass) – Class that describes common behavior for classes
- [Object (computer science)](./Object_(computer_science)) – Semantic instance with state, behavior, and identity
- [Syntax (programming language)](./Syntax_(programming_language)) – Form of source code, without regard to meaningPages displaying short descriptions of redirect targets
- [Variable (computer science)](./Variable_(computer_science)) – Named container for a particular type of dataPages displaying short descriptions of redirect targets

 
- [![icon](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Octicons-terminal.svg/40px-Octicons-terminal.svg.png)](./File:Octicons-terminal.svg)[Computer programming portal](./Portal:Computer_programming)

 

## Notes

   
1. [1](./Class_(programming)#cite_ref-CommonBase_1-0) [2](./Class_(programming)#cite_ref-CommonBase_1-1) [3](./Class_(programming)#cite_ref-CommonBase_1-2) [4](./Class_(programming)#cite_ref-CommonBase_1-3) [5](./Class_(programming)#cite_ref-CommonBase_1-4) [Dahl, Ole-Johan](./Ole-Johan_Dahl); Myhrhaug, Bjørn; [Nygaard, Kristen](./Kristen_Nygaard) (1970). [Common Base Language](https://web.archive.org/web/20240919044713/https://www.softwarepreservation.org/projects/ALGOL/manual/Simula-CommonBaseLanguage.pdf) (PDF) (Report). Norwegian Computing Center. Archived from the original on 2024-09-19. Retrieved 20 August 2025.
2. [↑](./Class_(programming)#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides199514_2-0) [Gamma et al. 1995](./Class_(programming)#CITEREFGammaHelmJohnsonVlissides1995), p. 14.
3. [↑](./Class_(programming)#cite_ref-FOOTNOTEBruce20022.1_Objects,_classes,_and_object_types,_https://books.google.com/books?id=9NGWq3K1RwUC&pg=PA18_3-0) [Bruce 2002](./Class_(programming)#CITEREFBruce2002), 2.1 Objects, classes, and object types, [https://books.google.com/books?id=9NGWq3K1RwUC&pg=PA18](https://books.google.com/books?id=9NGWq3K1RwUC&pg=PA18).
4. [↑](./Class_(programming)#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides199517_4-0) [Gamma et al. 1995](./Class_(programming)#CITEREFGammaHelmJohnsonVlissides1995), p. 17.
5. [1](./Class_(programming)#cite_ref-pythondata_model_5-0) [2](./Class_(programming)#cite_ref-pythondata_model_5-1) ["3. Data model"](https://docs.python.org/reference/datamodel.html). *The Python Language Reference*. Python Software Foundation. Retrieved 2012-04-26.
6. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch199486-88_6-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 86-88.
7. [↑](./Class_(programming)#cite_ref-7) ["Classes (I)"](http://www.cplusplus.com/doc/tutorial/classes/). *C++ Language Tutorial*. cplusplus.com. Retrieved 2012-04-29.
8. [↑](./Class_(programming)#cite_ref-8) ["Classes (II)"](http://www.cplusplus.com/doc/tutorial/classes2/). *C++ Language Tutorial*. cplusplus.com. Retrieved 2012-04-29.
9. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994105_9-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 105.
10. [↑](./Class_(programming)#cite_ref-10) Parsons, June Jamrich (2015-06-22). *New Perspectives on Computer Concepts 2016, Comprehensive*. Boston, MA: Cengage Learning. [ISBN](./ISBN_(identifier)) [9781305271616](./Special:BookSources/9781305271616). [OCLC](./OCLC_(identifier)) [917155105](https://search.worldcat.org/oclc/917155105).
11. [1](./Class_(programming)#cite_ref-JavaAccessControl_11-0) [2](./Class_(programming)#cite_ref-JavaAccessControl_11-1) ["Controlling Access to Members of a Class"](http://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html). *The Java Tutorials*. Oracle. Retrieved 2012-04-19.
12. [↑](./Class_(programming)#cite_ref-12) ["OOP08-CPP. Do not return references to private data"](https://web.archive.org/web/20151003162754/https://www.securecoding.cert.org/confluence/display/cplusplus/OOP08-CPP.+Do+not+return+references+to+private+data). *CERT C++ Secure Coding Standard*. Carnegie Mellon University. 2010-05-10. Archived from [the original](https://www.securecoding.cert.org/confluence/display/cplusplus/OOP08-CPP.+Do+not+return+references+to+private+data) on 2015-10-03. Retrieved 2012-05-07.
13. [↑](./Class_(programming)#cite_ref-13)  Ben-Ari, Mordechai (2007-01-24). ["2.2 Identifiers"](http://introcs.cs.princeton.edu/java/11cheatsheet/errors.pdf) (PDF). *Compile and Runtime Errors in Java*. [Archived](https://web.archive.org/web/20111018094803/http://introcs.cs.princeton.edu/java/11cheatsheet/errors.pdf) (PDF) from the original on 2011-10-18. Retrieved 2012-05-07.
14. [1](./Class_(programming)#cite_ref-cppinterface_14-0) [2](./Class_(programming)#cite_ref-cppinterface_14-1) Wild, Fred. ["C++ Interfaces"](http://www.drdobbs.com/cpp/184410630). *Dr. Dobb's*. UBM Techweb. Retrieved 2012-05-02.
15. [↑](./Class_(programming)#cite_ref-15) ["modules_and_classes: Visibility"](https://docs.ruby-lang.org/en/master/syntax/modules_and_classes_rdoc.html#label-Visibility).
16. [↑](./Class_(programming)#cite_ref-16) ["Friendship and inheritance"](http://www.cplusplus.com/doc/tutorial/inheritance/). *C++ Language Tutorial*. cplusplus.com. Retrieved 2012-04-26.
17. [↑](./Class_(programming)#cite_ref-17) Berfeld, Marya (2 December 2008). ["UML-to-Java transformation in IBM Rational Software Architect editions and related software"](http://www.ibm.com/developerworks/rational/library/08/1202_berfeld/). [IBM](./IBM). Retrieved 20 December 2013.
18. [↑](./Class_(programming)#cite_ref-18) Jacobsen, Ivar; Magnus Christerson; Patrik Jonsson; Gunnar Overgaard (1992). [*Object Oriented Software Engineering*](https://archive.org/details/objectorientedso00jaco/page/43). Addison-Wesley ACM Press. pp. [43–69](https://archive.org/details/objectorientedso00jaco/page/43). [ISBN](./ISBN_(identifier)) [0-201-54435-0](./Special:BookSources/0-201-54435-0).
19. [↑](./Class_(programming)#cite_ref-19) Knublauch, Holger; Oberle, Daniel; Tetlow, Phil; Wallace, Evan (2006-03-09). ["A Semantic Web Primer for Object-Oriented Software Developers"](http://www.w3.org/2001/sw/BestPractices/SE/ODSD/). [W3C](./W3C). Retrieved 2008-07-30.
20. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994180_20-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 180.
21. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994128-129_21-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 128-129.
22. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994112_22-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 112.
23. [1](./Class_(programming)#cite_ref-javainterface_23-0) [2](./Class_(programming)#cite_ref-javainterface_23-1) ["Interfaces"](http://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html). *The Java Tutorials*. Oracle. Retrieved 2012-05-01.
24. [1](./Class_(programming)#cite_ref-ibmuml_24-0) [2](./Class_(programming)#cite_ref-ibmuml_24-1) Bell, Donald. ["UML Basics: The class diagram"](http://www.ibm.com/developerworks/rational/library/content/RationalEdge/sep04/bell/). *developer Works*. IBM. Retrieved 2012-05-02.
25. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994179_25-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 179.
26. [1](./Class_(programming)#cite_ref-cpppoly_26-0) [2](./Class_(programming)#cite_ref-cpppoly_26-1) ["Polymorphism"](http://www.cplusplus.com/doc/tutorial/polymorphism/). *C++ Language Tutorial*. cplusplus.com. Retrieved 2012-05-02.
27. [↑](./Class_(programming)#cite_ref-27) ["Abstract Methods and Classes"](http://docs.oracle.com/javase/tutorial/java/IandI/abstract.html). *The Java Tutorials*. Oracle. Retrieved 2012-05-02.
28. [↑](./Class_(programming)#cite_ref-28) ["Class Abstraction"](http://php.net/manual/en/language.oop5.abstract.php). *PHP Manual*. The PHP Group. Retrieved 2012-05-02.
29. [↑](./Class_(programming)#cite_ref-29) ["Interfaces (C# Programming Guide)"](http://msdn.microsoft.com/en-us/library/ms173156.aspx). *C# Programming Guide*. Microsoft. Retrieved 2013-08-15.
30. [↑](./Class_(programming)#cite_ref-30)  ["Inheritance (C# Programming Guide)"](http://msdn.microsoft.com/en-us/library/ms173149.aspx). *C# Programming Guide*. Microsoft. Retrieved 2012-05-02.
31. [↑](./Class_(programming)#cite_ref-31) ["Nested classes (C++ only)"](http://publib.boulder.ibm.com/infocenter/comphelp/v8v101/index.jsp?topic=%2Fcom.ibm.xlcpp8a.doc%2Flanguage%2Fref%2Fcplr061.htm). *XL C/C++ V8.0 for AIX*. IBM. Retrieved 2012-05-07.
32. [↑](./Class_(programming)#cite_ref-32)  ["Local type names (C++ only)"](http://publib.boulder.ibm.com/infocenter/comphelp/v8v101/index.jsp?topic=%2Fcom.ibm.xlcpp8a.doc%2Flanguage%2Fref%2Fcplr063.htm). *XL C/C++ V8.0 for AIX*. IBM. Retrieved 2012-05-07.
33. [↑](./Class_(programming)#cite_ref-33) ["Local classes (C++ only)"](http://publib.boulder.ibm.com/infocenter/comphelp/v8v101/index.jsp?topic=%2Fcom.ibm.xlcpp8a.doc%2Flanguage%2Fref%2Fcplr062.htm). *XL C/C++ V8.0 for AIX*. IBM. Retrieved 2012-05-07.
34. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994133-134_34-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 133-134.
35. [↑](./Class_(programming)#cite_ref-35) ["13 Classes and metaclasses"](https://web.archive.org/web/20210224193450/http://pharo.gforge.inria.fr/PBE1/PBE1ch14.html). *pharo.gforge.inria.fr*. Archived from [the original](http://pharo.gforge.inria.fr/PBE1/PBE1ch14.html) on 2021-02-24. Retrieved 2016-10-31.
36. [↑](./Class_(programming)#cite_ref-36) ["class Class"](https://docs.ruby-lang.org/en/master/Class.html).
37. [↑](./Class_(programming)#cite_ref-FOOTNOTEBooch1994134_37-0) [Booch 1994](./Class_(programming)#CITEREFBooch1994), p. 134.
38. [↑](./Class_(programming)#cite_ref-38) ["MOP: Concepts"](https://web.archive.org/web/20101115095930/http://www.alu.org/mop/concepts.html#introduction). *The Common Lisp Object System MetaObject Protocol*. Association of Lisp Users. Archived from [the original](https://www.alu.org/mop/concepts.html#introduction) on 2010-11-15. Retrieved 2012-05-08.
39. [↑](./Class_(programming)#cite_ref-39) ["sealed (C# Reference)"](http://msdn.microsoft.com/en-us/library/ms173149.aspx). *C# Reference*. Microsoft. Retrieved 2012-05-08.
40. [↑](./Class_(programming)#cite_ref-40)  ["Writing Final Classes and Methods"](http://docs.oracle.com/javase/tutorial/java/IandI/final.html). *The Java Tutorials*. Oracle. Retrieved 2012-05-08.
41. [↑](./Class_(programming)#cite_ref-41)  ["PHP: Final Keyword"](http://php.net/manual/en/language.oop5.final.php). *PHP Manual*. The PHP Group. Retrieved 2014-08-21.
42. [↑](./Class_(programming)#cite_ref-42) ["Sealed Classes"](https://docs.oracle.com/en/java/javase/22/language/sealed-classes-and-interfaces.html). *Oracle Help Center*. Retrieved 2025-07-07.
43. [↑](./Class_(programming)#cite_ref-43) JetBrains s.r.o. (15 December 2025). ["Inheritance"](https://kotlinlang.org/docs/inheritance.html). *kotlinlang.org*. JetBrains s.r.o.
44. [↑](./Class_(programming)#cite_ref-44) ["String (Java Platform SE 7)"](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html). *Java Platform, Standard Edition 7: API Specification*. Oracle. Retrieved 2012-05-08.
45. [↑](./Class_(programming)#cite_ref-45) Brand, Sy (2 March 2020). ["The Performance Benefits of Final Classes"](https://devblogs.microsoft.com/cppblog/the-performance-benefits-of-final-classes/). *Microsoft C++ team blog*. Microsoft. Retrieved 4 April 2020.
46. [↑](./Class_(programming)#cite_ref-46) ["Sealed Classes"](https://docs.oracle.com/en/java/javase/25/language/sealed-classes-and-interfaces.html). *docs.oracle.com*. Oracle Help Center. Retrieved 16 October 2025.
47. [↑](./Class_(programming)#cite_ref-47) Oracle Corporation. ["4 - Sealed Classes"](https://docs.oracle.com/en/java/javase/17/language/sealed-classes-and-interfaces.html). *docs.oracle.com*. Oracle Corporation. Retrieved 7 June 2026.
48. [↑](./Class_(programming)#cite_ref-48) ["9. Classes"](https://docs.python.org/3.3/tutorial/classes.html). *The Python Tutorial*. Python.org. Retrieved 3 March 2018. As is true for modules, classes partake of the dynamic nature of Python: they are created at runtime, and can be modified further after creation.
49. [1](./Class_(programming)#cite_ref-mspartial_49-0) [2](./Class_(programming)#cite_ref-mspartial_49-1) mairaw; BillWagner; tompratt-AQ (2015-09-19), ["Partial Classes and Methods"](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods), *C# Programming Guide*, Microsoft, retrieved 2018-08-08
50. [↑](./Class_(programming)#cite_ref-50) ["Partial Classes and Members - C#"](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods).
51. [↑](./Class_(programming)#cite_ref-51) BillWagner (2024-11-14). ["Partial Classes and Methods - C#"](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods). *learn.microsoft.com*. Retrieved 2025-02-06.
52. [↑](./Class_(programming)#cite_ref-52) ["Static Classes and Static Class Members (C# Programming Guide)"](http://msdn.microsoft.com/en-us/library/79b3xss3(v=vs.100).aspx). *C# Programming Guide*. Microsoft. Retrieved 2012-05-08. 
53. [↑](./Class_(programming)#cite_ref-53) ["Anonymous Classes (The Java Tutorials > Learning the Java Language > Classes and Objects)"](https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html). *docs.oracle.com*. Retrieved 2021-05-13.
54. [↑](./Class_(programming)#cite_ref-54) ["PHP: Anonymous classes - Manual"](https://www.php.net/manual/en/language.oop5.anonymous.php). *www.php.net*. Retrieved 2021-08-11.
55. [↑](./Class_(programming)#cite_ref-55) ["What is an Object?"](http://docs.oracle.com/javase/tutorial/java/concepts/object.html). *oracle.com*. Oracle Corporation. Retrieved 13 December 2013.
56. [↑](./Class_(programming)#cite_ref-56) Booch, Grady; Robert A. Maksimchuk; Michael W. Engle; Bobbi J. Young Ph.D.; Jim Conallen; Kelli A. Houston (April 30, 2007). [*Object-Oriented Analysis and Design with Applications*](http://my.safaribooksonline.com/book/software-engineering-and-development/object/9780201895513). Addison-Wesley Professional. pp. 1–28. [ISBN](./ISBN_(identifier)) [978-0-201-89551-3](./Special:BookSources/978-0-201-89551-3). Retrieved 20 December 2013. There are fundamental limiting factors of human cognition; we can address these constraints through the use of decomposition, abstraction, and hierarchy.
57. [↑](./Class_(programming)#cite_ref-57) Jacobsen, Ivar; Magnus Christerson; Patrik Jonsson; Gunnar Overgaard (1992). [*Object Oriented Software Engineering*](https://archive.org/details/objectorientedso00jaco). Addison-Wesley ACM Press. [ISBN](./ISBN_(identifier)) [0-201-54435-0](./Special:BookSources/0-201-54435-0).
58. [↑](./Class_(programming)#cite_ref-58) ["C++ International standard"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/n4713.pdf) (PDF). *Working Draft, Standard for Programming Language C++*. ISO/IEC JTC1/SC22 WG21. [Archived](https://web.archive.org/web/20171209100334/http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2017/n4713.pdf) (PDF) from the original on 2017-12-09. Retrieved 5 January 2020.
59. [↑](./Class_(programming)#cite_ref-59) Wegner, Peter (1987). ["Dimensions of object-based language design"](https://dl.acm.org/doi/pdf/10.1145/38765.38823). *Conference proceedings on Object-oriented programming systems, languages and applications*. pp. 168–182. [doi](./Doi_(identifier)):[10.1145/38765.38823](https://doi.org/10.1145%2F38765.38823). [ISBN](./ISBN_(identifier)) [0-89791-247-0](./Special:BookSources/0-89791-247-0).
60. [↑](./Class_(programming)#cite_ref-CLU's_history_60-0) Liskov, Barbara (1996). ["A history of CLU"](https://dl.acm.org/doi/pdf/10.1145/234286.1057826). *History of programming languages---II*. pp. 471–510. [doi](./Doi_(identifier)):[10.1145/234286.1057826](https://doi.org/10.1145%2F234286.1057826). [ISBN](./ISBN_(identifier)) [0-201-89502-1](./Special:BookSources/0-201-89502-1).
61. [↑](./Class_(programming)#cite_ref-61) Kiselyov, Oleg. ["Subtyping, Subclassing, and Trouble with OOP"](http://okmij.org/ftp/Computation/Subtyping/). Retrieved 7 October 2012.
62. [↑](./Class_(programming)#cite_ref-62) Ducasse, Stéphane. ["A set cannot be a subtype of a bag"](http://stephane.ducasse.free.fr/Resources/LecturesInPowerpoint/STOOP-416-LSP.ppt). Retrieved 7 October 2012.
63. [↑](./Class_(programming)#cite_ref-63) Amir, Masroor (25 March 2023). ["OOP - Object Oriented Programming - Concepts | Languages | Benefits [2023]"](https://www.thegeeksbot.com/2023/03/object-oriented-programming.html). *The Geeks Bot | A Computer Science Site for geeks*. Retrieved 2023-04-04.

 

## References

  
- Booch, Grady (1994). *Objects and Design with Applications, Second Edition*. Benjamin/Cummings.
- Gamma; Helm; Johnson; Vlissides (1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm). Addison Wesley. [ISBN](./ISBN_(identifier)) [9780201633610](./Special:BookSources/9780201633610).
- Bruce, Kim B. (2002). [*Foundations of Object-Oriented Languages: Types and Semantics*](http://mitpress.mit.edu/books/foundations-object-oriented-languages). Cambridge, Massachusetts: MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-02523-2](./Special:BookSources/978-0-262-02523-2).

  

## Further reading

 
- [Abadi; Cardelli: A Theory of Objects](http://lucacardelli.name/TheoryOfObjects.html)
- [ISO/IEC 14882:2003 Programming Language C++, International standard](http://www.open-std.org/jtc1/sc22/wg21/)
- [Class Warfare: Classes vs. Prototypes](http://www.laputan.org/reflection/warfare.html), by Brian Foote
- Meyer, B.: "Object-oriented software construction", 2nd edition, Prentice Hall, 1997, [ISBN](./ISBN_(identifier)) [0-13-629155-4](./Special:BookSources/0-13-629155-4)
- Rumbaugh et al.: "Object-oriented modeling and design", Prentice Hall, 1991, [ISBN](./ISBN_(identifier)) [0-13-630054-5](./Special:BookSources/0-13-630054-5)

 
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