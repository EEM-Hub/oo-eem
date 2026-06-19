---
source: https://en.wikipedia.org/wiki/Proxy_pattern
fetched: 2026-06-19
---

Software design pattern 

In [computer programming](./Computer_programming), the **proxy pattern** is a [software design pattern](./Software_design_pattern) which is a class functioning as an interface to something else.[*[vague](./Wikipedia:Vagueness)*] The proxy could interface to anything: a network connection, a large object in memory, a file, or some other resource that is expensive or impossible to duplicate. In short, a proxy is a wrapper or agent object that is being called by the client to access the real serving object behind the scenes. Use of the proxy can simply be [forwarding](./Forwarding_(object-oriented_programming)) to the real object, or can provide additional logic. In the proxy, extra functionality can be provided, for example caching when operations on the real object are resource intensive, or checking preconditions before operations on the real object are invoked. For the client, usage of a proxy object is similar to using the real object, because both implement the same interface.

 

## Overview

 

The proxy design pattern is one of the twenty-three well-known *[GoF design patterns](./Design_Patterns)* that describe how to solve recurring design problems to design flexible and reusable [object-oriented software](./Object-oriented_programming), that is, objects that are easier to implement, change, test, and reuse.[[1]](./Proxy_pattern#cite_note-GoF-1)

 

### Problem

 

The proxy design pattern is used to solve such problems:[[2]](./Proxy_pattern#cite_note-2)

 
- The access to an object should be controlled.
- Additional functionality should be provided when accessing an object.

 

When accessing sensitive objects, for example, it should be possible to check that clients have the needed access rights.

 

### Solution

 

Define a separate `Proxy` object that 

 
- can be used as a substitute for another object (`Subject`), and
- implements additional functionality to control the access to this subject.

 

This makes it possible to work through a `Proxy` object to perform additional functionality when accessing a subject, like checking the access rights of clients accessing a sensitive object.

 

To act as a substitute for a subject, a proxy must implement the `Subject` interface. Clients can't tell whether they work with a subject or its proxy.

 

See also the UML class and sequence diagram below.

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/6/6e/W3sDesign_Proxy_Design_Pattern_UML.jpg)](./File:W3sDesign_Proxy_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Proxy design pattern. 
[[3]](./Proxy_pattern#cite_note-3) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), 
the `Proxy` class implements the `Subject` interface so that it can act as substitute for `Subject` objects. It maintains a reference (`realSubject`) 
to the substituted object (`RealSubject`) so that it can forward requests to it
(`realSubject.operation()`). 

 

The sequence diagram 
shows the run-time interactions: The `Client` object 
works through a `Proxy` object that
controls the access to a `RealSubject` object.
In this example, the `Proxy` forwards the request to the `RealSubject`, which performs the request.

 

### Class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/75/Proxy_pattern_diagram.svg/500px-Proxy_pattern_diagram.svg.png)](./File:Proxy_pattern_diagram.svg)Proxy in [UML](./Unified_Modeling_Language) [![](//upload.wikimedia.org/wikipedia/commons/7/79/Proxy_pattern_in_LePUS3.gif)](./File:Proxy_pattern_in_LePUS3.gif)Proxy in [LePUS3](./Lepus3?action=edit&redlink=1) ([legend](https://web.archive.org/web/20180314162121/http://www.lepus.org.uk/ref/legend/legend.xml)) 

## Possible usage scenarios

 

### Remote proxy

 

In [distributed object communication](./Distributed_object_communication), a local object represents a remote object (one that belongs to a different address space). The local object is a proxy for the remote object, and method invocation on the local object results in [remote method invocation](./Remote_method_invocation) on the remote object. An example would be an [ATM](./Automated_teller_machine) implementation, where the ATM might hold proxy objects for bank information that exists in the remote server.

 

### Virtual proxy

 Further information: [Lazy loading](./Lazy_loading) 

In place of a complex or heavy object, a skeleton representation may be advantageous in some cases. When an underlying image is huge in size, it may be represented using a virtual proxy object, loading the real object on demand.

 

### Protection proxy

 

A protection proxy might be used to control access to a resource based on access rights.

 

## Example

 

The following is an example of the proxy design pattern in [C++](./C++):

 
```
import std;

using std::string;
using std::unique_ptr;

// Subject Interface
class Image {
public:
    virtual void display() const = 0;
    virtual ~Image() = default;
};

// Real Subject (expensive to load)
class RealImage : public Image {
private:
    string filename;
public:
    explicit RealImage(const string& file):
        filename{file} {
        loadFromDisk();
    }

    void display() const override {
        std::println("Displaying image: {}", filename);
    }

private:
    void loadFromDisk() const {
        std::println("Loading image from disk: {}", filename);
    }
};

// Proxy (controls access to RealImage)
class ProxyImage : public Image {
private:
    string filename;
    mutable unique_ptr<RealImage> realImage; // lazily created
public:
    explicit ProxyImage(const string& file):
        filename{file} {}

    void display() const override {
        if (!realImage) {
            std::println("(Proxy) Loading image on demand...");
            realImage = std::make_unique<RealImage>(filename);
        }
        realImage->display();
    }
};

// Client code
int main() {
    Image* img = new ProxyImage("photo.png");

    // First display (should load)
    img->display();

    // Second display (should use cached image)
    img->display();

    delete img;
    return 0;
}

```
 

## See also

 
- [Composite pattern](./Composite_pattern)
- [Decorator pattern](./Decorator_pattern)
- [Lazy initialization](./Lazy_initialization)

 

## References

  
1. [↑](./Proxy_pattern#cite_ref-GoF_1-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/207). Addison Wesley. pp. [207ff](https://archive.org/details/designpatternsel00gamm/page/207). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
2. [↑](./Proxy_pattern#cite_ref-2) ["The Proxy design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=s07&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.
3. [↑](./Proxy_pattern#cite_ref-3) ["The Proxy design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=s07&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Proxy implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Proxy)***    [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Proxy pattern](https://commons.wikimedia.org/wiki/Category:Proxy%20pattern).  
- Geary, David (February 22, 2002). ["Take control with the Proxy design pattern"](https://www.infoworld.com/article/2074068/take-control-with-the-proxy-design-pattern.html). *[JavaWorld](./JavaWorld)*. Retrieved 2020-07-20.
- [PerfectJPattern Open Source Project](https://perfectjpattern.sourceforge.net/dp-proxy.html), Provides componentized implementation of the Proxy Pattern in Java
- [Adapter vs. Proxy vs. Facade Pattern Comparison](https://web.archive.org/web/20120311202925/http://www.netobjectives.com/PatternRepository/index.php?title=AdapterVersusProxyVersusFacadePatternComparison) at the [Wayback Machine](./Wayback_Machine) (archived 2012-03-11)
- [Proxy Design Pattern](https://sourcemaking.com/design_patterns/proxy)
- [Proxy pattern C++ implementation example](https://web.archive.org/web/20141019100543/http://patterns.org.pl/proxy.html) at the [Wayback Machine](./Wayback_Machine) (archived 2014-10-19)
- [Proxy pattern description from the Portland Pattern Repository](https://wiki.c2.com/?ProxyPattern)

 
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