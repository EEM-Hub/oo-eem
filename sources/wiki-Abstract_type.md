---
source: https://en.wikipedia.org/wiki/Abstract_type
fetched: 2026-06-19
---

Feature of a programming language 
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Abstract type"–news·newspapers·books·scholar·JSTOR(January 2022)(Learn how and when to remove this message) |
| --- | --- |

 Not to be confused with [Abstract data type](./Abstract_data_type). 
| Type systems |
| --- |
| General concepts |
| Type safetyStrong vs. weak typing |
| Major categories |
| Staticvs.dynamicManifestvs.inferredNominalvs.structuralDuck typing |
| Minor categories |
| AbstractDependentFlow-sensitiveGradualIntersectionLatentRefinementSubstructuralUniqueSession |
| vte |

 

In [programming languages](./Programming_languages), an **abstract type** (also known as **existential types**)[[1]](./Abstract_type#cite_note-1) is a [type](./Type_(computer_science)) in a [nominative type system](./Nominative_type_system) that cannot be [instantiated](./Instance_(computer_science)) directly; by contrast, a **concrete type** *can* be instantiated directly. Instantiation of an abstract type can occur only indirectly, via a concrete [*subtype*](./Subtyping). 

 

An abstract type may provide no implementation, or an incomplete implementation. In some languages, abstract types with no implementation (rather than an incomplete implementation) are known as *[protocols](./Protocol_(object-oriented_programming))*, *interfaces*, *signatures*, or *class types*. In [class-based](./Class-based_programming) [object-oriented programming](./Object-oriented_programming), abstract types are implemented as *[abstract classes](./Abstract_class)* (also known as *[abstract base classes](./Abstract_base_class)*), and concrete types as *[concrete classes](./Concrete_class)*. In [generic programming](./Generic_programming), the analogous notion is a [*concept*](./Concept_(generic_programming)), which similarly specifies syntax and semantics, but does not require a subtype relationship: two unrelated types may satisfy the same concept.

 

Often, abstract types will have one or more implementations provided separately, for example, in the form of concrete subtypes that *can* be instantiated. In object-oriented programming, an abstract class may include *[abstract methods](./Abstract_method)* or *abstract [properties](./Property_(programming))*[[2]](./Abstract_type#cite_note-Oracle-2) that are shared by its subclasses. Other names for language features that are (or may be) used to implement abstract types include *[traits](./Trait_(computer_science))*, *[mixins](./Mixin)*, *flavors*, *roles*, or *type classes*.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Abstract types may also include any number of non-abstract methods and properties, such as when implementing the [Template Method Pattern](./Template_method_pattern) which uses a mixture of invariant methods with fixed implementations and [hook methods](./Hooking) which can be overridden in concrete subclasses to provide custonised logic.

 

## Creation

 

Abstract classes can be created, signified, or simulated in several ways:

 
- By use of the explicit [keyword](./Keyword_(computer_programming)) `abstract` in the class definition, as in [Java](./Java_(programming_language)), [D](./D_(programming_language)) or [C#](./C_Sharp_(programming_language)).
- By including, in the class definition, one or more [abstract methods](./Abstract_method) (called *pure [virtual functions](./Virtual_functions)* in [C++](./C++)), which the class is declared to accept as part of its protocol, but for which no implementation is provided.
- By [inheriting](./Inheritance_(object-oriented_programming)) from an abstract type, and not overriding all missing features necessary to complete the class definition.  In other words, a child type that does not implement all abstract methods from its parent becomes abstract itself.[[2]](./Abstract_type#cite_note-Oracle-2)[[3]](./Abstract_type#cite_note-3)
- In many dynamically typed languages such as [Smalltalk](./Smalltalk), any class that sends a particular method to [this](./This_(computer_science)), but does not implement that method, can be considered abstract.  (However, in many such languages, like [Objective-C](./Objective-C), the error is not detected until the class is used, and the message returns results in an exception error message such as "Does not recognize selector: xxx" as `- [NSObject doesNotRecognizeSelector:(SEL)selector]` is invoked upon detection of an unimplemented method).

 

## Examples

 

### Java

 

By default, all methods in all classes are concrete, unless the abstract keyword is used. An abstract class may include abstract methods, which have no implementation.
By default, all methods in all interfaces are abstract, unless the default keyword is used.
The default keyword can be used to specify a concrete method in an interface.

 
```
// By default, all methods in all classes are concrete, unless the abstract keyword is used.
abstract class Demo {
    // An abstract class may include abstract methods, which have no implementation.
    public abstract int sum(int x, int y);

    // An abstract class may also include concrete methods.
    public int product(int x, int y) { 
        return x * y; 
    }
}

// By default, all methods in all interfaces are abstract, unless the default keyword is used.
interface DemoInterface {
    int getLength(); // The abstract keyword can be used here, though is completely useless
    
    // The default keyword can be used in this context to specify a concrete method in an interface
    default int product(int x, int y) {
        return x * y;
    }
}

```
 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e9/UML_class_pet.svg/960px-UML_class_pet.svg.png)](./File:UML_class_pet.svg)

 

## Usage

 

Abstract types are an important feature in [statically typed](./Static_typing) OOP languages. Many [dynamically typed](./Dynamic_typing) languages have no equivalent feature (although the use of [duck typing](./Duck_typing) makes abstract types unnecessary); however *[traits](./Trait_(computer_programming))* are found in some modern dynamically-typed languages.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Some authors argue that classes should be [leaf classes](./Leaf_class_(programming_language)) (have no subtypes), or else be abstract.[[4]](./Abstract_type#cite_note-riel1996-4)[[5]](./Abstract_type#cite_note-meyers1996-5)

 

Abstract types are useful in that they can be used to define and enforce a *[protocol](./Protocol_(object-oriented_programming))*; a set of operations that all objects implementing the protocol must support.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Abstract types are also an essential part of the [template method pattern](./Template_method_pattern).

 

## See also

 
- [![icon](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Octicons-terminal.svg/40px-Octicons-terminal.svg.png)](./File:Octicons-terminal.svg)[Computer programming portal](./Portal:Computer_programming)

 
- [Class](./Class_(programming))
- [Concept](./Concept_(generic_programming))
- [Type class](./Type_class)

 

## References

  
1. [↑](./Abstract_type#cite_ref-1) Mitchell, John C.; Plotkin, Gordon D.; [*Abstract Types Have Existential Type*](https://theory.stanford.edu/~jcm/papers/mitch-plotkin-88.pdf), ACM Transactions on Programming Languages and Systems, Vol. 10, No. 3, July 1988, pp. 470–502
2. [1](./Abstract_type#cite_ref-Oracle_2-0) [2](./Abstract_type#cite_ref-Oracle_2-1) ["Abstract Methods and Classes (The Java Tutorials > Learning the Java Language > Interfaces and Inheritance)"](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html). *Oracle.com*. Retrieved 2019-08-14.
3. [↑](./Abstract_type#cite_ref-3) ["Pure Virtual Functions and Abstract Classes in C++"](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/). *GeeksforGeeks.org*. 15 July 2014.
4. [↑](./Abstract_type#cite_ref-riel1996_4-0) Riel, Arthur (1996). *Object-Oriented Design Heuristics*. Addison-Wesley Professional. p. 89. [ISBN](./ISBN_(identifier)) [0-201-63385-X](./Special:BookSources/0-201-63385-X).
5. [↑](./Abstract_type#cite_ref-meyers1996_5-0) Meyers, Scott (1996). [*More Effective C++*](https://archive.org/details/moreeffectivec3500meye/page/258). Addison-Wesley Professional. p. [258](https://archive.org/details/moreeffectivec3500meye/page/258). [ISBN](./ISBN_(identifier)) [0-201-63371-X](./Special:BookSources/0-201-63371-X). Make non-leaf classes abstract

 

## Further reading

 
- [*Head First Java*](https://archive.org/details/headfirstjava00sier_0/page/688). O'Reilly Media. 2003. pp. [688](https://archive.org/details/headfirstjava00sier_0/page/688). [ISBN](./ISBN_(identifier)) [0-596-00920-8](./Special:BookSources/0-596-00920-8).
- Core Java: An Integrated Approach by  R. Nageswara Rao

 

## External links

 
- "Abstract or Skeletal Interfaces Explained" [](https://10kloc.wordpress.com/2012/12/03/abstract-interfaces-the-mystery-revealed/)
- *Types and Programming Languages* by Benjamin Pierce (MIT Press 2002) [](http://www.cis.upenn.edu/~bcpierce/tapl/main.html)
- *[Abstract type](http://rosettacode.org/wiki/Abstract_type)* at [Rosetta Code](./Rosetta_Code)

 Categories