---
source: https://en.wikipedia.org/wiki/Composite_pattern
fetched: 2026-06-19
---

Design pattern in software engineering 

In [software engineering](./Software_engineering), the **composite pattern** is a partitioning [design pattern](./Design_pattern_(computer_science)). The composite pattern describes a group of objects that are treated the same way as a single instance of the same type of object. The intent of a composite is to "compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets clients treat individual objects and compositions uniformly.[[1]](./Composite_pattern#cite_note-GangOfFour-1)

 

## Overview

 
|  | This section mayrequirecleanupto meet Wikipedia'squality standards. The specific problem is:The subsection headersshould not redundantly refer back to the article title and should not be phrased as questions. But do these headers even accurately describe the subsection content? If yes, changing them to "Problems solved" and "Solution described" may be appropriate.Please helpimprove this sectionif you can.(May 2024)(Learn how and when to remove this message) |
| --- | --- |

 

The Composite[[2]](./Composite_pattern#cite_note-GoF-2)
design pattern is one of the twenty-three well-known 
*[GoF design patterns](./Design_Patterns)* 
that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

### Problems

 

The Composite pattern solves these problems:

 
- Represent a part-whole hierarchy so that clients can treat part and whole objects uniformly.
- Represent a part-whole hierarchy as tree structure.

 

When defining (1) `Part` objects and (2) `Whole` objects that act as containers for `Part` objects, clients must treat them separately, which complicates client code.[[3]](./Composite_pattern#cite_note-3)

 

### Solution

 
- Define a unified `Component` interface for part (`Leaf`) objects and whole (`Composite`) objects.
- Individual `Leaf` objects implement the `Component` interface directly, and `Composite` objects forward requests to their child components.

 

This enables clients to work through the `Component` interface to treat `Leaf` and `Composite` objects uniformly:
`Leaf` objects perform a request directly,
and `Composite` objects 
forward the request to their child components recursively downwards the tree structure.
This makes client classes easier to implement, change, test, and reuse.

 

See also the UML class and object diagram below.

 

## Motivation

 

When dealing with Tree-structured data, programmers often have to discriminate between a leaf-node and a branch. This makes code more complex, and therefore, more error prone. The solution is an interface that allows treating complex and primitive objects uniformly. In [object-oriented programming](./Object-oriented_programming), a composite is an object designed as a composition of one-or-more similar objects, all exhibiting similar functionality. This is known as a "[has-a](./Has-a)" relationship between objects.[[4]](./Composite_pattern#cite_note-4) The key concept is that you can manipulate a single instance of the object just as you would manipulate a group of them. The operations you can perform on all the composite objects often have a [least common denominator](./Least_common_denominator) relationship. For example, if defining a system to portray grouped shapes on a screen, it would be useful to define resizing a group of shapes to have the same effect (in some sense) as resizing a single shape.

 

## When to use

 

Composite should be used when clients ignore the difference between compositions of objects and individual objects.[[1]](./Composite_pattern#cite_note-GangOfFour-1)  If programmers find that they are using multiple objects in the same way, and often have nearly identical code to handle each of them, then composite is a good choice; it is less complex in this situation to treat primitives and composites as homogeneous.

 

## Structure

 

### UML class and object diagram

 [![](//upload.wikimedia.org/wikipedia/commons/6/65/W3sDesign_Composite_Design_Pattern_UML.jpg)](./File:W3sDesign_Composite_Design_Pattern_UML.jpg)A sample UML class and object diagram for the Composite design pattern. [[5]](./Composite_pattern#cite_note-5) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), the `Client` class doesn't refer to the `Leaf` and `Composite` classes directly (separately).
Instead, the `Client` refers to the common `Component` interface and can treat `Leaf` and `Composite` uniformly.

The `Leaf` class has no children and implements the `Component` interface directly.

The `Composite` class maintains a container of child
`Component` objects (`children`) and forwards requests
to these `children` (`for each child in children: child.operation()`).

 

The object collaboration diagram 
shows the run-time interactions: In this example, the `Client` object sends a request to the top-level `Composite` object (of type `Component`) in the tree structure.
The request is forwarded to (performed on) all child `Component` objects 
(`Leaf` and `Composite` objects) downwards the tree structure.

 Defining Child-Related Operations [![](//upload.wikimedia.org/wikipedia/commons/3/39/W3sDesign_Composite_Design_Pattern_Type_Safety_UML.jpg)](./File:W3sDesign_Composite_Design_Pattern_Type_Safety_UML.jpg)Defining child-related operations in the Composite design pattern. [[6]](./Composite_pattern#cite_note-6) 

There are two design variants for defining and implementing child-related operations
like adding/removing a child component to/from the container (`add(child)/remove(child)`) and accessing a child component (`getChild()`):

 
- *Design for transparency:* Child-related operations are defined in the `Component` interface. This enables clients to treat `Leaf` and `Composite` objects uniformly. But [type safety](./Type_safety) is lost because clients can perform child-related operations on `Leaf` objects.
- *Design for type safety:* Child-related operations are defined only in the `Composite` class. Clients must treat `Leaf` and `Composite` objects differently. But type safety is gained because clients *cannot* perform child-related operations on `Leaf` objects.

 

The GoF authors present a variant of the Composite design pattern that emphasizes *transparency* over *type safety* and discuss the tradeoffs of the two approaches.[[1]](./Composite_pattern#cite_note-GangOfFour-1)

 

The type-safe approach is particularly palatable if the composite structure is fixed post construction: the construction code does not require transparency because it needs to know the types involved in order to construct the composite. If downstream, the code does not need to modify the structure, then the child manipulation operations do not need to be present on the `Component` interface.

 

### UML class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/5a/Composite_UML_class_diagram_%28fixed%29.svg/960px-Composite_UML_class_diagram_%28fixed%29.svg.png)](./File:Composite_UML_class_diagram_(fixed).svg)Composite pattern in [UML](./Unified_Modeling_Language). Component 
- is the abstraction for all components, including composite ones
- declares the interface for objects in the composition
- (optional) defines an interface for accessing a component's parent in the recursive structure, and implements it if that's appropriate

 Leaf 
- represents leaf objects in the composition
- implements all Component methods

 Composite 
- represents a composite Component (component having children)
- implements methods to manipulate children
- implements all Component methods, generally by delegating them to its children

 [![](//upload.wikimedia.org/wikipedia/commons/a/a9/Composite_pattern_in_LePUS3.png)](./File:Composite_pattern_in_LePUS3.png)Composite pattern in [LePUS3](./Lepus3?action=edit&redlink=1). 

## Variation

 

As it is described in [Design Patterns](./Design_Patterns), the pattern also involves including the child-manipulation methods in the main Component interface, not just the Composite subclass. More recent descriptions sometimes omit these methods.[[7]](./Composite_pattern#cite_note-7)

 

## Example

  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Composite  

This C++23 implementation is based on the pre C++98 implementation in the book.

 
```
import std;

using std::runtime_error;
using std::shared_ptr;
using std::string;
using std::unique_ptr;
using std::vector;

// Component object
// declares the interface for objects in the composition.
class Equipment {
private:
    string name;
    double netPrice;
protected:
    Equipment() = default;

    explicit Equipment(const string& name): 
        name{name}, netPrice{0} {}
public:
    // implements default behavior for the interface common to all classes, as appropriate.
    [[nodiscard]]
    virtual const string& getName() const noexcept {
        return name;
    }

    virtual void setName(const string& name) noexcept {
        this->name = name;
    }

    [[nodiscard]]
    virtual double getNetPrice() const noexcept {
        return netPrice;
    }

    virtual void setNetPrice(double netPrice) noexcept {
        this->netPrice = netPrice;
    }

    // declares an interface for accessing and managing its child components.
    virtual void add(shared_ptr<Equipment>) = 0;
    virtual void remove(shared_ptr<Equipment>) = 0;
    virtual ~Equipment() = default;
};

// Composite object
// defines behavior for components having children.
class CompositeEquipment: public Equipment {
private:
    // stores child components.
    using EquipmentList = vector<shared_ptr<Equipment>>;
    EquipmentList equipments;
protected:
    CompositeEquipment() = default;

    explicit CompositeEquipment(const string& name):
        Equipment(name), equipments{EquipmentList()} {}
public:
    // implements child-related operations in the Component interface.
    [[nodiscard]]
    virtual double getNetPrice() const noexcept override {
        double total = Equipment::getNetPrice();
        for (const Equipment& i: equipments) {
            total += i->getNetPrice();
        }
        return total;
    }

    virtual void add(shared_ptr<Equipment> equipment) override {
        equipments.push_back(equipment.get());
    }

    virtual void remove(shared_ptr<Equipment> equipment) override {
        equipments.remove(equipment.get());
    }
};

// Leaf object
// represents leaf objects in the composition.
class FloppyDisk: public Equipment {
public:
    explicit FloppyDisk(const String& name):
        Equipment(name) {}

    // A leaf has no children.
    void add(shared_ptr<Equipment>) override {
        throw runtime_error("FloppyDisk::add() cannot be called!");
    }

    void remove(shared_ptr<Equipment>) override {
        throw runtime_error("FloppyDisk::remove() cannot be called!");
    }
};

class Chassis: public CompositeEquipment {
public:
    explicit Chassis(const string& name): 
        CompositeEquipment(name) {}
};

int main() {
    shared_ptr<FloppyDisk> fd1 = std::make_shared<FloppyDisk>("3.5in Floppy");
    fd1->setNetPrice(19.99);
    std::println("{}: netPrice = {}", fd1->getName(), fd1->getNetPrice);

    shared_ptr<FloppyDisk> fd2 = std::make_shared<FloppyDisk>("5.25in Floppy");
    fd2->setNetPrice(29.99);
    std::println("{}: netPrice = {}", fd2->getName(), fd2->getNetPrice);

    unique_ptr<Chassis> ch = std::make_unique<Chassis>("PC Chassis");
    ch->setNetPrice(39.99);
    ch->add(fd1);
    ch->add(fd2);
    std::println("{}: netPrice = {}", ch->getName(), ch->getNetPrice);

    fd2->add(fd1);
}

```
 

The program output is

 
```
3.5in Floppy: netPrice=19.99
5.25in Floppy: netPrice=29.99
PC Chassis: netPrice=89.97
terminate called after throwing an instance of 'std::runtime_error'
  what():  FloppyDisk::add

```
 

## See also

 
- [Perl Design Patterns Book](./Perl_Design_Patterns_Book)
- [Mixin](./Mixin)
- [Law of Demeter](./Law_of_Demeter)

 

## References

  
1. [1](./Composite_pattern#cite_ref-GangOfFour_1-0) [2](./Composite_pattern#cite_ref-GangOfFour_1-1) [3](./Composite_pattern#cite_ref-GangOfFour_1-2) Gamma, Erich; Richard Helm; Ralph Johnson; John M. Vlissides (1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/395). Addison-Wesley. pp. [395](https://archive.org/details/designpatternsel00gamm/page/395). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Composite_pattern#cite_ref-GoF_2-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/163). Addison Wesley. pp. [163ff](https://archive.org/details/designpatternsel00gamm/page/163). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
3. [↑](./Composite_pattern#cite_ref-3) ["The Composite design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=s03&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.
4. [↑](./Composite_pattern#cite_ref-4) Scott Walters (2004). [*Perl Design Patterns Book*](https://web.archive.org/web/20160308182256/http://perldesignpatterns.com/?CompositePattern). Archived from [the original](http://perldesignpatterns.com/?CompositePattern) on 2016-03-08. Retrieved 2010-01-18.
5. [↑](./Composite_pattern#cite_ref-5) ["The Composite design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=s03&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
6. [↑](./Composite_pattern#cite_ref-6) ["The Composite design pattern - Implementation"](http://w3sdesign.com/?gr=s03&ugr=implem). *w3sDesign.com*. Retrieved 2017-08-12.
7. [↑](./Composite_pattern#cite_ref-7) Geary, David (13 September 2002). ["A look at the Composite design pattern"](https://www.infoworld.com/article/2074564/a-look-at-the-composite-design-pattern.html). Java Design Patterns. *[JavaWorld](./JavaWorld)*. Retrieved 2020-07-20.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Composite implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Composite)***  
- [Composite Pattern](http://designpattern.co.il/Composite.html) implementation in Java
- [Composite pattern description from the Portland Pattern Repository](https://wiki.c2.com/?CompositePattern)
- [Composite pattern in UML and in LePUS3, a formal modelling language](https://web.archive.org/web/20151002170520/http://www.lepus.org.uk/ref/companion/Composite.xml)
- [Class::Delegation on CPAN](https://search.cpan.org/dist/Class-Delegation/lib/Class/Delegation.pm)
- ["The End of Inheritance: Automatic Run-time Interface Building for Aggregated Objects"](http://aspn.activestate.com/ASPN/Cookbook/Python/Recipe/149878) by [Paul Baranowski](./Paul_Baranowski?action=edit&redlink=1)
- [PerfectJPattern Open Source Project](https://perfectjpattern.sourceforge.net/dp-composite.html), Provides componentized implementation of the Composite Pattern in Java
- [](https://web.archive.org/web/20090531030742/http://www.theresearchkitchen.com/blog/archives/57) A persistent Java-based implementation
- [Composite Design Pattern](http://sourcemaking.com/design_patterns/composite)

 
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