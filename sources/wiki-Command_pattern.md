---
source: https://en.wikipedia.org/wiki/Command_pattern
fetched: 2026-06-19
---

Behavioral design pattern 
|  | This article includes alist of references,related reading, orexternal links,but its sources remain unclear because it lacksinline citations.Please helpimprovethis article byintroducingmore precise citations.(December 2012)(Learn how and when to remove this message) |
| --- | --- |

 

In [object-oriented programming](./Object-oriented_programming), the **command pattern** is a [behavioral](./Behavioral_pattern) [design pattern](./Design_pattern_(computer_science)) in which an object is used to [encapsulate](./Information_hiding) all information needed to perform an action or trigger an event at a later time. This information includes the method name, the object that owns the method and values for the method parameters.

 

Four terms always associated with the command pattern are *command*, *receiver*, *invoker* and *client*. A *command* object knows about *receiver* and invokes a method of the receiver. Values for parameters of the receiver method are stored in the command.  The receiver object to execute these methods is also stored in the command object by [aggregation](./Object_composition#Aggregation). The *receiver* then does the work when the `execute()` method in *command* is called. An *invoker* object knows how to execute a command, and optionally does bookkeeping about the command execution. The invoker does not know anything about a concrete command, it knows only about the command *interface*. Invoker object(s), command objects and receiver objects are held by a *client* object. The *client* decides which receiver objects it assigns to the command objects, and which commands it assigns to the invoker. The client decides which commands to execute at which points. To execute a command, it passes the command object to the invoker object.

 

Using command objects makes it easier to construct general components that need to delegate, sequence or execute method calls at a time of their choosing without the need to know the class of the method or the method parameters. Using an invoker object allows bookkeeping about command executions to be conveniently performed, as well as implementing different modes for commands, which are managed by the invoker object, without the need for the client to be aware of the existence of bookkeeping or modes.

 

The central ideas of this design pattern closely mirror the semantics of [first-class functions](./First-class_function) and [higher-order functions](./Higher-order_function) in [functional programming languages](./Functional_programming_language).  Specifically, the invoker object is a higher-order function of which the command object is a first-class argument.

 

## Overview

 

The command[[1]](./Command_pattern#cite_note-GoF-1)
design pattern is one of the twenty-three well-known *[GoF design patterns](./Design_Patterns)* that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

Using the command design pattern can solve these problems:[[2]](./Command_pattern#cite_note-2)

 
- Coupling the invoker of a request to a particular request should be avoided. That is, hard-wired requests should be avoided.
- It should be possible to configure an object (that invokes a request) with a request.

 

Implementing (hard-wiring) a request directly into a class is inflexible because it couples the class to a particular request at compile-time, which makes it impossible to specify a request at run-time.

 

Using the command design pattern describes the following solution:

 
- Define separate (command) objects that encapsulate a request.
- A class delegates a request to a command object instead of implementing a particular request directly.

 

This enables one to configure a class with a command object that is used to perform a request. The class is no longer coupled to a particular request and has no knowledge (is independent) of how the request is carried out.

 

See also the UML class and sequence diagram below.

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/c/c8/W3sDesign_Command_Design_Pattern_UML.jpg)](./File:W3sDesign_Command_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Command design pattern. [[3]](./Command_pattern#cite_note-3) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), the `Invoker` class doesn't implement a request directly.
Instead, `Invoker` refers to the `Command` interface to perform a request (`command.execute()`), which makes the `Invoker` independent of how the request is performed.
The `Command1` class implements the `Command` interface by performing an action on a receiver (`receiver1.action1()`).

 

The [UML](./Unified_Modeling_Language) [sequence diagram](./Sequence_diagram)
shows the run-time interactions: The `Invoker` object calls `execute()` on a `Command1` object.
`Command1` calls `action1()` on a `Receiver1` object,
which performs the request.

 

### UML class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Command_pattern.svg/960px-Command_pattern.svg.png)](./File:Command_pattern.svg)UML diagram of the command pattern 

## Uses

 GUI buttons and menu itemsIn [Swing](./Swing_(Java)) and [Borland](./Borland) [Delphi](./Delphi_(software)) programming, an `Action` is a command object. In addition to the ability to perform the desired command, an Action may have an associated icon, [keyboard shortcut](./Keyboard_shortcut), [tooltip](./Tooltip) text, and so on. A toolbar button or menu item component may be completely initialized using only the Action object. [Macro](./Macro_(computer_science)) recordingIf all user actions are represented by command objects, a program can record a sequence of actions simply by keeping a list of the command objects as they are executed. It can then "play back" the same actions by executing the same command objects again in sequence. If the program embeds a scripting engine, each command object can implement a toScript() method, and user actions can then be easily recorded as scripts. [Mobile code](./Code_mobility)Using languages such as Java where code can be streamed/slurped from one location to another via URLClassloaders and Codebases the commands can enable new behavior to be delivered to remote locations (EJB Command, Master Worker). Multi-level [undo](./Undo)If all user actions in a program are implemented as command objects, the program can keep a stack of the most recently executed commands. When the user wants to undo a command, the program simply pops the most recent command object and executes its undo() method. NetworkingIt is possible to send whole command objects across the network to be executed on the other machines, for example player actions in computer games. Parallel processingWhere the commands are written as tasks to a shared resource and executed by many threads in parallel (possibly on remote machines; this variant is often referred to as the Master/Worker pattern) [Progress bars](./Progress_bar)Suppose a program has a sequence of commands that it executes in order. If each command object has a getEstimatedDuration() method, the program can easily estimate the total duration. It can show a progress bar that meaningfully reflects how close the program is to completing all the tasks. [Thread pools](./Thread_pool)A typical, general-purpose thread pool class might have a public addTask() method that adds a work item to an internal queue of tasks waiting to be done. It maintains a pool of threads that execute commands from the queue. The items in the queue are command objects. Typically these objects implement a common interface such as java.lang.Runnable that allows the thread pool to execute the command even though the thread pool class itself was written without any knowledge of the specific tasks for which it would be used. [Transactional](./Database_transaction) behaviorSimilar to undo, a [database engine](./Database_engine) or software installer may keep a list of operations that have been or will be performed. Should one of them fail, all others can be reversed or discarded (usually called *rollback*). For example, if two database tables that refer to each other must be updated, and the second update fails, the transaction can be rolled back, so that the first table does not now contain an invalid reference. [Wizards](./Wizard_(software))Often a wizard presents several pages of configuration for a single action that happens only when the user clicks the "Finish" button on the last page. In these cases, a natural way to separate user interface code from application code is to implement the wizard using a command object. The command object is created when the wizard is first displayed. Each wizard page stores its GUI changes in the command object, so the object is populated as the user progresses. "Finish" simply triggers a call to execute(). This way, the command class will work. 

## Example

  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Command  

This C++23 implementation is based on the pre C++98 implementation in the book.

 
```
import std;

using std::shared_ptr;
using std::unique_ptr;

// Abstract command
class Command {
protected:
    Command() = default;
public:
    // declares an interface for executing an operation.
    virtual void execute() = 0;
    virtual ~Command() = default;
};

// Concrete command
template <typename Receiver>
class SimpleCommand : public Command {
private:
    Receiver* receiver;
    Action action;
public:
    using Action = void (Receiver::*)();

    // defines a binding between a Receiver object and an action.
    SimpleCommand(shared_ptr<Receiver> receiver, Action action):
        receiver{receiver.get()}, action{action} {}

    SimpleCommand(const SimpleCommand&) = delete;
    const SimpleCommand& operator=(const SimpleCommand&) = delete;

    // implements execute by invoking the corresponding operation(s) on Receiver.
    virtual void execute() {
        (receiver->*action)();
    }
};

// Receiver
class MyClass {
public:
    // knows how to perform the operations associated with carrying out a request. Any class may serve as a Receiver.
    void action() {
        std::println("MyClass::action called");
    }
};

int main(int argc, char* argv[]) {
    shared_ptr<MyClass> receiver = std::make_shared<MyClass>();
    // ...
    unique_ptr<Command> command = std::make_unique<SimpleCommand<MyClass>>(receiver, &MyClass::action);
    // ...
    command->execute();
}

```
 

The program output is

 
```
MyClass::action called

```
 

## See also

 
- [Batch queue](./Batch_queue)
- [Closure](./Closure_(computer_science))
- [Command queue](./Command_queue)
- [Function object](./Function_object)
- [Job scheduler](./Job_scheduler)
- [Model–view–controller](./Model–view–controller)
- [Priority queue](./Priority_queue)
- [Software design pattern](./Software_design_pattern)
- *[Design Patterns](./Design_Patterns)* (book)

 

## History

 

The first published mention of using a Command class to implement interactive systems seems to be a 1985 article by Henry Lieberman.[[4]](./Command_pattern#cite_note-4) The first published description of a (multiple-level) undo-redo mechanism, using a Command class with *execute* and *undo* methods, and a history list, appears to be the first (1988) edition of [Bertrand Meyer](./Bertrand_Meyer)'s book [Object-oriented Software Construction](./Object-oriented_Software_Construction),[[5]](./Command_pattern#cite_note-5) section 12.2.

 

## References

  
1. [↑](./Command_pattern#cite_ref-GoF_1-0) Erich Gamma; Richard Helm; Ralph Johnson; John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/233). Addison Wesley. pp. [233ff](https://archive.org/details/designpatternsel00gamm/page/233). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Command_pattern#cite_ref-2) ["The Command design pattern - Problem, Solution, and Applicability"](https://web.archive.org/web/20200923124858/http://w3sdesign.com/?gr=b02&ugr=proble). *w3sDesign.com*. Archived from [the original](http://w3sdesign.com/?gr=b02&ugr=proble) on 2020-09-23. Retrieved 2017-08-12.
3. [↑](./Command_pattern#cite_ref-3) ["The Command design pattern - Structure and Collaboration"](https://web.archive.org/web/20200923120537/http://w3sdesign.com/?gr=b02&ugr=struct). *w3sDesign.com*. Archived from [the original](http://w3sdesign.com/?gr=b02&ugr=struct) on September 23, 2020. Retrieved 2017-08-12.
4. [↑](./Command_pattern#cite_ref-4) Lieberman, Henry (1985). "There's more to menu systems than meets the screen". *ACM SIGGRAPH Computer Graphics*. **19** (3): 181–189. [doi](./Doi_(identifier)):[10.1145/325165.325235](https://doi.org/10.1145%2F325165.325235).
5. [↑](./Command_pattern#cite_ref-5) [Meyer, Bertrand](./Bertrand_Meyer) (1988). *Object-Oriented Software Construction* (1st ed.). Prentice-Hall. [Bibcode](./Bibcode_(identifier)):[1988oosc.book.....M](https://ui.adsabs.harvard.edu/abs/1988oosc.book.....M).

 

## External links

   [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Command pattern](https://commons.wikimedia.org/wiki/Category:Command%20pattern).    [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Command implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Command)***  
- [Command Pattern](https://wiki.c2.com/?CommandPattern)
- [Java Tip 68: Learn how to implement the Command pattern in Java](https://www.infoworld.com/article/2077569/java-tip-68--learn-how-to-implement-the-command-pattern-in-java.html)

 
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