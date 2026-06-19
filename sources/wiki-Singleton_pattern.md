---
source: https://en.wikipedia.org/wiki/Singleton_pattern
fetched: 2026-06-19
---

Design pattern in object-oriented software development [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fb/Singleton_UML_class_diagram.svg/250px-Singleton_UML_class_diagram.svg.png)](./File:Singleton_UML_class_diagram.svg)A [class diagram](./Class_diagram) exemplifying the singleton pattern. 

In [object-oriented programming](./Object-oriented_programming), the **singleton pattern** is a [software design pattern](./Software_design_pattern) that restricts the [instantiation](./Instantiation_(computer_science)) of a [class](./Class_(programming)) to a singular instance. It is one of the well-known ["Gang of Four" design patterns](./Design_Patterns), which describe how to solve recurring problems in object-oriented software.[[1]](./Singleton_pattern#cite_note-GoF-1) The pattern is useful when exactly one object is needed to coordinate actions across a system.

 

More specifically, the singleton pattern allows classes to:[[2]](./Singleton_pattern#cite_note-2)

 
- Ensure they only have one instance
- Provide easy access to that instance
- Control their instantiation (for example, hiding the [constructors](./Constructor_(object-oriented_programming)) of a [class](./Class_(programming)))

 

The term comes from the [mathematical concept of a singleton](./Singleton_(mathematics)).

 

## Common uses

 

Singletons are often preferred to [global variables](./Global_variables) because they do not pollute the global [namespace](./Namespace) (or their containing namespace). Additionally, they permit [lazy](./Lazy_evaluation) allocation and initialization, whereas global variables in many languages will always consume resources.[[1]](./Singleton_pattern#cite_note-GoF-1)[[3]](./Singleton_pattern#cite_note-devin-3)

 

The singleton pattern can also be used as a basis for other design patterns, such as the [abstract factory](./Abstract_factory_pattern), [factory method](./Factory_method_pattern), [builder](./Builder_pattern) and [prototype](./Prototype_pattern) patterns. [Facade](./Facade_pattern) objects are also often singletons because only one facade object is required.

 

[Logging](./Log_file) is a common real-world use case for singletons, because all objects that wish to log messages require a uniform point of access and conceptually write to a single source.[[4]](./Singleton_pattern#cite_note-rainsberger-4)

 

## Implementations

 

Implementations of the singleton pattern ensure that only one instance of the singleton class ever exists and typically provide [global access](./Global_scope) to that instance.

 

Typically, this is accomplished by:

 
- Declaring all [constructors](./Constructor_(object-oriented_programming)) of the class to be [private](./Private_member), which prevents it from being instantiated by other objects
- Providing a [static method](./Static_method) that returns a [reference](./Reference_(computer_science)) to the instance

 

The instance is usually stored as a private [static variable](./Static_variable); the instance is created when the variable is initialized, at some point before when the static method is first called.

 

This [C++23](./C++23) implementation is based on the pre-C++98 implementation in the book [*[citation needed](./Wikipedia:Citation_needed)*].

 
```
import std;

class Singleton {
private:
    Singleton() = default; // no public constructor
    ~Singleton() = default; // no public destructor
    inline static Singleton* instance = nullptr; // declaration class variable
    int value;
public:
    // defines a class operation that lets clients access its unique instance.
    static Singleton& getInstance() {
        if (!instance) {
            instance = new Singleton();
        }
        return *instance;
    }
  
    Singleton(const Singleton&) = delete("Copy construction disabled");
    Singleton& operator=(const Singleton&) = delete("Copy assignment disabled");

    static void destroy() {
        delete instance;
        instance = nullptr;
    }

    // existing interface goes here
    [[nodiscard]]
    int getValue() const noexcept {
        return value;
    }

    void setValue(int newValue) noexcept {
        value = newValue;
    }
};

int main() {
    Singleton::getInstance().setValue(42);
    std::println("value = {}", Singleton::getInstance().getValue());
    Singleton::destroy();
}

```
 

The program output is

 
```
value=42

```
 

This is an implementation of the Meyers singleton[[5]](./Singleton_pattern#cite_note-5) in C++11. The Meyers singleton has no destruct method. The program output is the same as above.

 
```
import std;

class Singleton {
private:
    Singleton() = default;
    ~Singleton() = default;
    int value;
public:
    static Singleton& getInstance() {
        static Singleton instance;
        return instance;
    }
  
    [[nodiscard]]
    int getValue() const noexcept {
        return value;
    }
  
    void setValue(int newValue) noexcept {
        value = newValue;
    }
};

int main() {
    Singleton::getInstance().setValue(42);
    std::println("value = {}", Singleton::getInstance().getValue());
}

```
 

### Lazy initialization

 

A singleton implementation may use [lazy initialization](./Lazy_initialization) in which the instance is created when the static method is first invoked. In [multithreaded](./Multithreading_(software)) programs, this can cause [race conditions](./Race_condition) that result in the creation of multiple instances. The following [Java 5+](./Java_version_history#Java_5) example[[6]](./Singleton_pattern#cite_note-6) is a [thread-safe](./Thread_safety) implementation, using lazy initialization with [double-checked locking](./Double-checked_locking).

 
```
public class Singleton {
    private static volatile Singleton instance = null;

    private Singleton() {}

    public static Singleton getInstance() {
        if (instance == null) {
            synchronized (Singleton.class) {
                if (instance == null) {
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}

```
 

## Criticism

 

Some consider the singleton to be an [anti-pattern](./Anti-pattern) that introduces [global state](./Global_variables) into an application, often unnecessarily. This introduces a potential dependency on the singleton by other objects, requiring analysis of implementation details to determine whether a dependency actually exists.[[7]](./Singleton_pattern#cite_note-google-7) This increased [coupling](./Coupling_(computer_programming)) can introduce difficulties with [unit testing](./Unit_testing).[[8]](./Singleton_pattern#cite_note-button-8) In turn, this places restrictions on any abstraction that uses the singleton, such as preventing [concurrent](./Concurrency_(computer_science)) use of multiple instances.[[8]](./Singleton_pattern#cite_note-button-8)[[9]](./Singleton_pattern#cite_note-9)[[10]](./Singleton_pattern#cite_note-googletesting.blogspot.com-10)

 

Singletons also violate the [single-responsibility principle](./Single-responsibility_principle) because they are responsible for enforcing their own uniqueness along with performing their normal functions.[[8]](./Singleton_pattern#cite_note-button-8)

 

## See also

 
- [Initialization-on-demand holder idiom](./Initialization-on-demand_holder_idiom)
- [Multiton pattern](./Multiton_pattern)
- [Software design pattern](./Software_design_pattern)

 

## References

  
1. [1](./Singleton_pattern#cite_ref-GoF_1-0) [2](./Singleton_pattern#cite_ref-GoF_1-1) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/127). Addison Wesley. pp. [127ff](https://archive.org/details/designpatternsel00gamm/page/127). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
2. [↑](./Singleton_pattern#cite_ref-2) ["The Singleton design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=c05&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-16.
3. [↑](./Singleton_pattern#cite_ref-devin_3-0) Soni, Devin (31 July 2019). ["What Is a Singleton?"](https://betterprogramming.pub/what-is-a-singleton-2dc38ca08e92). *BetterProgramming*. Retrieved 28 August 2021.
4. [↑](./Singleton_pattern#cite_ref-rainsberger_4-0) Rainsberger, J.B. (1 July 2001). ["Use your singletons wisely"](https://web.archive.org/web/20210224180356/https://www.ibm.com/developerworks/library/co-single/). IBM. Archived from [the original](https://www.ibm.com/developerworks/library/co-single/) on 24 February 2021. Retrieved 28 August 2021.
5. [↑](./Singleton_pattern#cite_ref-5) Scott Meyers (1997). *More Effective C++*. Addison Wesley. pp. 146 ff. [ISBN](./ISBN_(identifier)) [0-201-63371-X](./Special:BookSources/0-201-63371-X).
6. [↑](./Singleton_pattern#cite_ref-6) Eric Freeman, Elisabeth Freeman, Kathy Sierra, and Bert Bates (October 2004). ["5: One of a Kind Objects: The Singleton Pattern"](https://books.google.com/books?id=GGpXN9SMELMC&pg=PA182). *Head First Design Patterns* (First ed.). O'Reilly Media, Inc. p. 182. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
7. [↑](./Singleton_pattern#cite_ref-google_7-0) ["Why Singletons Are Controversial"](https://web.archive.org/web/20210506162753/https://code.google.com/archive/p/google-singleton-detector/wikis/WhySingletonsAreControversial.wiki). *Google Code Archive*. Archived from [the original](https://code.google.com/archive/p/google-singleton-detector/wikis/WhySingletonsAreControversial.wiki) on 6 May 2021. Retrieved 28 August 2021.
8. [1](./Singleton_pattern#cite_ref-button_8-0) [2](./Singleton_pattern#cite_ref-button_8-1) [3](./Singleton_pattern#cite_ref-button_8-2) Button, Brian (25 May 2004). ["Why Singletons are Evil"](https://web.archive.org/web/20210715184717/https://docs.microsoft.com/en-us/archive/blogs/scottdensmore/why-singletons-are-evil). *Being Scott Densmore*. Microsoft. Archived from [the original](https://docs.microsoft.com/en-us/archive/blogs/scottdensmore/why-singletons-are-evil) on 15 July 2021. Retrieved 28 August 2021.
9. [↑](./Singleton_pattern#cite_ref-9) Steve Yegge. [Singletons considered stupid](http://steve.yegge.googlepages.com/singleton-considered-stupid), September 2004
10. [↑](./Singleton_pattern#cite_ref-googletesting.blogspot.com_10-0) Hevery, Miško, "[Global State and Singletons](http://googletesting.blogspot.com/2008/11/clean-code-talks-global-state-and.html)", *Clean Code Talks*, 21 November 2008.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science/Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science/Design%20Patterns)* has a page on the topic of: ***[Singleton implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science/Design%20Patterns/Singleton)***    [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Singleton pattern](https://commons.wikimedia.org/wiki/Category:Singleton%20pattern).  
- Complete article "[Java Singleton Pattern Explained](https://howtodoinjava.com/design-patterns/creational/singleton-design-pattern-in-java/)"
- Four different ways to implement singleton in Java "[Ways to implement singleton in Java](https://web.archive.org/web/20150709155148/http://www.javaexperience.com/design-patterns-singleton-design-pattern/)"

 
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