---
source: https://en.wikipedia.org/wiki/Iterator_pattern
fetched: 2026-06-19
---

Software design pattern 

In [object-oriented programming](./Object-oriented_programming), the **iterator pattern** is a [design pattern](./Design_pattern_(computer_science)) in which an [iterator](./Iterator) is used to traverse a [container](./Collection_(abstract_data_type)) and access the container's elements. The iterator pattern decouples [algorithms](./Algorithm) from containers; in some cases, algorithms are necessarily container-specific and thus cannot be decoupled.

 

For example, the hypothetical algorithm `searchForElement()` can be implemented generally using a specified type of iterator rather than implementing it as a container-specific algorithm. This allows `searchForElement()` to be used on any container that supports the required type of iterator.

  

## Overview

 

The Iterator
[[1]](./Iterator_pattern#cite_note-GoF-1)
design pattern is one of the 23 well-known 
*["Gang of Four" design patterns](./Design_Patterns)* 
that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

### What problems can the Iterator design pattern solve?

 

[[2]](./Iterator_pattern#cite_note-2)

 
- The elements of an aggregate object should be accessed and traversed without exposing its representation (data structures).
- New traversal operations should be defined for an aggregate object without changing its interface.

 

Defining access and traversal operations in the aggregate interface is inflexible because it commits the aggregate to particular access and traversal operations and makes it impossible to add new operations
later without having to change the aggregate interface.

 

### What solution does the Iterator design pattern describe?

 
- Define a separate (iterator) object that encapsulates accessing and traversing an aggregate object.
- Clients use an iterator to access and traverse an aggregate without knowing its representation (data structures).

 

Different iterators can be used to access and traverse an aggregate in different ways. 

New access and traversal operations can be defined independently by defining new iterators.

 

See also the UML class and sequence diagram below.

 

## Definition

 

The essence of the Iterator Pattern is to "Provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation.".[[3]](./Iterator_pattern#cite_note-3)

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/c/c5/W3sDesign_Iterator_Design_Pattern_UML.jpg)](./File:W3sDesign_Iterator_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Iterator design pattern.[[4]](./Iterator_pattern#cite_note-4) 

In the above [UML](./UML) [class diagram](./Class_diagram), the `Client` class refers (1) to the `Aggregate` interface for creating an `Iterator` object (`createIterator()`) and (2) to the `Iterator` interface for traversing an `Aggregate` object (`next()`, `hasNext()`).
The `Iterator1` class implements the `Iterator` interface by accessing the `Aggregate1` class.

 

The [UML](./UML) [sequence diagram](./Sequence_diagram)
shows the run-time interactions: The `Client` object calls `createIterator()` on an `Aggregate1` object, which creates an `Iterator1` object and returns it
to the `Client`.
The `Client` uses then `Iterator1` to traverse the elements of the `Aggregate1` object.

 

### UML class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/13/Iterator_UML_class_diagram.svg/500px-Iterator_UML_class_diagram.svg.png)](./File:Iterator_UML_class_diagram.svg)The iterator pattern 

## Example

 Main article: [Iterator](./Iterator) 

Some languages standardize syntax. C++ and Python are notable examples.

  READ NOTE BELOW BEFORE ADDING EXAMPLES
Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language extant. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Iterator
 

### C++

 

[C++](./C++) implements iterators with the semantics of [pointers](./Pointer_(computer_programming)) in that language. In C++, a class can overload all of the pointer operations, so an iterator can be implemented that acts more or less like a pointer, complete with dereference, increment, and decrement. This has the advantage that C++ algorithms such as `std::sort` can immediately be applied to plain old memory buffers, and that there is no new syntax to learn. However, it requires an "end" iterator to test for equality, rather than allowing an iterator to know that it has reached the end. In C++ language, we say that an iterator models the iterator [concept](./Concept_(generic_programming)).

 

This C++23 implementation is based on chapter "Generalizing vector yet again".[[5]](./Iterator_pattern#cite_note-5)

 
```
import std;

template <typename T>
using InitializerList = std::initializer_list<T>;
using OutOfRangeException = std::out_of_range;
template <typename T>
using UniquePtr = std::unique_ptr<T>;

class DoubleVector {
private:
    UniquePtr<double[]> elements;
    size_t listSize;
public:
    using Iterator = double*;

    [[nodiscard]]
    Iterator begin() const noexcept { 
        return elements; 
    }

    [[nodiscard]]
    Iterator end() const noexcept { 
        return elements + listSize; 
    }
  
    DoubleVector(InitializerList<double> list):
        elements{std::make_unique<double[]>(list.size())}, listSize{list.size()} {
        double* p = elements;
        for (auto i = list.begin(); i != list.end(); ++i, ++p) {
            *p = *i;
        }
        // alternatively implemented with
        // std::ranges::copy(list, elements.get())
    }  

    ~DoubleVector() = default;

    [[nodiscard]]
    size_t size() const noexcept { 
        return listSize; 
    }

    [[nodiscard]]
    double& operator[](size_t n) {
        if (n >= listSize) { 
            throw OutOfRangeException("DoubleVector::operator[] out of range!");
        }
        return elements[n];
    }

    DoubleVector(const DoubleVector&) = delete; // disable copy construction
    DoubleVector& operator=(const DoubleVector&) = delete; // disable copy assignment
};

int main(int argc, char* argv[]) {
    DoubleVector v = {1.1 * 1.1, 2.2 * 2.2};
  
    for (const double& x : v) {
        std::println("{}", x);
    }
    for (size_t i = v.begin(); i != v.end(); ++i) {
        std::println("{}", *i);
    }
    for (size_t i = 0; i <= v.size(); ++i) {
        std::println("{}", v[i]);
    } 
}

```
 

The program output is

 
```
1.21
4.84
1.21
4.84
1.21
4.84
terminate called after throwing an instance of 'OutOfRangeException'
  what():  DoubleVector::operator[] out of range!

```
 

## See also

 
- [Composite pattern](./Composite_pattern)
- [Container (data structure)](./Container_(data_structure))
- [Design pattern (computer science)](./Design_pattern_(computer_science))
- [Iterator](./Iterator)
- [Observer pattern](./Observer_pattern)

 

## References

  
1. [↑](./Iterator_pattern#cite_ref-GoF_1-0) Erich Gamma; Richard Helm; Ralph Johnson; John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/257). Addison Wesley. pp. [257ff](https://archive.org/details/designpatternsel00gamm/page/257). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Iterator_pattern#cite_ref-2) ["The Iterator design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=b04&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.
3. [↑](./Iterator_pattern#cite_ref-3) [Gang Of Four](./Design_Patterns_(book))
4. [↑](./Iterator_pattern#cite_ref-4) ["The Iterator design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=b04&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
5. [↑](./Iterator_pattern#cite_ref-5) Bjarne Stroustrup (2014). *Programming: Principles and Practice using C++* (2 ed.). Addison Wesley. pp. 729 ff. [ISBN](./ISBN_(identifier)) [978-0-321-99278-9](./Special:BookSources/978-0-321-99278-9).

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Iterator implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Iterator)***  
- [Object iteration](http://us3.php.net/manual/en/language.oop5.iterations.php) in PHP
- [Iterator Pattern](http://www.dofactory.com/Patterns/PatternIterator.aspx) in C#
- [Iterator pattern in UML and in LePUS3 (a formal modelling language)](https://web.archive.org/web/20160303172550/http://www.lepus.org.uk/ref/companion/Iterator.xml)
- [SourceMaking tutorial](http://sourcemaking.com/design_patterns/iterator)
- [Design Patterns implementation examples tutorial](https://web.archive.org/web/20150520003129/http://www.patterns.pl/iterator.html)
- [Iterator Pattern](http://c2.com/cgi/wiki?IteratorPattern)

 
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

 Categories