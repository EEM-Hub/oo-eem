---
source: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
fetched: 2026-06-19
---

Programming pattern 

In [object-oriented design](./Object-oriented_design), the **chain-of-responsibility pattern** is a [behavioral](./Behavioral_pattern) [design pattern](./Design_pattern_(computer_science)) consisting of a source of [command objects](./Command_pattern) and a series of **processing objects**.[[1]](./Chain-of-responsibility_pattern#cite_note-1)  Each processing object contains logic that defines the types of command objects that it can handle; the rest are passed to the next processing object in the chain. A mechanism also exists for adding new processing objects to the end of this chain.

 

In a variation of the standard chain-of-responsibility model, some handlers may act as [dispatchers](./Dynamic_dispatch), capable of sending commands out in a variety of directions, forming a *tree of responsibility*. In some cases, this can occur recursively, with processing objects calling higher-up processing objects with commands that attempt to solve some smaller part of the problem; in this case recursion continues until the command is processed, or the entire tree has been explored. An [XML](./XML) [interpreter](./Interpreter_(computing)) might work in this manner.

 

This pattern promotes the idea of [loose coupling](./Loose_coupling).

 

The chain-of-responsibility pattern is structurally nearly identical to the [decorator pattern](./Decorator_pattern), the difference being that for the decorator, all classes handle the request, while for the chain of responsibility, exactly one of the classes in the chain handles the request. This is a strict definition of the Responsibility concept in the [*Gang of Four Design Patterns* book](./Design_Patterns). However, many implementations (such as loggers below, or UI event handling, or servlet filters in Java, etc.) allow several elements in the chain to take responsibility.

 

## Overview

 

The Chain of Responsibility[[2]](./Chain-of-responsibility_pattern#cite_note-GoF-2)
design pattern is one of the twenty-three well-known 
Gang of Four design patterns that describe common solutions to recurring design problems when designing flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

### Problems

 

The Chain of Responsibility pattern solves:

 
- Coupling the sender of a request to its receiver should be avoided.
- It should be possible that more than one receiver can handle a request.

 

Implementing a request directly within the class that sends the request is inflexible
because it couples the class to a particular receiver and makes it impossible to support multiple receivers.[[3]](./Chain-of-responsibility_pattern#cite_note-3)

 

### Solution

 
- Define a chain of receiver objects having the responsibility, depending on run-time conditions, to either handle a request or forward it to the next receiver on the chain (if any).

 

This enables us to send a request to a chain of receivers
without having to know which one handles the request.
The request gets passed along the chain until a receiver handles the request.
The sender of a request is no longer coupled to a particular receiver.

 

See also the UML class and sequence diagram below.

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/6/6a/W3sDesign_Chain_of_Responsibility_Design_Pattern_UML.jpg)](./File:W3sDesign_Chain_of_Responsibility_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Chain of Responsibility design pattern.[[4]](./Chain-of-responsibility_pattern#cite_note-4) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), the `Sender` class doesn't refer to a particular receiver class directly.
Instead, `Sender` refers to the `Handler` interface for handling a request (`handler.handleRequest()`), which makes the `Sender` independent of which receiver handles the request.
The `Receiver1`, `Receiver2`, and `Receiver3` classes implement the `Handler` interface by either handling or forwarding a request (depending on run-time conditions).

The [UML](./Unified_Modeling_Language) [sequence diagram](./Sequence_diagram)
shows the run-time interactions: In this example, the `Sender` object calls `handleRequest()` on the `receiver1` object (of type `Handler`). 
The `receiver1` forwards the request to `receiver2`, which in turn forwards the request to `receiver3`, which handles (performs) the request.

 

## Example

  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Chain_of_responsibility  

This C++23 implementation is based on the pre C++98 implementation in the book.[[5]](./Chain-of-responsibility_pattern#cite_note-5)

 
```
import std;

using std::shared_ptr;

enum class Topic: char {
    NO_HELP_TOPIC = 0,
    PRINT_TOPIC = 1,
    PAPER_ORIENTATION = 2,
    APPLICATION_TOPIC = 3,
    PAPER_ORIENTATION_TOPIC = 4,
    // more topics
};

// Abstract handler
// defines an interface for handling requests.
class HelpHandler {
private:
    HelpHandler* successor;
    Topic topic;
public:
    explicit HelpHandler(HelpHandler* h = nullptr, Topic t = Topic::NO_HELP_TOPIC):
        successor{h}, topic{t} {}

    [[nodiscard]]
    virtual bool hasHelp() const noexcept {
        return topic != Topic::NO_HELP_TOPIC;
    }

    virtual void setHandler(HelpHandler* h, Topic t) {
        successor = h;
        topic = t;
    }

    virtual void handleHelp() const {
        std::println("HelpHandler::handleHelp called");
        // (optional) implements the successor link.
        if (successor) {
            successor->handleHelp();
        }
    }

    virtual ~HelpHandler() = default;

    HelpHandler(const HelpHandler&) = delete;
    HelpHandler& operator=(const HelpHandler&) = delete;
};

class Widget: public HelpHandler {
private:
    Widget* parent;
protected:
    explicit Widget(Widget* w, Topic t = Topic::NO_HELP_TOPIC):
        HelpHandler(w, t), parent{w} {
        parent = w;
    }
public:
    Widget(const Widget&) = delete;
    Widget& operator=(const Widget&) = delete;
};

// Concrete handler
// handles requests it is responsible for.
class Button: public Widget {
public:
    explicit Button(shared_ptr<Widget> h, Topic t = Topic::NO_HELP_TOPIC):
        Widget(h.get(), t) {}

    void handleHelp() const override {
        // If the Concrete handler can handle the request, it does so.
        // Otherwise, it forwards the request to its successor.
        std::println("Button::handleHelp called");
        if (hasHelp()) {
            // handles requests it is responsible for.
        } else {
            // can access its successor.
            HelpHandler::handleHelp();
        }
    }
};

// Concrete handler
class Dialog: public Widget {
public:
    explicit Dialog(shared_ptr<HelpHandler> h, Topic t = Topic::NO_HELP_TOPIC):
        Widget(nullptr) {
        setHandler(h.get(), t);
    }

    void handleHelp() const override {
        std::println("Dialog::handleHelp called");
        // Widget operations that Dialog overrides...
        if(hasHelp()) {
            // offer help on the dialog
        } else {
            HelpHandler::handleHelp();
        }
    }
};

class Application: public HelpHandler {
public:
    explicit Application(Topic t):
        HelpHandler(nullptr, t) {}

    void handleHelp() const override {
        std::println("Application::handleHelp called");
        // show a list of help topics
    }
};

int main(int argc, char* argv[]) {
    shared_ptr<Application> application = std::make_shared<Application>(Topic::APPLICATION_TOPIC);
    shared_ptr<Dialog> dialog = std::make_shared<Dialog>(application, Topic::PRINT_TOPIC);
    shared_ptr<Button> button = std::make_shared<Button>(dialog, Topic::PAPER_ORIENTATION_TOPIC);

    button->handleHelp();
    return 0;
}

```
 

## Implementations

 

### Cocoa and Cocoa Touch

 

The [Cocoa](./Cocoa_(API)) and [Cocoa Touch](./Cocoa_Touch) frameworks, used for [OS X](./OS_X) and [iOS](./IOS) applications respectively, actively use the chain-of-responsibility pattern for handling events. Objects that participate in the chain are called *responder* objects, inheriting from the `NSResponder` (OS X)/`UIResponder` (iOS) class. All view objects (`NSView`/`UIView`), view controller objects (`NSViewController`/`UIViewController`), window objects (`NSWindow`/`UIWindow`), and the application object (`NSApplication`/`UIApplication`) are responder objects.

 

Typically, when a view receives an event which it can't handle, it dispatches it to its superview until it reaches the view controller or window object. If the window can't handle the event, the event is dispatched to the application object, which is the last object in the chain. For example:

 
- On OS X, moving a textured window with the mouse can be done from any location (not just the title bar), unless on that location there's a view which handles dragging events, like slider controls. If no such view (or superview) is there, dragging events are sent up the chain to the window which does handle the dragging event.
- On iOS, it's typical to handle view events in the view controller which manages the view hierarchy, instead of subclassing the view itself. Since a view controller lies in the responder chain after all of its managed subviews, it can intercept any view events and handle them.

 

## See also

 
- [Software design pattern](./Software_design_pattern)
- [Single responsibility principle](./Single_responsibility_principle)

 

## References

  
1. [↑](./Chain-of-responsibility_pattern#cite_ref-1) ["Chain of Responsibility Design Pattern"](https://web.archive.org/web/20180227070352/http://www.blackwasp.co.uk/ChainOfResponsibility.aspx). Archived from the original on 2018-02-27. Retrieved 2013-11-08.
2. [↑](./Chain-of-responsibility_pattern#cite_ref-GoF_2-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/223). Addison Wesley. pp. [223ff](https://archive.org/details/designpatternsel00gamm/page/223). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
3. [↑](./Chain-of-responsibility_pattern#cite_ref-3) ["The Chain of Responsibility design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=b01&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.
4. [↑](./Chain-of-responsibility_pattern#cite_ref-4) ["The Chain of Responsibility design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=b01&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
5. [↑](./Chain-of-responsibility_pattern#cite_ref-5) Erich Gamma (1994). *Design Patterns: Elements of Reusable Object-Oriented Software*. Addison Wesley. pp. 189 ff. [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).

 
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