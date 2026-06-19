---
source: https://en.wikipedia.org/wiki/Mediator_pattern
fetched: 2026-06-19
---

Not to be confused with [Broker pattern](./Broker_pattern). Software architecture design pattern 

In [software engineering](./Software_engineering), the **mediator pattern** defines an object that [encapsulates](./Encapsulation_(computer_programming)) how a set of objects interact. This pattern is considered to be a [behavioral pattern](./Behavioral_pattern) due to the way it can alter the program's running behavior.

 

In object-oriented programming, programs often consist of many [classes](./Class_(computer_science)). [Business logic](./Business_logic) and [computation](./Computation) are distributed among these classes. However, as more classes are added to a program, especially during [maintenance](./Software_maintenance) and/or [refactoring](./Refactoring), the problem of [communication](./Communication) between these classes may become more complex. This makes the program harder to read and maintain. Furthermore, it can become difficult to change the program, since any change may affect code in several other classes.

 

With the mediator pattern, communication between objects is encapsulated within a **mediator object**. Objects no longer communicate directly with each other, but instead communicate through the mediator. This reduces the dependencies between communicating objects, thereby reducing [coupling](./Coupling_(computer_programming)).

 

## Overview

 

The mediator[[1]](./Mediator_pattern#cite_note-GoF-1) design pattern is one of the twenty-three well-known [design patterns](./Design_Patterns) that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

### Problems that the mediator design pattern can solve

 

Source:[[2]](./Mediator_pattern#cite_note-2)

 
- Tight coupling between a set of interacting objects should be avoided.
- It should be possible to change the interaction between a set of objects independently.

 

Defining a set of interacting objects by accessing and updating each other directly is inflexible because it tightly couples the objects to each other and makes it impossible to change the interaction independently from (without having to change) the objects.
And it stops the objects from being reusable and makes them hard to test.

 

*Tightly coupled objects* are hard to implement, change, test, and reuse because they refer to and know about many different objects.

 

### Solutions described by the mediator design pattern

 
- Define a separate (mediator) object that encapsulates the interaction between a set of objects.
- Objects delegate their interaction to a mediator object instead of interacting with each other directly.

 

The objects interact with each other indirectly through a mediator object that controls and coordinates the interaction.

 

This makes the objects *loosely coupled*. They only refer to and know about their mediator object and have no explicit knowledge of each other.

 

See also the UML class and sequence diagram below.

 

## Definition

 

The essence of the mediator pattern is to "define an object that encapsulates how a set of objects interact". It promotes loose coupling by keeping objects from referring to each other explicitly, and it allows their interaction to be varied independently.[[3]](./Mediator_pattern#cite_note-3)[[4]](./Mediator_pattern#cite_note-4) Client classes can use the mediator to send messages to other clients, and can receive messages from other clients via an event on the mediator class.

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/9/92/W3sDesign_Mediator_Design_Pattern_UML.jpg)](./File:W3sDesign_Mediator_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the mediator design pattern.[[5]](./Mediator_pattern#cite_note-5) 

In the above [UML](./UML) [class diagram](./Class_diagram), the `Colleague1` and `Colleague2` classes do not refer to (and update) each other directly.
Instead, they refer to the common `Mediator` interface for controlling and coordinating interaction (`mediate()`), which makes them independent from one another with respect to how the interaction is carried out.
The `Mediator1` class implements the interaction between `Colleague1` and `Colleague2`.

 

The [UML](./UML) [sequence diagram](./Sequence_diagram) shows the run-time interactions. In this example, a `Mediator1` object 
mediates (controls and coordinates) the interaction between `Colleague1` and `Colleague2` objects.

 

Assuming that `Colleague1` wants to interact with `Colleague2` (to update/synchronize its state, for example), `Colleague1` calls `mediate(this)` on the `Mediator1` object, which gets the changed data from `Colleague1` and performs an `action2()` on `Colleague2`.

 

Thereafter,
`Colleague2` calls `mediate(this)` on the `Mediator1` object, which gets the changed data from `Colleague2` and performs an `action1()` on `Colleague1`.

 

### Class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/e/e4/Mediator_design_pattern.png)](./File:Mediator_design_pattern.png)The mediator behavioural design pattern Participants 

**Mediator** - defines the interface for communication between *Colleague* objects

 

**ConcreteMediator** - implements the mediator interface and coordinates communication between *Colleague* objects. It is aware of all of the *Colleagues* and their purposes with regards to inter-communication.

 

**Colleague** - defines the interface for communication with other *Colleagues* through its *Mediator*

 

**ConcreteColleague** - implements the Colleague interface and communicates with other *Colleagues* through its *Mediator*

 

## Example

 

### C#

 

The mediator pattern ensures that components are [loosely coupled](./Loosely_coupled), such that they do not call each other explicitly, but instead do so through calls to a mediator. In the following example, the mediator registers all Components and then calls their `SetState` methods.

 
```
interface IComponent
{
    void SetState(object state);
}

class Component1 : IComponent
{
    internal void SetState(object state)
    {
        throw new NotImplementedException();
    }
}

class Component2 : IComponent
{
    internal void SetState(object state)
    {
        throw new NotImplementedException();
    }
}

// Mediates the common tasks
class Mediator
{
    internal IComponent Component1 { get; set; }
    internal IComponent Component2 { get; set; }

    internal void ChangeState(object state)
    {
        this.Component1.SetState(state);
        this.Component2.SetState(state);
    }
}

```
 

A chat room could use the mediator pattern, or a system where many ‘clients’ each receive a message each time one of the other clients performs an action (for chat rooms, this would be when each person sends a message). In reality using the mediator pattern for a chat room would only be practical when used with [remoting](./Remoting). Using raw sockets would not allow for the [delegate](./Delegation_(object-oriented_programming)) [callbacks](./Callbacks) (people subscribed to the Mediator class’ MessageReceived event).

 
```
public delegate void MessageReceivedEventHandler(string message, string sender);

public class Mediator
{
    public event MessageReceivedEventHandler MessageReceived;

    public void Send(string message, string sender)
    {
        if (MessageReceived != null)
        {
            Console.WriteLine(f"Sending '{message}' from {sender}");
            MessageReceived(message, sender);
        }
    }
}

public class Person
{
    private Mediator _mediator;

    public Person(Mediator mediator, string name)
    {
        Name = name;
        _mediator = mediator;
        _mediator.MessageReceived += new MessageReceivedEventHandler(Receive);
    }

    public string Name { get; set; }

    private void Receive(string message, string sender)
    {
        if (sender != Name)
        {
            Console.WriteLine(f"{Name} received '{message}' from {sender}");
        }
    }

    public void Send(string message)
    {
        _mediator.Send(message, Name);
    }
}

```
 

### Java

  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Mediator   

In the following example, a `Mediator` object controls the values of several `Storage` objects, forcing the user code to access the stored values through the mediator. When a storage object wants to emit an event indicating that its value has changed, it also goes back to the mediator object (via the method `notifyObservers`) that controls the list of the observers (implemented using the [observer pattern](./Observer_pattern)).

 
```
import java.util.HashMap;
import java.util.Optional;
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.function.Consumer;

class Storage<T> {
    T value;
    
    T getValue() {
        return value;
    }
    void setValue(Mediator<T> mediator, String storageName, T value) {
        this.value = value;
        mediator.notifyObservers(storageName);
    }
}

class Mediator<T> {
    private final HashMap<String, Storage<T>> storageMap = new HashMap<>();
    private final CopyOnWriteArrayList<Consumer<String>> observers = new CopyOnWriteArrayList<>();
    
    public void setValue(String storageName, T value) {
        Storage storage = storageMap.computeIfAbsent(storageName, name -> new Storage<>());
        storage.setValue(this, storageName, value);
    }
    
    public Optional<T> getValue(String storageName) {
        return Optional.ofNullable(storageMap.get(storageName)).map(Storage::getValue);
    }
    
    public void addObserver(String storageName, Runnable observer) {
        observers.add(eventName -> {
            if (eventName.equals(storageName)) {
                observer.run();
            }
        });
    }
    
    void notifyObservers(String eventName) {
        observers.forEach(observer -> observer.accept(eventName));
    }
}

public class MediatorDemo {
    public static void main(String[] args) {
        Mediator<Integer> mediator = new Mediator<>();
        mediator.setValue("Bob", 20);
        mediator.setValue("Alice", 24);
        mediator.getValue("Alice").ifPresent(age -> System.out.printf("Age for Alice: %d\n", age));
        
        mediator.addObserver("Bob", () -> {
            System.out.printf("New age for Bob: %s\n", mediator.getValue("Bob").orElseThrow(RuntimeException::new));
        });
        mediator.setValue("Bob", 21);
    }
}

```
  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Mediator   

## See also

 
- [Data mediation](./Data_mediation)
- *[Design Patterns](./Design_Patterns),* the book which gave rise to the study of design patterns in computer science [*[citation needed](./Wikipedia:Citation_needed)*]
- [Software design pattern](./Software_design_pattern), a standard solution to common problems in software design

 

## References

 
1. [↑](./Mediator_pattern#cite_ref-GoF_1-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/273). Addison Wesley. pp. [273ff](https://archive.org/details/designpatternsel00gamm/page/273). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
2. [↑](./Mediator_pattern#cite_ref-2) Franke, Günther. ["The Mediator design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=b05&ugr=proble). *w3sDesign*. Retrieved 2017-08-12.
3. [↑](./Mediator_pattern#cite_ref-3) [Gamma, Erich](./Erich_Gamma); Helm, Richard; [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). *[Design Patterns](./Design_Patterns)*. [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
4. [↑](./Mediator_pattern#cite_ref-4) ["Mediator Design Pattern"](http://sourcemaking.com/design_patterns/mediator). *SourceMaking*.
5. [↑](./Mediator_pattern#cite_ref-5) Franke, Günther. ["The Mediator design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=b05&ugr=struct). *w3sDesign*. Retrieved 2017-08-12.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Mediator implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Mediator)***  
- Kaiser, Bodo (2012-09-21). ["Is the use of the mediator pattern recommend?"](https://stackoverflow.com/questions/12534338/is-the-use-of-the-mediator-pattern-recommend). *[Stack Overflow](./Stack_Overflow)*.

 
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