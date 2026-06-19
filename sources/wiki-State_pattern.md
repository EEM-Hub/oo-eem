---
source: https://en.wikipedia.org/wiki/State_pattern
fetched: 2026-06-19
---

Software design pattern 

The **state pattern** is a [behavioral](./Behavioral_pattern) [software design pattern](./Software_design_pattern) that allows an object to alter its behavior when its internal state changes. This pattern is close to the concept of [finite-state machines](./Finite-state_machine). The state pattern can be interpreted as a [strategy pattern](./Strategy_pattern), which is able to switch a strategy through invocations of methods defined in the pattern's interface.

 

The state pattern is used in [computer programming](./Computer_programming) to encapsulate varying behavior for the same [object](./Object_(computer_science)), based on its internal state. This can be a cleaner way for an object to change its behavior at runtime without resorting to conditional statements and thus improve maintainability.[[1]](./State_pattern#cite_note-GOF-1): 395 

 

## Overview

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/ec/W3sDesign_State_Design_Pattern_UML.jpg/250px-W3sDesign_State_Design_Pattern_UML.jpg)](./File:W3sDesign_State_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the State design pattern.[[2]](./State_pattern#cite_note-2) 

The state design pattern is one of twenty-three [design patterns documented by the Gang of Four](./Design_Patterns) that describe how to solve recurring design problems. Such problems cover the design of flexible and reusable object-oriented software, such as objects that are easy to implement, change, test, and reuse.[[3]](./State_pattern#cite_note-GoF-3)

 

The state pattern is set to solve two main problems:[[4]](./State_pattern#cite_note-4)

 
- An object should change its behavior when its internal state changes.
- State-specific behavior should be defined independently. That is, adding new states should not affect the behavior of existing states.

 

Implementing state-specific behavior directly within a class is inflexible because it commits the class to a particular behavior and makes it impossible to add a new state or change the behavior of an existing state later, independently from the class, without changing the class. In this, the pattern describes two solutions:

 
- Define separate (state) objects that encapsulate state-specific behavior for each state. That is, define an interface (state) for performing state-specific behavior, and define classes that implement the interface for each state.
- A class delegates state-specific behavior to its current state object instead of implementing state-specific behavior directly.

 

This makes a class independent of how state-specific behavior is implemented. New states can be added by defining new state classes. A class can change its behavior at run-time by changing its current state object.

 

## Structure

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e8/State_Design_Pattern_UML_Class_Diagram.svg/500px-State_Design_Pattern_UML_Class_Diagram.svg.png)](./File:State_Design_Pattern_UML_Class_Diagram.svg)State in UML[[1]](./State_pattern#cite_note-GOF-1) 

In the accompanying [Unified Modeling Language](./Unified_Modeling_Language) (UML) [class diagram](./Class_diagram), the `Context` class doesn't implement state-specific behavior directly. Instead, `Context` refers to the `State` interface for performing state-specific behavior (`state.handle()`), which makes `Context` independent of how state-specific behavior is implemented. The `ConcreteStateA` and `ConcreteStateB` classes implement the `State` interface, that is, implement (encapsulate) the state-specific behavior for each state. The UML [sequence diagram](./Sequence_diagram) shows the run-time interactions:

 

The `Context` object delegates state-specific behavior to different `State` objects. First, `Context` calls `handle(this)` on its current (initial) state object (`ConcreteStateA`), which performs the operation and calls `setState(ConcreteStateB)` on `Context` to change context's current state to `ConcreteStateB`. The next time, `Context` again calls `handle(this)` on its current state object (`ConcreteStateB`), which performs the operation and changes context's current state to `ConcreteStateA`.

 

## Example

 

This is a [C++](./C++) example demonstrating the state pattern.

 
```
import std;

using std::unique_ptr;

// Abstract State
class FanState {
public:
    virtual void handleButtonPress(class Fan& fan) const = 0;
    virtual ~FanState() = default;
};

// Context
class Fan {
private:
    unique_ptr<FanState> currentState;
public:
    explicit Fan(unique_ptr<FanState> state):
        currentState{state} {}

    void setState(unique_ptr<FanState> state) noexcept {
        currentState = state;
    }

    void pressButton() noexcept {
        currentState->handleButtonPress(*this);
    }
};

// Concrete States
class OffState : public FanState {
public:
    void handleButtonPress(Fan& fan) const override {
        std::println("Fan is OFF -> Switching to LOW speed.");
        fan.setState(std::make_unique<LowSpeedState>());
    }
};

class LowSpeedState : public FanState {
public:
    void handleButtonPress(Fan& fan) const override {
        std::println("Fan is on LOW speed -> Switching to HIGH speed.");
        fan.setState(std::make_unique<HighSpeedState>());
    }
};

class HighSpeedState : public FanState {
public:
    void handleButtonPress(Fan& fan) const override {
        std::println("Fan is on HIGH speed -> Turning OFF.");
        fan.setState(std::make_unique<OffState>());
    }
};

int main() {
    Fan fan(std::unique_ptr<OffState>());

    // Simulate pressing the button several times
    fan.pressButton(); // OFF -> LOW
    fan.pressButton(); // LOW -> HIGH
    fan.pressButton(); // HIGH -> OFF
    fan.pressButton(); // OFF -> LOW

    return 0;
}

```
 

## See also

 
- [Typestate analysis](./Typestate_analysis)

 

## References

  
1. [1](./State_pattern#cite_ref-GOF_1-0) [2](./State_pattern#cite_ref-GOF_1-1) [Erich Gamma](./Erich_Gamma); [Richard Helm](./Richard_Helm); [Ralph Johnson](./Ralph_Johnson_(computer_scientist)); [John M. Vlissides](./John_M._Vlissides) (1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](./Design_Patterns:_Elements_of_Reusable_Object-Oriented_Software). [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./State_pattern#cite_ref-2) ["The State design pattern – Structure and Collaboration"](http://w3sdesign.com/?gr=b08&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
3. [↑](./State_pattern#cite_ref-GoF_3-0) Erich Gamma; Richard Helm; Ralph Johnson; John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/305). Addison Wesley. pp. [305ff](https://archive.org/details/designpatternsel00gamm/page/305). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
4. [↑](./State_pattern#cite_ref-4) ["The State design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=b08&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[State implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/State)***  
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