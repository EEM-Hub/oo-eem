---
source: https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)
fetched: 2026-06-19
---

Abstraction of a class 

In [object-oriented programming](./Object-oriented_programming), an **interface** or **protocol type** [[a]](./Interface_(object-oriented_programming)#cite_note-1) is a [data type](./Data_type) that acts as an [abstraction](./Abstraction_(computer_science)) of a [class](./Class_(programming)). It describes a set of [method signatures](./Method_signature), the implementations of which may be provided by multiple classes that are otherwise not necessarily related to each other.[[1]](./Interface_(object-oriented_programming)#cite_note-csharp-learn-2) A class which provides the methods listed in an interface is said to *implement* the interface,[[1]](./Interface_(object-oriented_programming)#cite_note-csharp-learn-2) or to *adopt* the protocol.[[2]](./Interface_(object-oriented_programming)#cite_note-swift-24h-3)

 

Interfaces are useful for [encapsulation](./Encapsulation_(computer_programming)) and reducing [coupling](./Coupling_(computer_programming)). For example, in [Java](./Java_(programming_language)), the `Comparable` interface specifies the method `compareTo`. Thus, a sorting method only needs to take objects of types which implement `Comparable` to sort them, without knowing about the inner nature of the class (except that two of these objects can be compared via `compareTo()`).

 

## Examples

 

Some [programming languages](./Programming_language) provide explicit language support for interfaces: [Ada](./Ada_(programming_language)), [C#](./C_Sharp_(programming_language)), [D](./D_(programming_language)), [Dart](./Dart_(programming_language)), [Delphi](./Delphi_(software)), [Go](./Go_(programming_language)), [Java](./Java_(programming_language)), [Logtalk](./Logtalk), [Object Pascal](./Object_Pascal), [Objective-C](./Objective-C), [OCaml](./OCaml), [PHP](./PHP), [Racket](./Racket_(programming_language)), [Swift](./Swift_(programming_language)), [Python](./Python_(programming_language)) 3.8. In languages supporting [multiple inheritance](./Multiple_inheritance), such as [C++](./C++), interfaces are [abstract classes](./Abstract_class).

 

In Java, an implementation of interfaces may look like:

 
```
class Animal { ... }
class Theropod extends Animal { ... }

interface Flyable {
    void fly();
}

interface Vocal {
    void vocalize();
}

public class Bird extends Theropod implements Flyable, Vocal {
    // ...
    public void fly() { ... }
    public void vocalize() { ... }
}

```
 

In languages without explicit support, interfaces are often still present as conventions; this is known as [duck typing](./Duck_typing). For example, in [Python](./Python_(programming_language)), any class can implement an `__iter__` method and be used as an [iterable](./Iterator).[[3]](./Interface_(object-oriented_programming)#cite_note-python-iter-4) Classes may also explicitly subclass an [ABC](./Abstract_base_class), such as `collections.abc.Iterable`.

 

[Type classes](./Type_class) in languages like [Haskell](./Haskell), or module signatures in [ML](./ML_(programming_language)) and [OCaml](./OCaml), are used for many of the same things as are interfaces.[*[clarification needed](./Wikipedia:Please_clarify)*]

 

In [Rust](./Rust_(programming_language)), interfaces are called *traits*.[[4]](./Interface_(object-oriented_programming)#cite_note-5) In Rust, a `struct` does not contain methods, but may add methods through separate `impl` blocks:

 
```
trait Pet {
    fn speak(&self);
}

struct Dog {
    // Structs only contain their fields
    name: String
}

impl Dog {
    // Not from a trait
    fn new(name: String) -> Self {
        Dog { name }
    }
}

impl Pet for Dog {
    // From a trait
    fn speak(&self) {
        println!("{} says 'Woof!'", self.name);
    }
}

fn main() {
    let dog = Dog::new(String::from("Arlo"));
    dog.speak();
}

```
 

In C++, there are multiple ways to resemble interfaces. One such way is the Java-style interface, which is done using abstract classes. The other, which resembles Go interfaces, is using [concepts](./Concepts_(C++)). Unlike inheritance, with concepts any type may satisfy a concept (not just classes) so long as it satisfies all of its requirements.

 

## See also

 
- [Interface (computing)](./Interface_(computing))
- [Protocols in Objective-C](./Objective-C#Protocols)
- [Interface (Java)](./Interface_(Java))
- [Concept (generic programming)](./Concept_(generic_programming))
- [Delegation (programming)](./Delegation_(programming))
- [Class (computer science)](./Class_(computer_science))
- [Application programming interface](./Application_programming_interface)

 

## Notes

  
1. [↑](./Interface_(object-oriented_programming)#cite_ref-1) Use of these terms varies by programming language. Java and languages derived from it tend to use *interface*, while *protocol* is generally more popular elsewhere.

 

## References

  
1. [1](./Interface_(object-oriented_programming)#cite_ref-csharp-learn_2-0) [2](./Interface_(object-oriented_programming)#cite_ref-csharp-learn_2-1) ["Interfaces - define behavior for multiple types"](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/interfaces). *learn.microsoft.com*. Retrieved 16 November 2022.
2. [↑](./Interface_(object-oriented_programming)#cite_ref-swift-24h_3-0) Miller, BJ (2015). *Sams Teach Yourself Swift in 24 hours*. Indianapolis, Indiana. p. 263. [ISBN](./ISBN_(identifier)) [978-0-672-33724-6](./Special:BookSources/978-0-672-33724-6). Any type can **adopt** a protocol to help give it extra functionality to accomplish a particular set of tasks.`{{cite book}}`:  CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
3. [↑](./Interface_(object-oriented_programming)#cite_ref-python-iter_4-0) ["Glossary — Python 3.11.0 documentation"](https://docs.python.org/3/glossary.html#term-iterable). *docs.python.org*. Retrieved 16 November 2022.
4. [↑](./Interface_(object-oriented_programming)#cite_ref-5) ["Traits - The Rust Reference"](https://doc.rust-lang.org/reference/items/traits.html). January 2024.

 
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