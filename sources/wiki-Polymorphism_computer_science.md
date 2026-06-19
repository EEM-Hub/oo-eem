---
source: https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
fetched: 2026-06-19
---

Using one interface or symbol with regards to multiple different types Not to be confused with [Polymorphic code](./Polymorphic_code). 
| Polymorphism |
| --- |
| Ad hoc polymorphism |
| Function overloadingOperator overloading |
| Parametric polymorphism |
| Generic functionGeneric programming |
| Subtyping |
| Virtual functionSingle and dynamic dispatchDouble dispatchMultiple dispatchPredicate dispatch |
| vte |

 

In [programming language theory](./Programming_language_theory) and [type theory](./Type_theory), **polymorphism** allows a value or variable to have more than one type and allows a given operation to be performed on values of more than one type.[[1]](./Polymorphism_(computer_science)#cite_note-Luca-1)

 

In [object-oriented programming](./Object-oriented_programming), polymorphism is the provision of one [interface](./Interface_(object-oriented_programming)) to entities of different [data types](./Data_type).[[2]](./Polymorphism_(computer_science)#cite_note-2)  The concept is borrowed from a principle in [biology](./Biology) in which an organism or species can have many different forms or stages.[[3]](./Polymorphism_(computer_science)#cite_note-Moved-3)

 

The most commonly recognized major forms of polymorphism are:

 
- *[Ad hoc polymorphism](./Ad_hoc_polymorphism)*: defines a common interface for an arbitrary set of individually specified types.
- *[Parametric polymorphism](./Parametric_polymorphism)*: does not specify concrete types and instead uses abstract symbols that can substitute for any type.
- *[Subtyping](./Subtyping)* (also called *subtype polymorphism* or *inclusion polymorphism*): when a name denotes instances of many different classes related by a common superclass.[[4]](./Polymorphism_(computer_science)#cite_note-gbooch-4)

 

## History

 

Interest in polymorphic [type systems](./Type_system) developed significantly in the 1990s, with practical implementations beginning to appear by the end of the decade. *Ad hoc polymorphism* and *parametric polymorphism* were originally described in [Christopher Strachey](./Christopher_Strachey)'s *[Fundamental Concepts in Programming Languages](./Fundamental_Concepts_in_Programming_Languages)*,[[5]](./Polymorphism_(computer_science)#cite_note-Strachey00-5) where they are listed as "the two main classes" of polymorphism. Ad hoc polymorphism was a feature of [ALGOL 68](./ALGOL_68), while parametric polymorphism was the core feature of [ML](./ML_(programming_language))'s [type system](./Type_system).

 

In a 1985 paper, [Peter Wegner](./Peter_Wegner_(computer_scientist)) and [Luca Cardelli](./Luca_Cardelli) introduced the term *inclusion polymorphism* to model subtypes and [inheritance](./Inheritance_(object-oriented_programming)),[[1]](./Polymorphism_(computer_science)#cite_note-Luca-1) citing [Simula](./Simula) as the first programming language to implement it.

 

## Forms

 

### Ad hoc polymorphism

 Further information: [Ad hoc polymorphism](./Ad_hoc_polymorphism) 

[Christopher Strachey](./Christopher_Strachey) chose the term *[ad hoc](./Ad_hoc) polymorphism* to refer to polymorphic functions that can be applied to arguments of different types, but that behave differently depending on the type of the argument to which they are applied (also known as [function overloading](./Function_overloading) or [operator overloading](./Operator_overloading)).[[5]](./Polymorphism_(computer_science)#cite_note-Strachey00-5) "Ad hoc" here means that this form of polymorphism is not a fundamental feature of the type system. In the [Java](./Java_(programming_language)) example below, the `add` functions seem to work generically over two types ([integer](./Integer_(computer_science)) and [string](./String_(computer_science))) when looking at the invocations, but are considered entirely distinct functions by the [compiler](./Compiler):

 
```
class AdHocPolymorphic {
    public String add(int x, int y) {
        return String.format("Sum: %d", x + y);
    }

    public String add(String name) {
        return String.format("Added ", name);
    }
}

public class Adhoc {
    public static void main(String[] args) {
        AdHocPolymorphic poly = new AdHocPolymorphic();

        System.out.println(poly.add(1, 2));   // prints "Sum: 3"
        System.out.println(poly.add("Jay")); // prints "Added Jay"
    }
}

```
 

In [dynamically typed](./Dynamically_typed) languages the situation can be more complex, as the correct function that needs to be invoked might only be determinable at run time.

 

[Implicit type conversion](./Implicit_type_conversion) has also been defined as a form of polymorphism, referred to as "coercion polymorphism".[[1]](./Polymorphism_(computer_science)#cite_note-Luca-1)[[6]](./Polymorphism_(computer_science)#cite_note-Tucker2004-6)

 

### Parametric polymorphism

 Further information: [Parametric polymorphism](./Parametric_polymorphism) 

*Parametric polymorphism* allows a function or a data type to be written generically, so that it can handle values *uniformly* without depending on their type.[[7]](./Polymorphism_(computer_science)#cite_note-bjpierce-7) Parametric polymorphism is a way to make a language more expressive while still maintaining full static [type safety](./Type_safety).

 

The concept of parametric polymorphism applies to both [data types](./Data_type) and [functions](./Function_(computer_programming)). A function that can evaluate to or be applied to values of different types is known as a *polymorphic function.* A data type that can appear to be of a generalized type (e.g., a [list](./List_(abstract_data_type)) with elements of arbitrary type) is designated *polymorphic data type* like the generalized type from which such specializations are made.

 

Parametric polymorphism is ubiquitous in functional programming, where it is often simply referred to as "polymorphism". The next example in [Haskell](./Haskell) shows a parameterized list data type and two parametrically polymorphic functions on them:

 
```
data List a = Nil | Cons a (List a)

length :: List a -> Integer
length Nil         = 0
length (Cons x xs) = 1 + length xs

map :: (a -> b) -> List a -> List b
map f Nil         = Nil
map f (Cons x xs) = Cons (f x) (map f xs)

```
 

Parametric polymorphism is also available in several object-oriented languages. For instance, [templates](./Template_(C++)) in [C++](./C++) and [D](./D_(programming_language)), or under the name [generics](./Generics_in_Java) in [C#](./C_Sharp_(programming_language)), [Delphi](./Delphi_(software)), [Java](./Java_(programming_language)), and [Go](./Go_(programming_language)):

 
```
class List<T> {
    class Node<T> {
        T elem;
        Node<T> next;
    }
    Node<T> head;
    int length() { ... }
}

List<B> map(Func<A, B> f, List<A> xs) {
    ...
}

```
 

[John C. Reynolds](./John_C._Reynolds) (and later [Jean-Yves Girard](./Jean-Yves_Girard)) formally developed this notion of polymorphism as an extension to lambda calculus (called the polymorphic lambda calculus or [System F](./System_F)). Any parametrically polymorphic function is necessarily restricted in what it can do, working on the shape of the data instead of its value, leading to the concept of [parametricity](./Parametricity).

 

### Subtyping

 Further information: [Subtyping](./Subtyping) 

Some languages employ the idea of *subtyping* (also called *subtype polymorphism* or *inclusion polymorphism*) to restrict the range of types that can be used in a particular case of polymorphism. In these languages, subtyping allows a function to be written to take an object of a certain type *T*, but also work correctly if passed an object that belongs to a type *S* that is a subtype of *T* (according to the [Liskov substitution principle](./Liskov_substitution_principle)). This type relation is sometimes written *S* <: *T*. Conversely, *T* is said to be a *supertype* of *S*, written *T* :> *S*. Subtype polymorphism is usually resolved dynamically (see below).

 

In the following Java example cats and dogs are made subtypes of pets. The procedure `letsHear()` accepts a pet, but will also work correctly if a subtype is passed to it:

 
```
abstract class Pet {
    abstract String speak();
}

class Cat extends Pet {
    String speak() {
        return "Meow!";
    }
}

class Dog extends Pet {
    String speak() {
        return "Woof!";
    }
}

static void letsHear(final Pet pet) {
    System.out.println(pet.speak());
}

static void main(String[] args) {
    letsHear(new Cat());
    letsHear(new Dog());
}

```
 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e9/UML_class_pet.svg/960px-UML_class_pet.svg.png)](./File:UML_class_pet.svg)

 

In another example, if *Number*, *Rational*, and *Integer* are types such that *Number* :> *Rational* and *Number* :> *Integer* (*Rational* and *Integer* as subtypes of a type *Number* that is a supertype of them), a function written to take a *Number* will work equally well when passed an *Integer* or *Rational* as when passed a *Number*. The actual type of the object can be hidden from clients into a [black box](./Black_box), and accessed via object [identity](./Identity_(object-oriented_programming)). If the *Number* type is *abstract*, it may not be possible to access an object whose *most-derived* type is *Number* (see [abstract data type](./Abstract_data_type), [abstract class](./Abstract_class)). This particular kind of type hierarchy is known, especially in the context of the [Scheme language](./Scheme_(programming_language)), as a *[numerical tower](./Numerical_tower)*, and usually contains many more types.

 

[Object-oriented programming languages](./Object-oriented_programming_language) offer subtype polymorphism using *[subclassing](./Subclass_(computer_science))* (also known as *[inheritance](./Inheritance_in_object-oriented_programming)*). In typical implementations, each class contains what is called a *[virtual table](./Virtual_table)* (shortly called *vtable*) – a table of functions that implement the polymorphic part of the class interface—and each object contains a pointer to the vtable of its class, which is then consulted whenever a polymorphic method is called. This mechanism is an example of:

 
- *[late binding](./Late_binding)*, because virtual function calls are not bound until the time of invocation;
- *[single dispatch](./Single_dispatch)* (i.e., single-argument polymorphism), because virtual function calls are bound simply by looking through the vtable provided by the first argument (the `this` object), so the runtime types of the other arguments are completely irrelevant.

 

The same goes for most other popular object systems. Some, however, such as [Common Lisp Object System](./Common_Lisp_Object_System), provide *[multiple dispatch](./Multiple_dispatch)*, under which method calls are polymorphic in all arguments.

 

The interaction between parametric polymorphism and subtyping leads to the concepts of [type variance](./Type_variance) and [bounded quantification](./Bounded_quantification).

 

### Row polymorphism

 Further information: [Row polymorphism](./Row_polymorphism) See also: [Duck typing](./Duck_typing) 

Row polymorphism[[8]](./Polymorphism_(computer_science)#cite_note-8) is a similar, but distinct concept from subtyping. It deals with [structural types](./Structural_type_system). It allows the usage of all values whose types have certain properties, without losing the remaining type information.

 

### Polytypism

 Further information: [Generic programming § Functional languages](./Generic_programming#Functional_languages) 

A related concept is *polytypism* (or *data type genericity*). A polytypic function is more general than polymorphic, and in such a function, "though one can provide fixed ad hoc cases for specific data types, an ad hoc combinator is absent".[[9]](./Polymorphism_(computer_science)#cite_note-9)

 

### Rank polymorphism

 

Rank polymorphism is one of the defining features of the [array programming](./Array_programming) languages, like [APL](./APL_(programming_language)). The essence of the rank-polymorphic programming model is implicitly treating all operations as aggregate operations, usable on arrays with arbitrarily many dimensions,[[10]](./Polymorphism_(computer_science)#cite_note-10) which is to say that rank polymorphism allows functions to be defined to operate on arrays of any shape and size.

 

## Implementation aspects

 

### Static and dynamic polymorphism

 Further information: [Static polymorphism](./Static_polymorphism), [Late binding](./Late_binding), and [Dynamic dispatch](./Dynamic_dispatch) 

Polymorphism can be distinguished by when the implementation is selected: statically (at compile time) or dynamically (at run time, typically via a [virtual function](./Virtual_function)). This is known respectively as *[static dispatch](./Static_dispatch)* and *[dynamic dispatch](./Dynamic_dispatch),* and the corresponding forms of polymorphism are accordingly called *static polymorphism* and *dynamic polymorphism*.

 

Static polymorphism executes faster, because there is no dynamic dispatch overhead, but requires additional compiler support. Further, static polymorphism allows greater static analysis by compilers (notably for optimization), source code analysis tools, and human readers (programmers). Dynamic polymorphism is more flexible but slower—for example, dynamic polymorphism allows [duck typing](./Duck_typing), and a dynamically linked library may operate on objects without knowing their full type.

 

Static polymorphism typically occurs in ad hoc polymorphism and parametric polymorphism, whereas dynamic polymorphism is usual for subtype polymorphism. However, it is possible to achieve static polymorphism with subtyping through more sophisticated use of [template metaprogramming](./Template_metaprogramming), namely the [curiously recurring template pattern](./Curiously_recurring_template_pattern).

 

When polymorphism is exposed via a [library](./Library_(computing)), static polymorphism becomes impossible for [dynamic libraries](./Dynamic_libraries) as there is no way of knowing what types the parameters are when the [shared object](./Shared_object) is built. While languages like C++ and Rust use [monomorphized](./Monomorphization) templates, the [Swift programming language](./Swift_programming_language) makes extensive use of dynamic dispatch to build the [application binary interface](./Application_binary_interface) for these libraries by default. As a result, more code can be shared for a reduced system size at the cost of runtime overhead.[[11]](./Polymorphism_(computer_science)#cite_note-11)

 

## See also

 
- [Type class](./Type_class)
- [Virtual inheritance](./Virtual_inheritance)

 

## References

  
1. [1](./Polymorphism_(computer_science)#cite_ref-Luca_1-0) [2](./Polymorphism_(computer_science)#cite_ref-Luca_1-1) [3](./Polymorphism_(computer_science)#cite_ref-Luca_1-2) [Cardelli, Luca](./Luca_Cardelli); [Wegner, Peter](./Peter_Wegner_(computer_scientist)) (December 1985). ["On understanding types, data abstraction, and polymorphism"](http://lucacardelli.name/Papers/OnUnderstanding.A4.pdf) (PDF). *[ACM Computing Surveys](./ACM_Computing_Surveys)*. **17** (4): 471–523. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.117.695](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.117.695). [doi](./Doi_(identifier)):[10.1145/6041.6042](https://doi.org/10.1145%2F6041.6042). [S2CID](./S2CID_(identifier)) [2921816](https://api.semanticscholar.org/CorpusID:2921816). Conventional typed languages, such as Pascal, are based on the idea that functions and procedures, and hence their operands, have a unique type. Such languages are said to be *monomorphic*, in the sense that every value and variable can be interpreted to be of one and only one type. Monomorphic programming languages may be contrasted with *polymorphic* languages in which some values and variables may have more than one type. Polymorphic functions are functions whose operands (actual parameters) can have more than one type. Polymorphic types are types whose operations are applicable to values of more than one type.
2. [↑](./Polymorphism_(computer_science)#cite_ref-2) [Stroustrup, Bjarne](./Bjarne_Stroustrup) (February 19, 2007). ["Bjarne Stroustrup's C++ Glossary"](http://www.stroustrup.com/glossary.html#Gpolymorphism). polymorphism – providing a single interface to entities of different types.
3. [↑](./Polymorphism_(computer_science)#cite_ref-Moved_3-0) ["Polymorphism"](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html). *The Java Tutorials: Learning the Java Language: Interfaces and Inheritance*. Oracle. Retrieved 2021-09-08.
4. [↑](./Polymorphism_(computer_science)#cite_ref-gbooch_4-0) Conallen, J.; Engle, M.; Houston, K.; Maksimchuk, R.; Young, B.; [Booch, G.](./Grady_Booch) (2007). *Object-Oriented Analysis and Design with Applications* (3rd ed.). Pearson Education. [ISBN](./ISBN_(identifier)) [9780132797443](./Special:BookSources/9780132797443).
5. [1](./Polymorphism_(computer_science)#cite_ref-Strachey00_5-0) [2](./Polymorphism_(computer_science)#cite_ref-Strachey00_5-1) [Strachey, Christopher](./Christopher_Strachey) (2000). "Fundamental Concepts in Programming Languages". *[Higher-Order and Symbolic Computation](./Higher-Order_and_Symbolic_Computation)*. **13** (1/2): 11–49. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.332.3161](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.332.3161). [doi](./Doi_(identifier)):[10.1023/A:1010000313106](https://doi.org/10.1023%2FA%3A1010000313106). [ISSN](./ISSN_(identifier)) [1573-0557](https://search.worldcat.org/issn/1573-0557). [S2CID](./S2CID_(identifier)) [14124601](https://api.semanticscholar.org/CorpusID:14124601).
6. [↑](./Polymorphism_(computer_science)#cite_ref-Tucker2004_6-0) Tucker, Allen B. (2004). [*Computer Science Handbook*](https://books.google.com/books?id=9IFMCsQJyscC&pg=SA91-PA5) (2nd ed.). Taylor & Francis. pp. 91–. [ISBN](./ISBN_(identifier)) [978-1-58488-360-9](./Special:BookSources/978-1-58488-360-9).
7. [↑](./Polymorphism_(computer_science)#cite_ref-bjpierce_7-0) Pierce, B.C. (2002). ["23.2 Varieties of Polymorphism"](https://books.google.com/books?id=ti6zoAC9Ph8C&pg=PA340). *Types and Programming Languages*. MIT Press. pp. 340–1. [ISBN](./ISBN_(identifier)) [9780262162098](./Special:BookSources/9780262162098).
8. [↑](./Polymorphism_(computer_science)#cite_ref-8)  Wand, Mitchell (June 1989). "Type inference for record concatenation and multiple inheritance". *Proceedings. Fourth Annual Symposium on Logic in Computer Science*. pp. 92–97. [doi](./Doi_(identifier)):[10.1109/LICS.1989.39162](https://doi.org/10.1109%2FLICS.1989.39162). 
9. [↑](./Polymorphism_(computer_science)#cite_ref-9) Lämmel, Ralf; Visser, Joost (2002). "Typed Combinators for Generic Traversal". *Practical Aspects of Declarative Languages: 4th International Symposium*. Springer. pp. 137–154, See p. 153. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.18.5727](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.18.5727). [ISBN](./ISBN_(identifier)) [354043092X](./Special:BookSources/354043092X).
10. [↑](./Polymorphism_(computer_science)#cite_ref-10) Slepak, Justin; Shivers, Olin; Manolios, Panagiotis (2019). "The semantics of rank polymorphism". [arXiv](./ArXiv_(identifier)):[1907.00509](https://arxiv.org/abs/1907.00509) [[cs.PL](https://arxiv.org/archive/cs.PL)].
11. [↑](./Polymorphism_(computer_science)#cite_ref-11) Beingessner, Alexis. ["How Swift Achieved Dynamic Linking Where Rust Couldn't"](https://gankra.github.io/blah/swift-abi/).

 

## External links

 
- [C++ examples of polymorphism](http://www.cplusplus.com/doc/tutorial/polymorphism/)
- [Objects and Polymorphism (Visual Prolog)](http://wiki.visual-prolog.com/index.php?title=Objects_and_Polymorphism)
- [Polymorphism on MSDN](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/polymorphism)
- [Polymorphism Java Documentation on Oracle](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html)

 
| vteData types |
| --- |
| Uninterpreted | BitByteTritTryteWordBit array |
| Numeric | Arbitrary-precision or bignumComplexDecimalFixed pointBlock floating pointFloating pointReduced precisionMinifloatHalf precisionbfloat16Single precisionDouble precisionQuadruple precisionOctuple precisionExtended precisionLong doubleIntegersignednessIntervalRational |
| Reference | AddressphysicalvirtualPointer |
| Text | CharacterStringnull-terminated |
| Composite | Algebraic data typegeneralizedArrayAssociative arrayClassDependentEqualityInductiveIntersectionListObjectmetaobjectOption typeProductRecord or StructRefinementSetUniontagged |
| Other | Any typeBooleanBottom typeCollectionEnumerated typeExceptionFunction typeOpaque data typeRecursive data typeSemaphoreStreamStrongly typed identifierType classEmpty typeUnit typeVoid |
| Relatedtopics | ValueAbstract data typeBoxingData structureGenericKindmetaclassParametric polymorphismPrimitive data typeInterfaceSubtypingType constructorType conversionType systemType theoryVariable |

           Hidden categories below