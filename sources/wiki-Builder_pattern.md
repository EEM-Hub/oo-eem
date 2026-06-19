---
source: https://en.wikipedia.org/wiki/Builder_pattern
fetched: 2026-06-19
---

Design pattern in object-oriented programming 

The **builder pattern** is a [design pattern](./Software_design_pattern) that provides a flexible solution to various object creation problems in [object-oriented programming](./Object-oriented_programming). The builder pattern [separates](./Separation_of_concerns) the construction of a complex object from its representation. It is one of the 23 classic design patterns described in the book *[Design Patterns](./Design_Patterns)* and is sub-categorized as a [creational pattern](./Creational_pattern).[[1]](./Builder_pattern#cite_note-FOOTNOTEGammaHelmJohnsonVlissides199497-1)

 

## Overview

 

The builder design pattern solves problems like:[[2]](./Builder_pattern#cite_note-2)

 
- How can a class (the same construction process) create different representations of a complex object?
- How can a class that includes creating a complex object be simplified?

 

Creating and assembling the parts of a complex object directly within a class is inflexible.  It commits the class to creating a particular representation of the complex object and makes it impossible to change the representation later independently from (without having to change) the class.

 

The builder design pattern describes how to solve such problems:

 
- Encapsulate creating and assembling the parts of a complex object in a separate  `Builder` object.
- A class delegates object creation to a `Builder` object instead of creating the objects directly.

 

A class (the same construction process) can delegate to different `Builder` objects to create different representations of a complex object.

 

## Definition

 

The intent of the builder design pattern is to separate the construction of a complex object from its representation. By doing so, the same construction process can create different representations.[[1]](./Builder_pattern#cite_note-FOOTNOTEGammaHelmJohnsonVlissides199497-1)

 

## Advantages

 

Advantages of the builder pattern include:[[3]](./Builder_pattern#cite_note-:0-3)

 
- Allows for variation in a product's internal representation.
- Encapsulates code for construction and representation.
- Provides control over the steps of the construction process.

 

## Disadvantages

 

Disadvantages of the builder pattern include:

 
- A distinct ConcreteBuilder must be created for each type of product.[[3]](./Builder_pattern#cite_note-:0-3)
- Builder classes must be mutable.
- May hamper/complicate dependency injection.
- In many [null-safe](./Void_safety) languages, the builder pattern defers [compile-time](./Compile_time) errors for unset fields to [runtime](./Execution_(computing)#Runtime).

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/8/87/W3sDesign_Builder_Design_Pattern_UML.jpg)](./File:W3sDesign_Builder_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the builder design pattern.[[4]](./Builder_pattern#cite_note-4) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram),
the `Director` class doesn't create and assemble the `ProductA1` and `ProductB1` objects directly.
Instead, the `Director` refers to the `Builder` interface for building (creating and assembling) the parts of a complex object,
which makes the `Director` independent of which concrete classes are instantiated (which representation is created).
The `Builder1` class implements the `Builder` interface by creating and assembling the `ProductA1` and `ProductB1` objects.

The [UML](./Unified_Modeling_Language) [sequence diagram](./Sequence_diagram) shows the run-time interactions:
The `Director` object calls `buildPartA()` on the `Builder1` object, which creates and assembles the `ProductA1` object.
Thereafter,
the `Director` calls `buildPartB()` on `Builder1`, which creates and assembles the `ProductB1` object.

 

### Class diagram

 [![Builder Structure](//upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Builder_UML_class_diagram.svg/500px-Builder_UML_class_diagram.svg.png)](./File:Builder_UML_class_diagram.svg)Builder Structure Builder Abstract interface for creating objects (product). ConcreteBuilder Provides implementation for Builder. It is an [object able to construct other objects](./Factory_(software_concept)). Constructs and assembles parts to build the objects. 

## Examples

 

A [C#](./C_Sharp_(programming_language)) example:

 
```
namespace Wikipedia.Examples;

/// <summary>
/// Represents a product created by the builder.
/// </summary>
public class Bicycle
{
    public Bicycle(string make, string model, string colour, int height)
    {
        Make = make;
        Model = model;
        Colour = colour;
        Height = height;
    }

    public string Make { get; set; }
    public string Model { get; set; }
    public int Height { get; set; }
    public string Colour { get; set; }
}

/// <summary>
/// The builder abstraction.
/// </summary>
public interface IBicycleBuilder
{
    Bicycle GetResult();

    string Colour { get; set; }
    int Height { get; set; }
}

/// <summary>
/// Concrete builder implementation.
/// </summary>
public class GTBuilder : IBicycleBuilder
{
    public Bicycle GetResult()
    {
        return Height == 29 ? new Bicycle("GT", "Avalanche", Colour, Height) : null;
    }

    public string Colour { get; set; }
    public int Height { get; set; }
}

/// <summary>
/// The director.
/// </summary>
public class MountainBikeBuildDirector
{
    private IBicycleBuilder _builder;

    public MountainBikeBuildDirector(IBicycleBuilder builder)
    {
        _builder = builder;
    }

    public void Construct()
    {
        _builder.Colour = "Red";
        _builder.Height = 29;
    }

    public Bicycle GetResult()
	{
		return this._builder.GetResult();
	}
}

public class Client
{
    public void DoSomethingWithBicycles()
    {
        MountainBikeBuildDirector director = new(new GTBuilder());
        // Director controls the stepwise creation of product and returns the result.
        director.Construct();
        Bicycle myMountainBike = director.GetResult();
    }
}

```
 

The Director assembles a bicycle instance in the example above, delegating the construction to a separate builder object that has been given to the Director by the Client.

 

## See also

 
- [Currying](./Currying)

 

## Notes

  
1. [1](./Builder_pattern#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides199497_1-0) [2](./Builder_pattern#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides199497_1-1) [Gamma et al. 1994](./Builder_pattern#CITEREFGammaHelmJohnsonVlissides1994), p. 97.
2. [↑](./Builder_pattern#cite_ref-2) ["The Builder design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=c02&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-13.
3. [1](./Builder_pattern#cite_ref-:0_3-0) [2](./Builder_pattern#cite_ref-:0_3-1) ["Index of /archive/2010/winter/51023-1/presentations"](https://www.classes.cs.uchicago.edu/archive/2010/winter/51023-1/presentations/ricetj_builder.pdf) (PDF). *www.classes.cs.uchicago.edu*. Retrieved 2016-03-03.
4. [↑](./Builder_pattern#cite_ref-4) ["The Builder design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=c02&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.

 

## References

 
- [Gamma, Erich](./Erich_Gamma); [Helm, Richard](./Richard_Helm); [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](./Design_Patterns). Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Builder implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Builder)***  

 

 
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