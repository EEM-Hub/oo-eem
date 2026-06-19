---
source: https://en.wikipedia.org/wiki/Composition_over_inheritance
fetched: 2026-06-19
---

Software design pattern [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/ba/UML_diagram_of_composition_over_inheritance.svg/500px-UML_diagram_of_composition_over_inheritance.svg.png)](./File:UML_diagram_of_composition_over_inheritance.svg)This diagram shows how the fly and sound behavior of an animal can be designed in a flexible way by using the composition over inheritance design principle.[[1]](./Composition_over_inheritance#cite_note-FHDPs-1) 

In [object-oriented programming](./Object-oriented_programming), **composition over inheritance** (sometimes **composition with forwarding** or **composite reuse**) is a common [design pattern](./Design_pattern) that tries to achieve [code reuse](./Code_reuse) without requiring [inheritance](./Inheritance_(object-oriented_programming)). Instead of having two child classes inherit functionality from a common parent, composition simulates inheritance by having the children include a copy of a "pseudo-parent" class as a field, which implements the functionality common to the two classes. Then, methods that would have been called on the child are instead called on the pseudo-parent, a technique called **method forwarding**.[[2]](./Composition_over_inheritance#cite_note-2)

 

Composition is generally used in languages where inheritance is unavailable or has an implementation that is considered inflexible, inconvenient, or inadequate (e.g. because a language lacks [multiple inheritance](./Multiple_inheritance)). However, many problems that are easily solved with inheritance are difficult to solve using only composition; as a result, inheritance and object composition typically work hand-in-hand, as discussed in the book *[Design Patterns](./Design_Patterns)* (1994).[[3]](./Composition_over_inheritance#cite_note-3)

 

## Example

 

### Inheritance

 

An example in [C++](./C++) follows:

 
```
import std;

using std::unique_ptr;
using std::vector;

class GameObject {
public:
    virtual void update() {
        // no-op
    }

    virtual void draw() const {
        // no-op
    }

    virtual void collide(vector<GameObject> objects) {
        // no-op
    }
};

class Visible : public GameObject {
private:
    unique_ptr<Model> model;
public:
    virtual void draw() const override {
        // code to draw a model at the position of this object
    }
};

class Solid : public GameObject {
public:
    virtual void collide(vector<GameObject> objects) override {
        // code to check for and react to collisions with other objects
    }
};

class Movable : public GameObject {
public:
    virtual void update() override {
        // code to update the position of this object
    }
};

```
 

Then, suppose we also have these concrete classes:

 
- class `Player` - which is `Solid`, `Movable` and `Visible`
- class `Cloud` - which is `Movable` and `Visible`, but not `Solid`
- class `Building` - which is `Solid` and `Visible`, but not `Movable`
- class `Trap` - which is `Solid`, but neither `Visible` nor `Movable`

 

Note that multiple inheritance is dangerous if not implemented carefully because it can lead to the [diamond problem](./Multiple_inheritance#The_diamond_problem). One solution to this is to create classes such as `VisibleAndSolid`, `VisibleAndMovable`, `VisibleAndSolidAndMovable`, etc. for every needed combination; however, this leads to a large amount of repetitive code. C++ uses [virtual inheritance](./Virtual_inheritance) to solve the diamond problem of multiple inheritance.

 

### Composition and interfaces

 

The C++ examples in this section demonstrate the principle of using composition and interfaces to achieve code reuse and polymorphism. Due to the C++ language not having a dedicated keyword to declare interfaces, the following C++ example uses inheritance from a pure [abstract base class](./Abstract_base_class). For most purposes, this is functionally equivalent to the interfaces provided in other languages, such as [Java](./Java_(programming_language))[[4]](./Composition_over_inheritance#cite_note-Bloch-4): 87  and [C#](./C_Sharp_(programming_language)).[[5]](./Composition_over_inheritance#cite_note-Price-5): 144 

 

Introduce an abstract class named `VisibilityDelegate`, with the subclasses `NotVisible` and `Visible`, which provides a means of drawing an object:

 
```
class VisibilityDelegate {
public:
    virtual void draw() const = 0;
};

class NotVisible : public VisibilityDelegate {
public:
    virtual void draw() const override {
        // no-op
    }
};

class Visible : public VisibilityDelegate {
public:
    virtual void draw() const override {
        // code to draw a model at the position of this object
    }
};

```
 

Introduce an abstract class named `UpdateDelegate`, with the subclasses `NotMovable` and `Movable`, which provides a means of moving an object:

 
```
class UpdateDelegate {
public:
    virtual void update() = 0;
};

class NotMovable : public UpdateDelegate {
public:
    virtual void update() override {
        // no-op
    }
};

class Movable : public UpdateDelegate {
public:
    virtual void update() override {
        // code to update the position of this object
    }
};

```
 

Introduce an abstract class named `CollisionDelegate`, with the subclasses `NotSolid` and `Solid`, which provides a means of colliding with an object:

 
```
import std;

using std::vector;

class CollisionDelegate {
public:
    virtual void collide(vector<GameObject> objects) = 0;
};

class NotSolid : public CollisionDelegate {
public:
    virtual void collide(vector<GameObject> objects) override {
        // no-op
    }
};

class Solid : public CollisionDelegate {
public:
    virtual void collide(vector<GameObject> objects) override {
        // code to check for and react to collisions with other objects
    }
};

```
 

Finally, introduce a class named `GameObject` with members to control its visibility (using a `VisibilityDelegate`), movability (using an `UpdateDelegate`), and solidity (using a `CollisionDelegate`). This class has methods which delegate to its members, e.g. `update()` simply calls a method on the `UpdateDelegate`:

 
```
import std;

using std::unique_ptr;
using std::vector;

class GameObject {
private:
    unique_ptr<VisibilityDelegate> visibilityDelegate;
    unique_ptr<UpdateDelegate> updateDelegate;
    unique_ptr<CollisionDelegate> collisionDelegate;
public:
    GameObject(VisibilityDelegate* v, UpdateDelegate* u, CollisionDelegate* c):
        visibilityDelegate{std::make_unique<VisibilityDelegate>(v)}, 
        updateDelegate{std::make_unique<UpdateDelegate>(u)}, 
        collisionDelegate{std::make_unique<CollisionDelegate>(c)} {}

    void update() {
        updateDelegate->update();
    }

    void draw() const {
        visibilityDelegate->draw();
    }

    void collide(vector<GameObject> objects) {
        collisionDelegate->collide(objects);
    }
};

```
 

Then, concrete classes would look like:

 
```
class Player : public GameObject {
public:
    Player(): 
        GameObject(new Visible(), new Movable(), new Solid()) {}

    // ...
};

class Smoke : public GameObject {
public:
    Smoke(): 
        GameObject(new Visible(), new Movable(), new NotSolid()) {}

    // ...
};

```
 

## Benefits

 

To favor composition over inheritance is a design principle that gives the design higher flexibility. It is more natural to build business-domain classes out of various components than trying to find commonality between them and creating a family tree. For example, an accelerator pedal and a steering wheel share very few common [traits](./Trait_(computer_programming)), yet both are vital components in a car. What they can do and how they can be used to benefit the car are easily defined. Composition also provides a more stable business domain in the long term as it is less prone to the quirks of the family members. In other words, it is better to compose what an object can do (*[has-a](./Has-a)*) than extend what it is (*[is-a](./Is-a)*).[[1]](./Composition_over_inheritance#cite_note-FHDPs-1)

 

Initial design is simplified by identifying system object behaviors in separate interfaces instead of creating a hierarchical relationship to distribute behaviors among business-domain classes via inheritance. This approach more easily accommodates future requirements changes that would otherwise require a complete restructuring of business-domain classes in the inheritance model. Additionally, it avoids problems often associated with relatively minor changes to an inheritance-based model that includes several generations of classes.
Composition relation is more flexible as it may be changed on runtime, while sub-typing relations are static and need recompilation in many languages.

 

Some languages, notably [Go](./Go_(programming_language))[[6]](./Composition_over_inheritance#cite_note-6) and [Rust](./Rust_(programming_language)),[[7]](./Composition_over_inheritance#cite_note-7) use type composition exclusively.

 

## Drawbacks

 

One common drawback of using composition instead of inheritance is that methods being provided by individual components may have to be implemented in the derived type, even if they are only [forwarding methods](./Forwarding_(object-oriented_programming)) (this is true in most programming languages, but not all; see [§ Avoiding drawbacks](./Composition_over_inheritance#Avoiding_drawbacks)). In contrast, inheritance does not require all of the base class's methods to be re-implemented within the derived class. Rather, the derived class only needs to implement (override) the methods having different behavior than the base class methods. This can require significantly less programming effort if the base class contains many methods providing default behavior and only a few of them need to be overridden within the derived class.

 

Thus, the pattern of "composition over inheritance" should not be interpreted as a literal mantra or law, but rather a selectively applicable suggestion to be used where appropriate.

 

For example, in the C# code below, the variables and methods of the `Employee` base class are inherited by the `HourlyEmployee` and `SalariedEmployee` derived subclasses. Only the `Pay()` method needs to be implemented (specialized) by each derived subclass. The other methods are implemented by the base class itself, and are shared by all of its derived subclasses; they do not need to be re-implemented (overridden) or even mentioned in the subclass definitions.

 

[![UML class Employee.svg](//upload.wikimedia.org/wikipedia/commons/thumb/8/89/UML_class_Employee.svg/500px-UML_class_Employee.svg.png)](./File:UML_class_Employee.svg)

 
```
// Base class
public abstract class Employee
{
    // Properties
    protected string Name { get; set; }
    protected int ID { get; set; }
    protected decimal PayRate { get; set; }
    protected int HoursWorked { get; }

    // Get pay for the current pay period
    public abstract decimal Pay();
}

// Derived subclass
public class HourlyEmployee : Employee
{
    // Get pay for the current pay period
    public override decimal Pay()
    {
        // Time worked is in hours
        return HoursWorked * PayRate;
    }
}

// Derived subclass
public class SalariedEmployee : Employee
{
    // Get pay for the current pay period
    public override decimal Pay()
    {
        // Pay rate is annual salary instead of hourly rate
        return HoursWorked * PayRate / 2087;
    }
}

```
 

### Avoiding drawbacks

 

This drawback can be avoided by using [traits](./Traits_(computer_science)), [mixins](./Mixin), (type) [embedding](./Embedding), or [protocol](./Protocol_(object-oriented_programming)) extensions.

 

Some languages provide specific means to mitigate this:

 
- [C#](./C_Sharp_(programming_language)) provides default interface methods since version 8.0 which allows to define body to interface member.[[8]](./Composition_over_inheritance#cite_note-8)[[5]](./Composition_over_inheritance#cite_note-Price-5): 28–29 [[9]](./Composition_over_inheritance#cite_note-Skeet-9): 38 [[10]](./Composition_over_inheritance#cite_note-Albahari-10): 466–468 
- [C++](./C++) allows `virtual` methods (for specifying a [virtual function](./Virtual_function)) to have default implementations.[[11]](./Composition_over_inheritance#cite_note-11)
- [D](./D_(programming_language)) provides an explicit "alias this" declaration within a type can forward into it every method and member of another contained type.[[12]](./Composition_over_inheritance#cite_note-12)
- [Dart](./Dart_(programming_language)) provides mixins with default implementations that can be shared.
- [Go](./Go_(programming_language)) type embedding avoids the need for forwarding methods.[[13]](./Composition_over_inheritance#cite_note-13)
- [Java](./Java_(programming_language)) provides default interface methods since version 8.[[4]](./Composition_over_inheritance#cite_note-Bloch-4): 104  Project Lombok[[14]](./Composition_over_inheritance#cite_note-14) supports delegation using the `@Delegate` annotation on the field, instead of copying and maintaining the names and types of all the methods from the delegated field.[[15]](./Composition_over_inheritance#cite_note-15)
- [Julia](./Julia_(programming_language)) macros can be used to generate forwarding methods. Several implementations exist such as Lazy.jl[[16]](./Composition_over_inheritance#cite_note-16) and TypedDelegation.jl.[[17]](./Composition_over_inheritance#cite_note-17)[[18]](./Composition_over_inheritance#cite_note-18)
- [Kotlin](./Kotlin_(programming_language)) includes the delegation pattern in the language syntax.[[19]](./Composition_over_inheritance#cite_note-19)
- [PHP](./PHP) supports [traits](./Traits_(computer_science)), since PHP 5.4.[[20]](./Composition_over_inheritance#cite_note-20)
- [Raku](./Raku_(programming_language)) provides a `handles` trait to facilitate method forwarding.[[21]](./Composition_over_inheritance#cite_note-21)
- [Rust](./Rust_(programming_language)) provides traits with default implementations.
- [Scala](./Scala_(programming_language)) (since version 3) provides an "export" clause to define aliases for selected members of an object.[[22]](./Composition_over_inheritance#cite_note-22)
- [Swift](./Swift_(programming_language)) extensions can be used to define a default implementation of a protocol on the protocol itself, rather than within an individual type's implementation.[[23]](./Composition_over_inheritance#cite_note-23)

 

## Empirical studies

 

A 2013 study of 93 open source Java programs (of varying size) found that:

 

While there is not huge opportunity to replace inheritance with composition (...), the opportunity is significant (median of 2% of uses [of inheritance] are only internal reuse, and a further 22% are only external or internal reuse).

Our results suggest there is no need for concern regarding abuse of inheritance (at least in open-source Java software), but they do highlight the question regarding use of composition versus inheritance. If there are significant costs associated with using inheritance when composition could be used, then our results suggest there is some cause for concern.

— Tempero *et al.*, "What programmers do with inheritance in Java"[[24]](./Composition_over_inheritance#cite_note-24)

 

## See also

 
- [Delegation pattern](./Delegation_pattern)
- [Liskov substitution principle](./Liskov_substitution_principle)
- [Object-oriented design](./Object-oriented_design)
- [Object composition](./Object_composition)
- [Role-oriented programming](./Role-oriented_programming)
- [State pattern](./State_pattern)
- [Strategy pattern](./Strategy_pattern)

 

## References

  
1. [1](./Composition_over_inheritance#cite_ref-FHDPs_1-0) [2](./Composition_over_inheritance#cite_ref-FHDPs_1-1) Freeman, Eric; Robson, Elisabeth; Sierra, Kathy; Bates, Bert (2004). [*Head First Design Patterns*](https://archive.org/details/headfirstdesignp00free_633). O'Reilly. p. [23](https://archive.org/details/headfirstdesignp00free_633/page/n57). [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6).
2. [↑](./Composition_over_inheritance#cite_ref-2) Knoernschild, Kirk (2002). [*Java Design - Objects, UML, and Process: 1.1.5 Composite Reuse Principle (CRP)*](https://books.google.com/books?id=4pjbgVHzomsC&q=composite+reuse+principle&pg=PA17). Addison-Wesley Inc. [ISBN](./ISBN_(identifier)) [9780201750447](./Special:BookSources/9780201750447). Retrieved 2012-05-29.
3. [↑](./Composition_over_inheritance#cite_ref-3) [Gamma, Erich](./Erich_Gamma); Helm, Richard; [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). *[Design Patterns: Elements of Reusable Object-Oriented Software](./Design_Patterns)*. [Addison-Wesley](./Addison-Wesley). p. [20](https://archive.org/details/designpatternsel00gamm/page/20). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2). [OCLC](./OCLC_(identifier)) [31171684](https://search.worldcat.org/oclc/31171684). 
4. [1](./Composition_over_inheritance#cite_ref-Bloch_4-0) [2](./Composition_over_inheritance#cite_ref-Bloch_4-1) Bloch, Joshua (2018). *"Effective Java: Programming Language Guide"* (third ed.). Addison-Wesley. [ISBN](./ISBN_(identifier)) [978-0134685991](./Special:BookSources/978-0134685991).
5. [1](./Composition_over_inheritance#cite_ref-Price_5-0) [2](./Composition_over_inheritance#cite_ref-Price_5-1) Price, Mark J. (2022). *C# 8.0 and .NET Core 3.0 – Modern Cross-Platform Development: Build Applications with C#, .NET Core, Entity Framework Core, ASP.NET Core, and ML.NET Using Visual Studio Code*. Packt. [ISBN](./ISBN_(identifier)) [978-1-098-12195-2](./Special:BookSources/978-1-098-12195-2).
6. [↑](./Composition_over_inheritance#cite_ref-6) Pike, Rob (2012-06-25). ["Less is exponentially more"](https://commandcenter.blogspot.com/2012/06/less-is-exponentially-more.html). Retrieved 2016-10-01.
7. [↑](./Composition_over_inheritance#cite_ref-7) ["Characteristics of Object-Oriented Languages - The Rust Programming Language"](https://doc.rust-lang.org/stable/book/ch17-01-what-is-oo.html#inheritance-as-a-type-system-and-as-code-sharing). *doc.rust-lang.org*. Retrieved 2022-10-10.
8. [↑](./Composition_over_inheritance#cite_ref-8) ["What's new in C# 8.0"](https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-8#default-interface-methods). *Microsoft Docs*. Microsoft. Retrieved 2019-02-20.
9. [↑](./Composition_over_inheritance#cite_ref-Skeet_9-0) Skeet, Jon (23 March 2019). *C# in Depth*. Manning. [ISBN](./ISBN_(identifier)) [978-1617294532](./Special:BookSources/978-1617294532).
10. [↑](./Composition_over_inheritance#cite_ref-Albahari_10-0) Albahari, Joseph (2022). *C# 10 in a Nutshell*. O'Reilly. [ISBN](./ISBN_(identifier)) [978-1-098-12195-2](./Special:BookSources/978-1-098-12195-2).
11. [↑](./Composition_over_inheritance#cite_ref-11) ["virtual function specifier"](https://en.cppreference.com/w/cpp/language/virtual.html). *cppreference.com*. cppreference. Retrieved 20 October 2025.
12. [↑](./Composition_over_inheritance#cite_ref-12) ["Alias This"](https://dlang.org/spec/class.html#alias-this). *D Language Reference*. Retrieved 2019-06-15.
13. [↑](./Composition_over_inheritance#cite_ref-13) ["*(Type)* Embedding"](https://golang.org/doc/effective_go.html#embedding). *The Go Programming Language Documentation*. Retrieved 2019-05-10.
14. [↑](./Composition_over_inheritance#cite_ref-14) ["Project Lombok"](https://projectlombok.org). *projectlombok.org*. Retrieved 2026-05-16.
15. [↑](./Composition_over_inheritance#cite_ref-15) ["@Delegate"](https://projectlombok.org/features/experimental/Delegate). *Project Lombok*. Retrieved 2018-07-11.
16. [↑](./Composition_over_inheritance#cite_ref-16) ["MikeInnes/Lazy.jl"](https://github.com/MikeInnes/Lazy.jl). *[GitHub](./GitHub)*.
17. [↑](./Composition_over_inheritance#cite_ref-17) ["JeffreySarnoff/TypedDelegation.jl"](https://github.com/JeffreySarnoff/TypedDelegation.jl). *[GitHub](./GitHub)*.
18. [↑](./Composition_over_inheritance#cite_ref-18) ["Method forwarding macro"](https://discourse.julialang.org/t/method-forwarding-macro/23355). *JuliaLang*. 20 April 2019. Retrieved 18 August 2022.
19. [↑](./Composition_over_inheritance#cite_ref-19) ["Delegated Properties"](https://kotlinlang.org/docs/reference/delegated-properties.html). *Kotlin Reference*. JetBrains. Retrieved 2018-07-11.
20. [↑](./Composition_over_inheritance#cite_ref-20) ["PHP: Traits"](https://www.php.net/manual/en/language.oop5.traits.php). *www.php.net*. Retrieved 23 February 2023.
21. [↑](./Composition_over_inheritance#cite_ref-21) ["Type system"](https://docs.raku.org/language/typesystem#index-entry-handles_trait-handles). *docs.raku.org*. Retrieved 18 August 2022.
22. [↑](./Composition_over_inheritance#cite_ref-22) ["Export Clauses"](https://docs.scala-lang.org/scala3/reference/other-new-features/export.html). *Scala Documentation*. Retrieved 2021-10-06.
23. [↑](./Composition_over_inheritance#cite_ref-23) ["Protocols"](https://docs.swift.org/swift-book/LanguageGuide/Protocols.html). *The Swift Programming Language*. Apple Inc. Retrieved 2018-07-11.
24. [↑](./Composition_over_inheritance#cite_ref-24) Tempero, Ewan; Yang, Hong Yul; Noble, James (2013). ["What programmers do with inheritance in Java"](https://www.cs.auckland.ac.nz/~ewan/qualitas/studies/inheritance/TemperoYangNobleECOOP2013-pre.pdf) (PDF). *ECOOP 2013 – Object-Oriented Programming*. ECOOP 2013–Object-Oriented Programming. Lecture Notes in Computer Science. Vol. 7920. pp. 577–601. [doi](./Doi_(identifier)):[10.1007/978-3-642-39038-8_24](https://doi.org/10.1007%2F978-3-642-39038-8_24). [ISBN](./ISBN_(identifier)) [978-3-642-39038-8](./Special:BookSources/978-3-642-39038-8).

 
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