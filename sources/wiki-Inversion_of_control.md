---
source: https://en.wikipedia.org/wiki/Inversion_of_control
fetched: 2026-06-19
---

Software programming technique 

 

In [software design](./Software_design), **inversion of control** (**IoC**) is a design principle in which custom-written portions of a [computer program](./Computer_program) receive the [flow of control](./Control_flow) from an external source (e.g. a [framework](./Software_framework)). The term "inversion" is historical: a [software architecture](./Software_architecture) with this design "inverts" control as compared to [procedural programming](./Procedural_programming). In procedural programming, a program's custom code [calls](./Function_call#Main_concepts) reusable libraries to take care of generic tasks, but with inversion of control, it is the external code or framework that is in control and calls the custom code.

 

Inversion of control has been widely used by application development frameworks since the rise of GUI environments[[1]](./Inversion_of_control#cite_note-Mesa1985-1)[[2]](./Inversion_of_control#cite_note-2) and continues to be used both in GUI environments and in [web server application frameworks](./Web_framework). Inversion of control makes the framework [extensible](./Extensible_programming) by the methods defined by the application programmer.[[3]](./Inversion_of_control#cite_note-3)

 

[Event-driven programming](./Event-driven_programming) is often implemented using IoC so that the custom code need only be concerned with the handling of events, while the [event loop](./Event_loop) and dispatch of events/messages is handled by the framework or the runtime environment. In web server application frameworks, dispatch is usually called routing, and handlers may be called endpoints. 

 

## Alternative meaning

 

The phrase "inversion of control" has separately also come to be used in the community of Java programmers to refer specifically to the patterns of [dependency injection](./Dependency_injection) (passing services to objects that need them) that occur with "IoC containers" in Java frameworks such as the [Spring Framework](./Spring_Framework).[[4]](./Inversion_of_control#cite_note-FowlerDI-IOC-4) In this different sense, "inversion of control" refers to granting the framework control over the implementations of dependencies that are used by application objects[[5]](./Inversion_of_control#cite_note-spring_framework_ioc_docs-5) rather than to the original meaning of granting the framework [control flow](./Control_flow) (control over the time of execution of application code, e.g. callbacks).

 

## Overview

 

As an example, with traditional programming, the [main function](./Main_function) of an application might make function calls into a menu library to display a list of available [commands](./Command_(computing)) and query the user to select one.[[6]](./Inversion_of_control#cite_note-FowlerDI-6) The library thus would return the chosen option as the value of the function call, and the main function uses this value to execute the associated command. This style was common in [text-based interfaces](./Text_based_interface). For example, an [email client](./Email_client) may show a screen with commands to load new mail, answer the current mail, create new mail, etc., and the program execution would block until the user presses a key to select a command.

 

With inversion of control, on the other hand, the program would be written using a [software framework](./Software_framework) that knows common behavioral and graphical elements, such as [windowing systems](./Windowing_system), menus, controlling the mouse, and toolbars. The custom code "fills in the blanks" for the framework, such as supplying a table of menu items and registering a code subroutine for each item, but it is the framework that monitors the user's actions and invokes the subroutine when a menu item is selected. In the mail client example, the framework could follow both the keyboard and mouse inputs and call the command invoked by the user by either means and at the same time monitor the [network interface](./Network_interface_controller) to find out if new messages arrive and refresh the screen when some network activity is detected. The same framework could be used as the skeleton for a spreadsheet program or a text editor. Conversely, the framework knows nothing about Web browsers, spreadsheets, or text editors; implementing their functionality takes custom code.

 

Inversion of control carries the strong connotation that the reusable code and the problem-specific code are developed independently even though they operate together in an application. [Callbacks](./Callback_(computer_programming)), [schedulers](./Scheduling_(computing)), [event loops](./Event_loop), and the [template method](./Template_method) are examples of [design patterns](./Design_pattern) that follow the inversion of control principle, although the term is most commonly used in the context of [object-oriented programming](./Object-oriented_programming). ([Dependency injection](./Dependency_injection) is an example of the separate, specific idea of "inverting control over the implementations of dependencies" popularised by Java frameworks.)[[4]](./Inversion_of_control#cite_note-FowlerDI-IOC-4)

 

Inversion of control is sometimes referred to as the "Hollywood Principle: Don't call us, we'll call you," reflecting how frameworks dictate execution flow.[[1]](./Inversion_of_control#cite_note-Mesa1985-1)

 

## Background

 

The etymology of the phrase has been traced back to 1988,[[7]](./Inversion_of_control#cite_note-FowlerIoC-7) but it is closely related to the concept of **program inversion** described by [Michael Jackson](./Michael_A._Jackson_(computer_scientist)) in his [Jackson Structured Programming](./Jackson_Structured_Programming) methodology in the 1970s.[[8]](./Inversion_of_control#cite_note-8) A [bottom-up parser](./Bottom-up_parsing) can be seen as an inversion of a [top-down parser](./Top-down_parsing): in the one case, the 
control lies with the parser, while in the other case, it lies with the receiving application.

 

The term was used by Michael Mattsson in a thesis (with its original meaning of a framework calling application code instead of vice versa)[[9]](./Inversion_of_control#cite_note-9) and was then taken from there[[10]](./Inversion_of_control#cite_note-10) by Stefano Mazzocchi and popularized by him in 1999 in a defunct Apache Software Foundation project, Avalon, in which it referred to a parent object passing in a child object's dependencies in addition to controlling execution flow.[[11]](./Inversion_of_control#cite_note-AvalonIoCPatterns-11) The phrase was further popularized in 2004 by [Robert C. Martin](./Robert_Cecil_Martin) and [Martin Fowler](./Martin_Fowler_(software_engineer)), the latter of whom traces the term's origins to the 1980s.[[7]](./Inversion_of_control#cite_note-FowlerIoC-7)

 

## Description

 

In traditional programming, the [flow](./Control_flow) of the [business logic](./Business_logic) is determined by objects that are [statically bound](./Static_binding) to one another. With inversion of control, the flow depends on the object graph that is built up during program execution. Such a dynamic flow is made possible by object interactions that are defined through abstractions. This [run-time binding](./Late_binding) is achieved by mechanisms such as [dependency injection](./Dependency_injection) or a [service locator](./Service_locator_pattern). In IoC, the code could also be linked statically during compilation, but finding the code to execute by reading its description from [external configuration](./Configuration_file) instead of with a direct reference in the code itself.

 

In dependency injection, a dependent [object](./Object-oriented_programming) or module is coupled to the object it needs at [run time](./Run_time_(program_lifecycle_phase)). Which particular object will satisfy the dependency during program execution typically cannot be known at [compile time](./Compile_time) using [static analysis](./Static_code_analysis). While described in terms of object interaction here, the principle can apply to other programming methodologies besides [object-oriented programming](./Object-oriented_programming).

 

In order for the running program to bind objects to one another, the objects must possess compatible [interfaces](./Software_interface). For example, class `A` may delegate behavior to interface `I` which is implemented by class `B`; the program instantiates `A` and `B`, and then injects `B` into `A`.

 

## Use

 
- The [Mesa](./Mesa_(programming_language)) Programming environment for [XDE](./Xerox_Development_Environment), 1985[[1]](./Inversion_of_control#cite_note-Mesa1985-1)
- [Visual Basic (classic)](./Visual_Basic_(classic)), 1991.
- HTML [DOM event](./DOM_event)
- The [Spring Framework](./Spring_Framework)[[5]](./Inversion_of_control#cite_note-spring_framework_ioc_docs-5)
- [ASP.NET Core](./ASP.NET_Core)[[12]](./Inversion_of_control#cite_note-AspNetCore7Routing-12)
- [Template method pattern](./Template_method_pattern)

 

## Example code

 

### HTML DOM events

 

Web browsers implement inversion of control for DOM events in HTML. The application developer uses `document.addEventListener()` to register a callback.

 
```
<!doctype html>
<html lang="en">
<head>
     <meta charset="utf-8">
     <title>DOM Level 2</title>
</head>
<body>
     <h1>DOM Level 2 Event handler</h1>     
     <div id="output"></div>

     <script>
          var listener = function () {
               document.getElementById("output").innerHTML = "<p>The registered listener was called.</p>";
          }          
          document.addEventListener("click", listener, true);

          document.getElementById("output").innerHTML = "<p>The event handler has been registered. If you click the page, your web browser will call the event handler.</p>"
     </script>
</body>
</html>

```
 

### Web application frameworks

 

This example code for an ASP.NET Core web application creates a web application host, registers an endpoint, and then passes control to the framework:[[12]](./Inversion_of_control#cite_note-AspNetCore7Routing-12)

 
```
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();
app.MapGet("/", () => "Hello World!");
app.Run();

```
 

## See also

  
- [Abstraction layer](./Abstraction_layer)
- [Asynchronous I/O](./Asynchronous_I/O)
- [Aspect-oriented programming](./Aspect-oriented_programming)
- [Callback (computer programming)](./Callback_(computer_programming))
- [Closure (computer programming)](./Closure_(computer_programming))
- [Continuation](./Continuation)
- [Delegate (CLI)](./Delegate_(CLI))
- [Dependency inversion principle](./Dependency_inversion_principle)
- [Flow-based programming](./Flow-based_programming)
- [Implicit invocation](./Implicit_invocation)
- [Interrupt handler](./Interrupt_handler)
- [Message passing](./Message_passing)
- [Monad (functional programming)](./Monad_(functional_programming))
- [Observer pattern](./Observer_pattern)
- [Publish–subscribe pattern](./Publish–subscribe_pattern)
- [Service locator pattern](./Service_locator_pattern)
- [Signal (computing)](./Signal_(computing))
- [Software framework](./Software_framework)
- [Strategy pattern](./Strategy_pattern)
- [User exit](./User_exit)
- [Visitor pattern](./Visitor_pattern)
- [XSLT](./XSLT)

  

## References

 
1. [1](./Inversion_of_control#cite_ref-Mesa1985_1-0) [2](./Inversion_of_control#cite_ref-Mesa1985_1-1) [3](./Inversion_of_control#cite_ref-Mesa1985_1-2) Sweet, Richard (25 June 1985). ["The Mesa Programming Environment"](https://dl.acm.org/doi/abs/10.1145/17919.806843). *ACM SIGPLAN Notices*. **20** (7): 216–229. [doi](./Doi_(identifier)):[10.1145/17919.806843](https://doi.org/10.1145%2F17919.806843).
2. [↑](./Inversion_of_control#cite_ref-2) [Visual_Basic_(classic)](./Visual_Basic_(classic))
3. [↑](./Inversion_of_control#cite_ref-3) Johnson, Ralph E.; Foote, Brian (June–July 1988). ["Designing Reusable Classes"](http://www.laputan.org/drc/drc.html). *Journal of Object-Oriented Programming*. **1** (2): 22–35. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.101.8594](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.101.8594). Retrieved 29 April 2014.
4. [1](./Inversion_of_control#cite_ref-FowlerDI-IOC_4-0) [2](./Inversion_of_control#cite_ref-FowlerDI-IOC_4-1) Fowler, Martin. ["Inversion of Control Containers and the Dependency Injection pattern"](https://martinfowler.com/articles/injection.html#InversionOfControl). *MartinFowler.com*. Retrieved 4 June 2023.
5. [1](./Inversion_of_control#cite_ref-spring_framework_ioc_docs_5-0) [2](./Inversion_of_control#cite_ref-spring_framework_ioc_docs_5-1) ["Spring Framework The IoC container"](https://docs.spring.io/spring-framework/docs/2.5.5/reference/beans.html). *docs.spring.io*. Retrieved 25 May 2023.
6. [↑](./Inversion_of_control#cite_ref-FowlerDI_6-0) [Dependency Injection](http://martinfowler.com/articles/injection.html).
7. [1](./Inversion_of_control#cite_ref-FowlerIoC_7-0) [2](./Inversion_of_control#cite_ref-FowlerIoC_7-1) [Inversion of Control](http://martinfowler.com/bliki/InversionOfControl.html) on Martin Fowler's Bliki
8. [↑](./Inversion_of_control#cite_ref-8) ["Introduction to Jackson Design Method"](http://www.jacksonworkbench.co.uk/stevefergspages/papers/ourusoff--introduction_to_jackson_design_method.pdf) (PDF).
9. [↑](./Inversion_of_control#cite_ref-9) Mattsson, Michael (February 1996). ["Object-Oriented Frameworks, A survey of methodological issues"](https://www.researchgate.net/publication/2238535). Department of Computer Science, Lund University. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.36.1424](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.36.1424). LU-CS-TR: 96-167.
10. [↑](./Inversion_of_control#cite_ref-10) Stefano Mazzocchi (22 January 2004). ["On Inversion of Control"](https://web.archive.org/web/20040202120126/http://www.betaversion.org/~stefano/linotype/news/38/). Archived from [the original](http://www.betaversion.org/~stefano/linotype/news/38/) on 2 February 2004.
11. [↑](./Inversion_of_control#cite_ref-AvalonIoCPatterns_11-0) ["IOC Patterns - Avalon Framework"](https://svn.apache.org/repos/asf/avalon/site///framework/cop/guide-patterns-ioc.html). *The Apache Avalon Project*. Retrieved 8 June 2023.
12. [1](./Inversion_of_control#cite_ref-AspNetCore7Routing_12-0) [2](./Inversion_of_control#cite_ref-AspNetCore7Routing_12-1) Ryan Nowak, Kirk Larkin, Rick Anderson. [""Routing in ASP.Net Core""](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/routing). *learn.microsoft.com*. microsoft. Retrieved 25 May 2023. Routing is responsible for matching incoming HTTP requests and dispatching those requests to the app's executable endpoints. Endpoints are the app's units of executable request-handling code. Endpoints are defined in the app and configured when the app starts.`{{cite web}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))

 

## External links

 
- [Inversion of Control explanation and implementation example](http://javaprogrammernotes.blogspot.com/2015/03/inversion-of-control-dependency.html)
- [Inversion of Control](https://www.sebaslab.com/the-truth-behind-inversion-of-control-part-ii-inversion-of-control/)

 
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

 

  Interwikies  
 

 Categories