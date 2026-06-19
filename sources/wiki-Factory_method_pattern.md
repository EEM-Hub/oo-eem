---
source: https://en.wikipedia.org/wiki/Factory_method_pattern
fetched: 2026-06-19
---

Object-oriented software design pattern 

In [object-oriented programming](./Object-oriented_programming), the **factory method pattern** is a [design pattern](./Software_design_pattern) that uses factory methods to deal with the problem of [creating objects](./Object_creation) without having to specify their exact [classes](./Class_(computer_programming)). Rather than by calling a [constructor](./Constructor_(object-oriented_programming)), this is accomplished by invoking a factory method to create an object. Factory methods can be specified in an [interface](./Interface_(object-oriented_programming)) and implemented by subclasses or implemented in a base class and optionally [overridden](./Method_overriding) by subclasses. It is one of the 23 classic design patterns described in the book *[Design Patterns](./Design_Patterns)* and is subcategorized as a [creational pattern](./Creational_pattern).[[1]](./Factory_method_pattern#cite_note-FOOTNOTEGammaHelmJohnsonVlissides1995107-1)

 

## Overview

 

The factory method design pattern solves problems such as:

 
- How can an object's [subclasses](./Subclass_(computer_science)) redefine its subsequent and distinct implementation? The pattern involves creation of a factory method within the [superclass](./Superclass_(computer_science)) that defers the object's creation to a subclass's factory method.
- How can an object's instantiation be deferred to a subclass? Create an object by calling a factory method instead of directly calling a constructor.

 

This enables the creation of subclasses that can change the way in which an object is created (for example, by redefining which class to instantiate).

 

## Definition

 

According to *[Design Patterns: Elements of Reusable Object-Oriented Software](./Design_Patterns)*: "Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory method lets a class defer instantiation to subclasses."[[2]](./Factory_method_pattern#cite_note-gof-2)

 

Creating an object often requires complex processes not appropriate to include within a composing object. The object's creation may lead to a significant duplication of code, may require information inaccessible to the composing object, may not provide a sufficient level of abstraction or may otherwise not be included in the composing object's [concerns](./Concern_(computer_science)). The factory method design pattern handles these problems by defining a separate [method](./Method_(computer_science)) for creating the objects, which subclasses can then override to specify the [derived type](./Subtyping) of product that will be created.

 

The factory method pattern relies on inheritance, as object creation is delegated to subclasses that implement the factory method to create objects.[[3]](./Factory_method_pattern#cite_note-3)
The pattern can also rely on the implementation of an [interface](./Interface_(object-oriented_programming)).

 

## Structure

 

### UML class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/4/43/W3sDesign_Factory_Method_Design_Pattern_UML.jpg)](./File:W3sDesign_Factory_Method_Design_Pattern_UML.jpg)A sample UML class diagram for the Factory Method design pattern.
[[4]](./Factory_method_pattern#cite_note-4) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), the `Creator` class that requires a `Product` object does not instantiate the `Product1` class directly. Instead, the `Creator` refers to a separate `factoryMethod()` to create a product object, which makes the `Creator` independent of the exact concrete class that is instantiated. Subclasses of `Creator` can redefine which class to instantiate. In this example, the `Creator1` subclass implements the abstract `factoryMethod()` by instantiating the `Product1` class.

 

## Examples

 

### Structure

 

A maze game may be played in two modes, one with regular rooms that are only connected with adjacent rooms, and one with magic rooms that allow players to be transported at random. 

 [![](//upload.wikimedia.org/wikipedia/commons/d/df/New_WikiFactoryMethod.png)](./File:New_WikiFactoryMethod.png) 

`Room` is the base class for a final product (`MagicRoom` or `OrdinaryRoom`). `MazeGame` declares the abstract factory method to produce such a base product. `MagicRoom` and `OrdinaryRoom` are subclasses of the base product implementing the final product. `MagicMazeGame` and `OrdinaryMazeGame` are subclasses of `MazeGame` implementing the factory method producing the final products. Factory methods thus decouple callers (`MazeGame`) from the implementation of the concrete classes. This makes the `new` operator redundant, allows adherence to the [open–closed principle](./Open–closed_principle) and makes the final product more flexible in the event of change.

 

### Example implementations

 

#### [C++](./C++)

 

This [C++23](./C++23) implementation is based on the pre C++98 implementation in the *[Design Patterns](./Design_Patterns)* book.[[5]](./Factory_method_pattern#cite_note-FOOTNOTEGammaHelmJohnsonVlissides1995122-5)

 
```
import std;

using std::unique_ptr;

enum class ProductId: char {
    MINE, 
    YOURS
};

// defines the interface of objects the factory method creates.
class Product {
public:
    virtual void print() = 0;
    virtual ~Product() = default;
};

// implements the Product interface.
class ConcreteProductMINE: public Product {
public:
    void print() {
        std::println("this={} print MINE", this);
    }
};

// implements the Product interface.
class ConcreteProductYOURS: public Product {
public:
    void print() {
        std::println("this={} print YOURS", this);
    }
};

// declares the factory method, which returns an object of type Product.
class Creator {
public:
    virtual unique_ptr<Product> create(ProductId id) {
        switch (id) {
            case ProductId::MINE:
                return std::make_unique<ConcreteProductMINE>();
            case ProductId::YOURS:
                return std::make_unique<ConcreteProductYOURS>();
            // repeat for remaining products
            default:
                return nullptr;
        }
    }

    virtual ~Creator() = default;
};

int main(int argc, char* argv[]) {
    unique_ptr<Creator> creator = std::make_unique<Creator>();
    unique_ptr<Product> product = creator->create(ProductId::MINE);
    product->print();

    product = creator->create(ProductId::YOURS);
    product->print();
}

```
 

The program output is like

 
```
this=0x6e5e90 print MINE
this=0x6e62c0 print YOURS

```
 

#### [C#](./C_Sharp_(programming_language))

 
```
// Empty vocabulary of actual object
public interface IPerson
{
    string GetName();
}

public class Villager : IPerson
{
    public string GetName()
    {
        return "Village Person";
    }
}

public class CityPerson : IPerson
{
    public string GetName()
    {
        return "City Person";
    }
}

public enum PersonType
{
    Rural,
    Urban
}

/// <summary>
/// Implementation of Factory - Used to create objects.
/// </summary>
public class PersonFactory
{
    public IPerson GetPerson(PersonType type)
    {
        switch (type)
        {
            case PersonType.Rural:
                return new Villager();
            case PersonType.Urban:
                return new CityPerson();
            default:
                throw new NotSupportedException();
        }
    }
}

```
 

The above code depicts the creation of an interface called `IPerson` and two implementations called `Villager` and `CityPerson`. Based on the type passed to the `PersonFactory` object, the original concrete object is returned as the interface `IPerson`.

 

A factory method is just an addition to the `PersonFactory` class. It creates the object of the class through interfaces but also allows the subclass to decide which class is instantiated.

 
```
public interface IProduct
{
    string GetName();
    bool SetPrice(double price);
}

public class Phone : IProduct
{
    private double _price;

    public string GetName()
    {
        return "Apple TouchPad";
    }

    public bool SetPrice(double price)
    {
        _price = price;
        return true;
    }
}

/* Almost same as Factory, just an additional exposure to do something with the created method */
public abstract class ProductAbstractFactory
{
    protected abstract IProduct MakeProduct();

    public IProduct GetObject() // Implementation of Factory Method.
    {
        return this.MakeProduct();
    }
}

public class PhoneConcreteFactory : ProductAbstractFactory
{
    protected override IProduct MakeProduct()
    {
        IProduct product = new Phone();
        // Do something with the object after receiving it
        product.SetPrice(20.30);
        return product;
    }
}

```
 

In this example, `MakeProduct` is used in `concreteFactory`. As a result, `MakeProduct()` may be invoked in order to retrieve it from the `IProduct`. Custom logic could run after the object is obtained in the concrete factory method. `GetObject` is made abstract in the factory interface.

 

#### [Java](./Java_(programming_language))

 

This [Java](./Java_(programming_language)) example is similar to one in the book *[Design Patterns](./Design_Patterns).*

 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f8/Maze_game_UML.svg/1280px-Maze_game_UML.svg.png)](./File:Maze_game_UML.svg)

 

The `MazeGame` uses `Room` but delegates the responsibility of creating `Room` objects to its subclasses that create the concrete classes. The regular game mode could use this template method:

 
```
public abstract class Room {
    abstract void connect(Room room);
}

public class MagicRoom extends Room {
    public void connect(Room room) {}
}

public class OrdinaryRoom extends Room {
    public void connect(Room room) {}
}

public abstract class MazeGame {
     private final List<Room> rooms = new ArrayList<>();

     public MazeGame() {
          Room room1 = makeRoom();
          Room room2 = makeRoom();
          room1.connect(room2);
          rooms.add(room1);
          rooms.add(room2);
     }

     abstract protected Room makeRoom();
}

```
 

The `MazeGame` constructor is a [template method](./Template_method_pattern) that adds some common logic. It refers to the `makeRoom()` factory method that encapsulates the creation of rooms such that other rooms can be used in a subclass. To implement the other game mode that has magic rooms, the `makeRoom` method may be overridden:

 
```
public class MagicMazeGame extends MazeGame {
    @Override
    protected MagicRoom makeRoom() {
        return new MagicRoom();
    }
}

public class OrdinaryMazeGame extends MazeGame {
    @Override
    protected OrdinaryRoom makeRoom() {
        return new OrdinaryRoom();
    }
}

MazeGame ordinaryGame = new OrdinaryMazeGame();
MazeGame magicGame = new MagicMazeGame();

```
 

#### [PHP](./PHP)

 

This [PHP](./PHP) example shows interface implementations instead of subclassing (however, the same can be achieved through subclassing). The factory method can also be defined as `public`and called directly by the client code (in contrast to the previous Java example).

 
```
/* Factory and car interfaces */

interface CarFactory
{
    public function makeCar(): Car;
}

interface Car
{
    public function getType(): string;
}

/* Concrete implementations of the factory and car */

class SedanFactory implements CarFactory
{
    public function makeCar(): Car
    {
        return new Sedan();
    }
}

class Sedan implements Car
{
    public function getType(): string
    {
        return 'Sedan';
    }
}

/* Client */

$factory = new SedanFactory();
$car = $factory->makeCar();
print $car->getType();

```
 

#### [Python](./Python_(programming_language))

 

This Python example employs the same as did the previous Java example.

 
```
from abc import ABC, abstractmethod

class MazeGame(ABC):
    def __init__(self) -> None:
        self.rooms = []
        self._prepare_rooms()

    def _prepare_rooms(self) -> None:
        room1 = self.make_room()
        room2 = self.make_room()

        room1.connect(room2)
        self.rooms.append(room1)
        self.rooms.append(room2)

    def play(self) -> None:
        print(f"Playing using {self.rooms[0]}")

    @abstractmethod
    def make_room(self):
        raise NotImplementedError("You should implement this!")

class MagicMazeGame(MazeGame):
    def make_room(self) -> "MagicRoom":
        return MagicRoom()

class OrdinaryMazeGame(MazeGame):
    def make_room(self) -> "OrdinaryRoom":
        return OrdinaryRoom()

class Room(ABC):
    def __init__(self) -> None:
        self.connected_rooms = []

    def connect(self, room: "Room") -> None:
        self.connected_rooms.append(room)

class MagicRoom(Room):
    def __str__(self) -> str:
        return "Magic room"

class OrdinaryRoom(Room):
    def __str__(self) -> str:
        return "Ordinary room"

ordinaryGame = OrdinaryMazeGame()
ordinaryGame.play()

magicGame = MagicMazeGame()
magicGame.play()

```
 

## Uses

 
- In [ADO.NET](./ADO.NET), [IDbCommand.CreateParameter](https://docs.microsoft.com/en-us/dotnet/api/system.data.idbcommand.createparameter?view=netframework-4.8) is an example of the use of factory method to connect parallel class hierarchies.
- In [Qt](./Qt_(toolkit)), [QMainWindow::createPopupMenu](http://qt-project.org/doc/qt-5.0/qtwidgets/qmainwindow.html#createPopupMenu) [Archived](https://web.archive.org/web/20150719014739/http://qt-project.org/doc/qt-5.0/qtwidgets/qmainwindow.html#createPopupMenu) 2015-07-19 at the [Wayback Machine](./Wayback_Machine) is a factory method declared in a framework that can be overridden in [application code](./Application_code).
- In [Java](./Java_(programming_language)), several factories are used in the [javax.xml.parsers](http://download.oracle.com/javase/1.5.0/docs/api/javax/xml/parsers/package-summary.html) package, such as javax.xml.parsers.DocumentBuilderFactory or javax.xml.parsers.SAXParserFactory.
- In the [HTML5](./HTML5) [DOM](./Document_Object_Model) [API](./Application_programming_interface), the Document interface contains a createElement() factory method for creating specific elements of the HTMLElement interface.

 

## See also

 
- *[Design Patterns](./Design_Patterns)*, the highly influential book
- [Design pattern](./Design_pattern), overview of design patterns in general
- [Abstract factory pattern](./Abstract_factory_pattern), a pattern often implemented using factory methods
- [Builder pattern](./Builder_pattern), another creational pattern
- [Template method pattern](./Template_method_pattern), which may call factory methods
- [Joshua Bloch](./Joshua_Bloch)'s idea of a [static factory method](./Static_factory_method?action=edit&redlink=1) for which Bloch claims there is no direct equivalent in *[Design Patterns](./Design_Patterns)*.

 

## Notes

  
1. [↑](./Factory_method_pattern#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides1995107_1-0) [Gamma et al. 1995](./Factory_method_pattern#CITEREFGammaHelmJohnsonVlissides1995), p. 107.
2. [↑](./Factory_method_pattern#cite_ref-gof_2-0) [Gamma, Erich](./Erich_Gamma); [Helm, Richard](./Richard_Helm); [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](./Design_Patterns). Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
3. [↑](./Factory_method_pattern#cite_ref-3) Freeman, Eric; Robson, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). [*Head First Design Patterns: A Brain-Friendly Guide*](http://shop.oreilly.com/product/9780596007126.do) (paperback). Vol. 1 (1st ed.). O'Reilly Media. p. 162. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6). Retrieved 2012-09-12.
4. [↑](./Factory_method_pattern#cite_ref-4) ["The Factory Method design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=c03&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
5. [↑](./Factory_method_pattern#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides1995122_5-0) [Gamma et al. 1995](./Factory_method_pattern#CITEREFGammaHelmJohnsonVlissides1995), p. 122.

 

## References

 
- [Martin Fowler](./Martin_Fowler_(software_engineer)); [Kent Beck](./Kent_Beck); [John Brant](./John_Brant_(author)?action=edit&redlink=1); [William Opdyke](./William_Opdyke); [Don Roberts](./Don_Roberts_(author)?action=edit&redlink=1) (June 1999). *Refactoring: Improving the Design of Existing Code*. Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-48567-2](./Special:BookSources/0-201-48567-2).
- Cox, Brad J. (1986). [*Object-oriented programming: an evolutionary approach*](./Object-oriented_programming). Addison-Wesley. [ISBN](./ISBN_(identifier)) [978-0-201-10393-9](./Special:BookSources/978-0-201-10393-9).
- Cohen, Tal; Gil, Joseph (2007). ["Better Construction with Factories"](http://tal.forum2.org/static/cv/Factories.pdf) (PDF). *Journal of Object Technology*. **6** (6). [Bertrand Meyer](./Bertrand_Meyer): 103. [doi](./Doi_(identifier)):[10.5381/jot.2007.6.6.a3](https://doi.org/10.5381%2Fjot.2007.6.6.a3). Retrieved 2007-03-12.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Factory method examples](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Factory%20method%20examples)***  
- [Factory Design Pattern](http://designpattern.co.il/Factory.html) [Archived](https://web.archive.org/web/20180110103637/http://designpattern.co.il/Factory.html) 2018-01-10 at the [Wayback Machine](./Wayback_Machine) Implementation in Java

 
- [Factory method in UML and in LePUS3](https://web.archive.org/web/20080503082912/http://www.lepus.org.uk/ref/companion/FactoryMethod.xml) (a Design Description Language)
- [Consider static factory methods](http://drdobbs.com/java/208403883) by Joshua Bloch

 
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