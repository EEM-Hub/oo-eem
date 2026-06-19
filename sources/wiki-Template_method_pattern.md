---
source: https://en.wikipedia.org/wiki/Template_method_pattern
fetched: 2026-06-19
---

Behavioral design pattern in object-oriented programming Not to be confused with [Template processor](./Template_processor). 
|  | This article includes a list ofgeneral references, butit lacks sufficient correspondinginline citations.Please help toimprovethis article byintroducingmore precise citations.(March 2012)(Learn how and when to remove this message) |
| --- | --- |

 

In [object-oriented programming](./Object-oriented_programming), the **template method** is one of the [behavioral](./Behavioral_pattern) [design patterns](./Software_design_pattern) identified by Gamma et al.[[1]](./Template_method_pattern#cite_note-:0-1) in the book *[Design Patterns](./Design_Patterns)*.  The template method is a method in a superclass, usually an abstract superclass, and defines the skeleton of an operation in terms of a number of high-level steps.  These steps are themselves implemented by additional *helper methods* in the same class as the *template method*.

 

The *helper methods* may be either *[abstract methods](./Abstract_method)*, in which case subclasses are required to provide concrete implementations, or *[hook methods](./Hooking),* which have empty bodies in the superclass. [Subclasses](./Subclass_(computer_science)) can (but are not required to) customize the operation by [overriding](./Method_overriding) the hook methods.  The intent of the template method is to define the overall structure of the operation, while allowing subclasses to refine, or redefine, certain steps.[[2]](./Template_method_pattern#cite_note-:2-2)

 

## Overview

 

This pattern has two main parts:

 
- The "template method" is implemented as a method in a [base class](./Base_class) (usually an [abstract class](./Abstract_class)).  This method contains code for the parts of the overall algorithm that are invariant.  The template ensures that the overarching algorithm is always followed.[[1]](./Template_method_pattern#cite_note-:0-1)  In the template method, portions of the algorithm that may *vary* are implemented by sending self messages that request the execution of additional *helper* methods.  In the base class, these helper methods are given a default implementation, or none at all (that is, they may be abstract methods).
- Subclasses of the base class "fill in" the empty or "variant" parts of the "template" with specific algorithms that vary from one subclass to another.[[3]](./Template_method_pattern#cite_note-:1-3) It is important that subclasses do *not* override the *template method* itself.

 

At run-time, the algorithm represented by the template method is executed by sending the template message to an instance of one of the concrete subclasses.  Through inheritance, the template method in the base class starts to execute.  When the template method sends a message to self requesting one of the helper methods, the message will be received by the concrete sub-instance. If the helper method has been overridden, the overriding implementation in the sub-instance will execute; if it has not been overridden, the inherited implementation in the base class will execute.  This mechanism ensures that the overall algorithm follows the same steps every time while allowing the details of some steps to depend on which instance received the original request to execute the algorithm.

 

This pattern is an example of [inversion of control](./Inversion_of_control) because the high-level code no longer determines what algorithms to run; a lower-level algorithm is instead selected at run-time.

 

Some of the self-messages sent by the template method may be to *[hook](./Hooking) methods.*  These methods are implemented in the same base class as the template method, but with empty bodies (i.e., they do nothing).  Hook methods exist so that subclasses can override them, and can thus fine-tune the action of the algorithm *without* the need to override the template method itself. In other words, they provide a "hook" on which to "hang" variant implementations.

 

## Structure

 

### UML class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/2/2a/W3sDesign_Template_Method_Design_Pattern_UML.jpg)](./File:W3sDesign_Template_Method_Design_Pattern_UML.jpg)A sample UML class diagram for the Template Method design pattern.[[4]](./Template_method_pattern#cite_note-4) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), the `AbstractClass` defines a `templateMethod()` operation that defines the skeleton (template) of a behavior by

 
- implementing the invariant parts of the behavior and
- sending to **self** the messages  `primitive1()` and `primitive2()` , which, because they are implemented in `SubClass1` , allow that subclass to provide a variant implementation of those parts of the algorithm.

 [![](//upload.wikimedia.org/wikipedia/commons/2/2a/Template_Method_pattern_in_LePUS3.gif)](./File:Template_Method_pattern_in_LePUS3.gif)Template Method in [LePUS3](./Lepus3?action=edit&redlink=1).[[5]](./Template_method_pattern#cite_note-5) 

## Usage

 

The *template method* is used in frameworks, where each implements the invariant parts of a domain's architecture, while providing hook methods for customization. This is an example of [inversion of control](./Inversion_of_control). The template method is used for the following reasons.[[3]](./Template_method_pattern#cite_note-:1-3)

 
- It lets subclasses implement varying behavior (through [overriding](./Method_overriding_(programming)) of the hook methods).[[6]](./Template_method_pattern#cite_note-:3-6)
- It avoids duplication in the code: the general workflow of the algorithm is implemented once in the abstract class's template method, and necessary variations are implemented in the subclasses.[[6]](./Template_method_pattern#cite_note-:3-6)
- It controls the point(s) at which specialization is permitted.  If the subclasses were to simply override the template method, they could make radical and arbitrary changes to the workflow. In contrast, by overriding only the hook methods, only certain specific details of the workflow can be changed,[[6]](./Template_method_pattern#cite_note-:3-6) and the overall workflow is left intact.

 

### Use with code generators

 
|  | This section'stone or style may not reflect theencyclopedic toneused on Wikipedia.See Wikipedia'sguide to writing better articlesfor suggestions.(November 2025)(Learn how and when to remove this message) |
| --- | --- |

 

The template pattern is useful when working with auto-generated code. The challenge of working with generated code is that changes to the source code will lead to changes in the generated code; if hand-written modifications have been made to the generated code, these will be lost.  How, then, should the generated code be customized?

 

The Template pattern provides a solution.  If the generated code follows the template method pattern, the generated code will all be an abstract superclass. Provided that hand-written customizations are confined to a subclass, the code generator can be run again without risk of over-writing these modifications.  When used with code generation, this pattern is sometimes referred to as the [generation gap pattern](./Generation_gap_(pattern)).[[7]](./Template_method_pattern#cite_note-7)

 

## C++ example

 

This C++23 implementation is based on the pre C++98 implementation in the book.

 

[![Cpp template method pattern UML.svg](//upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Cpp_template_method_pattern_UML.svg/250px-Cpp_template_method_pattern_UML.svg.png)](./File:Cpp_template_method_pattern_UML.svg)

 
```
import std;

using std::unique_ptr;

// abstract class
class View {
private:
    void setFocus() {
        std::println("View::setFocus called");
    }

    void resetFocus() {
        std::println("View::resetFocus called");
    }
public:
    // defines abstract primitive operations that concrete subclasses define to implement steps of an algorithm.
    virtual void doDisplay() = 0;

    // implements a template method defining the skeleton of an algorithm. The template method calls primitive operations as well as operations defined in AbstractClass or those of other objects.
    void display() {
        setFocus();
        doDisplay();
        resetFocus();
    }

    virtual ~View() = default;
};

// concrete class
class MyView : public View {
public:
    // implements the primitive operations to carry out subclass-specific steps of the algorithm.
    void doDisplay() override {
        // render the view's contents
        std::println("MyView::doDisplay called");
    }
};

int main(int argc, char* argv[]) {
    unique_ptr<View> myview = std::make_unique<MyView>();
    myview->display();
}

```
 

The program output is

 
```
View::setFocus called
MyView::doDisplay called
View::resetFocus called

```
 

## See also

 
- [Inheritance (object-oriented programming)](./Inheritance_(object-oriented_programming))
- [Method overriding (programming)](./Method_overriding_(programming))
- [GRASP (object-oriented designer)](./GRASP_(object-oriented_design))
- [Adapter pattern](./Adapter_pattern)
- [Strategy pattern](./Strategy_pattern)

 

## References

  
1. [1](./Template_method_pattern#cite_ref-:0_1-0) [2](./Template_method_pattern#cite_ref-:0_1-1) [Gamma, Erich](./Erich_Gamma); [Helm, Richard](./Richard_Helm); [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). "Template Method". [*Design Patterns*](./Design_Patterns). Addison-Wesley. pp. [325–330](https://archive.org/details/designpatternsel00gamm/page/325). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Template_method_pattern#cite_ref-:2_2-0) Freeman, Eric; Freeman, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). [*Head First Design Patterns*](http://shop.oreilly.com/product/9780596007126.do) (paperback). Vol. 1. O'REILLY. pp. 289, 311. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6). Retrieved 2012-09-12.
3. [1](./Template_method_pattern#cite_ref-:1_3-0) [2](./Template_method_pattern#cite_ref-:1_3-1) ["Template Method Design Pattern"](http://sourcemaking.com/design_patterns/template_method). Source Making - teaching IT professional. Retrieved 2012-09-12. Template Method is used prominently in frameworks.
4. [↑](./Template_method_pattern#cite_ref-4) ["The Template Method design pattern - Structure"](http://w3sdesign.com/?gr=b10&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
5. [↑](./Template_method_pattern#cite_ref-5) LePUS3 legend.  Retrieved from [http://lepus.org.uk/ref/legend/legend.xml](http://lepus.org.uk/ref/legend/legend.xml).
6. [1](./Template_method_pattern#cite_ref-:3_6-0) [2](./Template_method_pattern#cite_ref-:3_6-1) [3](./Template_method_pattern#cite_ref-:3_6-2) Chung, Carlo (2011). *Pro Objective-C Design Patterns for iOS*. Berkeley, CA: Apress. p. 266. [ISBN](./ISBN_(identifier)) [978-1-4302-3331-2](./Special:BookSources/978-1-4302-3331-2).
7. [↑](./Template_method_pattern#cite_ref-7) Vlissides, John (1998-06-22). [*Pattern Hatching: Design Patterns Applied*](http://www.informit.com/store/pattern-hatching-design-patterns-applied-9780201432930). Addison-Wesley Professional. pp. 85–101. [ISBN](./ISBN_(identifier)) [978-0201432930](./Special:BookSources/978-0201432930).

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Template method](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Template%20method)***  
- [Six common uses of the template pattern](https://www.codeproject.com/Articles/307452/common-use-of-Template-Design-pattern-Design-pat)
- [Template Method Design Pattern](http://sourcemaking.com/design_patterns/template_method)

 
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