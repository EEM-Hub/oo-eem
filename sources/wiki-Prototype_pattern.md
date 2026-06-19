---
source: https://en.wikipedia.org/wiki/Prototype_pattern
fetched: 2026-06-19
---

Creational design pattern in software development For other uses, see [Software prototyping](./Software_prototyping). Not to be confused with [Prototype-based programming](./Prototype-based_programming) or [Function prototype](./Function_prototype). 
|  | This article has multiple issues.Please helpimprove itor discuss these issues on thetalk page.(Learn how and when to remove these messages)This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Prototype pattern"–news·newspapers·books·scholar·JSTOR(November 2014)(Learn how and when to remove this message)This article'stone or style may not reflect theencyclopedic toneused on Wikipedia.See Wikipedia'sguide to writing better articlesfor suggestions.(June 2019)(Learn how and when to remove this message)(Learn how and when to remove this message) |  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Prototype pattern"–news·newspapers·books·scholar·JSTOR(November 2014)(Learn how and when to remove this message) |  | This article'stone or style may not reflect theencyclopedic toneused on Wikipedia.See Wikipedia'sguide to writing better articlesfor suggestions.(June 2019)(Learn how and when to remove this message) |
| --- | --- | --- | --- | --- | --- |
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Prototype pattern"–news·newspapers·books·scholar·JSTOR(November 2014)(Learn how and when to remove this message) |
|  | This article'stone or style may not reflect theencyclopedic toneused on Wikipedia.See Wikipedia'sguide to writing better articlesfor suggestions.(June 2019)(Learn how and when to remove this message) |

 

The **prototype pattern** is a creational [design pattern](./Design_pattern_(computer_science)) in [software development](./Software_development). It is used when the types of [objects](./Object_(computer_science)) to create is determined by a [prototypical](./Prototype) [instance](./Instance_(computer_science)), which is cloned to produce new objects. This pattern is used to avoid [subclasses](./Subclass_(computer_science)) of an object creator in the client application, like the [factory method pattern](./Factory_method_pattern) does, and to avoid the inherent cost of creating a new object in the standard way (e.g., using the '[new](./New_(C++))' keyword) when it is prohibitively expensive for a given application.

 

To implement the pattern, the client declares an abstract [base class](./Base_class) that specifies a [pure virtual](./Virtual_method#Abstract_classes_and_pure_virtual_functions) *clone()* method. Any class that needs a "[polymorphic](./Polymorphism_(computer_science)) [constructor](./Constructor_(computer_science))" capability derives itself from the abstract base class, and implements the *clone()* operation.

 

The client, instead of writing code that invokes the "new" operator on a hard-coded class name, calls the *clone()* method on the prototype, calls a [factory method](./Factory_method) with a [parameter](./Parameter) designating the particular concrete [derived class](./Derived_class) desired, or invokes the *clone()* method through some mechanism provided by another design pattern.

 

The [mitotic division](./Mitosis) of a cell — resulting in two identical cells — is an example of a prototype that plays an active role in copying itself and thus, demonstrates the Prototype pattern. When a cell splits, two cells of identical genotype result. In other words, the cell clones itself.[[1]](./Prototype_pattern#cite_note-1)

 

## Overview

 

The prototype design pattern is one of the 23 [Gang of Four design patterns](./Design_Patterns) that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.[[2]](./Prototype_pattern#cite_note-GoF-2): 117 

 

The prototype design pattern solves problems like:[[3]](./Prototype_pattern#cite_note-3)

 
- How can objects be created so that the specific type of object can be determined at runtime?
- How can dynamically loaded classes be instantiated?

 

Creating objects directly within the class that requires (uses) the objects is inflexible because it commits the class to particular objects at compile-time and makes it impossible to specify which objects to create at run-time.

 

The prototype design pattern describes how to solve such problems:

 
- Define a `Prototype` object that returns a copy of itself.
- Create new objects by copying a `Prototype` object.

 

This enables configuration of a class with different `Prototype` objects, which are copied to create new objects, and even more, `Prototype` objects can be added and removed at run-time.

See also the UML class and sequence diagram below.

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/c/c4/W3sDesign_Prototype_Design_Pattern_UML.jpg)](./File:W3sDesign_Prototype_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Prototype design pattern. 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), 
the `Client` class refers to the `Prototype` interface for cloning a `Product`.
The `Product1` class implements the `Prototype` interface by creating a copy of itself.

The [UML](./Unified_Modeling_Language) [sequence diagram](./Sequence_diagram) shows the run-time interactions: 
The `Client` object calls `clone()` on a `prototype:Product1` object, which creates and returns a copy of itself (a `product:Product1` object).

 

### UML class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/14/Prototype_UML.svg/960px-Prototype_UML.svg.png)](./File:Prototype_UML.svg)[UML](./Unified_Modeling_Language) class diagram describing the prototype design pattern 

## Rules of thumb

 

Sometimes [creational patterns](./Creational_pattern) overlap—there are cases when either prototype or [abstract factory](./Abstract_factory_pattern) would be appropriate. At other times, they complement each other: abstract factory might store a set of prototypes from which to clone and return product objects.[[2]](./Prototype_pattern#cite_note-GoF-2): 126  Abstract factory, [builder](./Builder_pattern), and prototype can use [singleton](./Singleton_pattern) in their implementations.[[2]](./Prototype_pattern#cite_note-GoF-2): 81, 134  Abstract factory classes are often implemented with factory methods (creation through [inheritance](./Inheritance_(object-oriented_programming))), but they can be implemented using prototype (creation through [delegation](./Delegation_(programming))).[[2]](./Prototype_pattern#cite_note-GoF-2): 95 

 

Often, designs start out using Factory Method (less complicated, more customizable, subclasses proliferate) and evolve toward abstract factory, prototype, or builder (more flexible, more complex) as the designer discovers where more flexibility is needed.[[2]](./Prototype_pattern#cite_note-GoF-2): 136 

 

Prototype does not require subclassing, but it does require an "initialize" operation. Factory method requires subclassing, but does not require initialization.[[2]](./Prototype_pattern#cite_note-GoF-2): 116 

 

Designs that make heavy use of the [composite](./Composite_pattern) and [decorator](./Decorator_pattern) patterns often can benefit from Prototype as well.[[2]](./Prototype_pattern#cite_note-GoF-2): 126 

 

A general guideline in programming suggests using the `clone()` method when creating a duplicate object during runtime to ensure it accurately reflects the original object. This process, known as object cloning, produces a new object with identical attributes to the one being cloned. Alternatively, *instantiating* a class using the `new` keyword generates an object with default attribute values.

 

For instance, in the context of designing a system for managing bank account transactions, it may be necessary to duplicate the object containing account information to conduct transactions while preserving the original data. In such scenarios, employing the `clone()` method is preferable over using `new` to instantiate a new object.

 

## Example

 

### C++23 Example

 

This [C++23](./C++23) implementation is based on the pre-C++98 implementation in the book. Discussion of the design pattern along with a complete illustrative example implementation using polymorphic class design are provided in the [C++ Annotations](https://fbb-git.gitlab.io/cppannotations/cppannotations/html/cplusplus14.html#l318).

 
```
import std;

using std::array;
using std::shared_ptr;
using std::unique_ptr;
using std::vector;

enum class Direction: char { 
    NORTH, 
    SOUTH, 
    EAST, 
    WEST 
};

class MapSite {
public:
    virtual void enter() = 0;
    virtual unique_ptr<MapSite> clone() const = 0;
    virtual ~MapSite() = default;
};

class Room: public MapSite {
private:
    int roomNumber;
    shared_ptr<array<shared_ptr<MapSite>, 4>> sides;
public:
    explicit Room(int n = 0): 
        roomNumber{n}, sides{std::make_shared<array<shared_ptr<MapSite>, 4>>()} {}

    ~Room() = default;

    Room& setSide(Direction d, shared_ptr<MapSite> ms) {
        (*sides)[static_cast<size_t>(d)] = std::move(ms);
        std::println("Room::setSide {} ms", d);
        return *this;
    }

    virtual void enter() override {}

    virtual unique_ptr<MapSite> clone() const override {
        return std::make_unique<Room>(*this);
    }

    Room(const Room&) = delete;
    Room& operator=(const Room&) = delete;
};

class Wall: public MapSite {
public:
    Wall():
        MapSite() {}

    ~Wall() = default;

    virtual void enter() override {}

    [[nodiscard]]
    virtual unique_ptr<MapSite> clone() const override {
        return std::make_unique<Wall>(*this);
    }
};

class Door: public MapSite {
private:
    shared_ptr<Room> room1;
    shared_ptr<Room> room2;
public:
    explicit Door(shared_ptr<Room> r1 = nullptr, shared_ptr<Room> r2 = nullptr):
        MapSite(), room1{std::move(r1)}, room2{std::move(r2)} {}

    ~Door() = default;

    virtual void enter() override {}

    [[nodiscard]]
    virtual unique_ptr<MapSite> clone() const override {
        return std::make_unique<Door>(*this);
    }

    void initialize(shared_ptr<Room> r1, shared_ptr<Room> r2) {
        room1 = std::move(r1);
        room2 = std::move(r2);
    }

    Door(const Door&) = delete;
    Door& operator=(const Door&) = delete;
};

class Maze {
private:
    vector<shared_ptr<Room>> rooms;
public:
    Maze() = default;
    ~Maze() = default;

    Maze& addRoom(shared_ptr<Room> r) {
        std::println("Maze::addRoom {}", reinterpret_cast<void*>(r.get()));
        rooms.push_back(std::move(r));
        return *this;
    }

    [[nodiscard]]
    shared_ptr<Room> roomNo(int n) const { 
        for (const Room& r: rooms) { 
            // actual lookup logic here... 
        } 
        return nullptr; 
    }

    [[nodiscard]]
    virtual unique_ptr<Maze> clone() const {
        return std::make_unique<Maze>(*this);
    }
};

class MazeFactory {
public:
    MazeFactory() = default;

    virtual ~MazeFactory() = default;

    [[nodiscard]]
    virtual unique_ptr<Maze> makeMaze() const {
        return std::make_unique<Maze>();
    }

    [[nodiscard]]
    virtual shared_ptr<Wall> makeWall() const {
        return std::make_shared<Wall>();
    }

    [[nodiscard]]
    virtual shared_ptr<Room> makeRoom(int n) const {
        return std::make_shared<Room>(n);
    }

    [[nodiscard]]
    virtual shared_ptr<Door> makeDoor(shared_ptr<Room> r1, shared_ptr<Room> r2) const {
        return std::make_shared<Door>(std::move(r1), std::move(r2));
    }
};

class MazePrototypeFactory: public MazeFactory {
private:
    unique_ptr<Maze> prototypeMaze;
    shared_ptr<Room> prototypeRoom;
    shared_ptr<Wall> prototypeWall;
    shared_ptr<Door> prototypeDoor;
public:
    MazePrototypeFactory(unique_ptr<Maze> m, shared_ptr<Wall> w, shared_ptr<Room> r, shared_ptr<Door> d):
        MazeFactory(), prototypeMaze{std::move(m)}, prototypeRoom{std::move(r)}, 
        prototypeWall{std::move(w)}, prototypeDoor{std::move(d)} {}

    ~MazePrototypeFactory() = default;

    virtual unique_ptr<Maze> makeMaze() const override {
        return prototypeMaze->clone();
    }

    [[nodiscard]]
    virtual shared_ptr<Room> makeRoom(int n) const override {
        return prototypeRoom->clone();
    }

    [[nodiscard]]
    virtual shared_ptr<Wall> makeWall() const override {
        return prototypeWall->clone();
    }

    [[nodiscard]]
    virtual shared_ptr<Door> makeDoor(shared_ptr<Room> r1, shared_ptr<Room> r2) const override {
        shared_ptr<Door> door = prototypeDoor->clone();
        door->initialize(std::move(r1), std::move(r2));
        return door;
    }

    MazePrototypeFactory(const MazePrototypeFactory&) = delete;
    MazePrototypeFactory& operator=(const MazePrototypeFactory&) = delete;
};

class MazeGame {
public:
    MazeGame() = default;
    ~MazeGame() = default;

    [[nodiscard]]
    unique_ptr<Maze> createMaze(MazePrototypeFactory& factory) {
        unique_ptr<Maze> maze = factory.makeMaze();
        shared_ptr<Room> r1 = factory.makeRoom(1);
        shared_ptr<Room> r2 = factory.makeRoom(2);
        shared_ptr<Door> door = factory.makeDoor(r1, r2);

        maze->addRoom(std::move(r1))
            .addRoom(std::move(r2));

        r1->setSide(Direction::NORTH, factory.makeWall())
            .setSide(Direction::EAST, door)
            .setSide(Direction::SOUTH, factory.makeWall())
            .setSide(Direction::WEST, factory.makeWall());

        r2->setSide(Direction::NORTH, factory.makeWall())
            .setSide(Direction::EAST, factory.makeWall())
            .setSide(Direction::SOUTH, factory.makeWall())
            .setSide(Direction::WEST, door);

        return maze;
    }
};

int main(int argc, char* argv[]) {
    MazeGame game;
    MazePrototypeFactory simpleMazeFactory(
        std::make_unique<Maze>(),
        std::make_shared<Wall>(),
        std::make_shared<Room>(0),
        std::make_shared<Door>()
    );

    unique_ptr<Maze> maze = game.createMaze(simpleMazeFactory);
}

```
 

The program output is:

 
```
Maze::addRoom 0x1160f50
Maze::addRoom 0x1160f70
Room::setSide 0 0x11613c0
Room::setSide 2 0x1160f90
Room::setSide 1 0x11613e0
Room::setSide 3 0x1161400
Room::setSide 0 0x1161420
Room::setSide 2 0x1161440
Room::setSide 1 0x1161460
Room::setSide 3 0x1160f90

```
 

## See also

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Prototype implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Prototype)***  
- [Function prototype](./Function_prototype)

 

## References

 
1. [↑](./Prototype_pattern#cite_ref-1) Duell, Michael (July 1997). "Non-Software Examples of Design Patterns". *Object Magazine*. **7** (5): 54. [ISSN](./ISSN_(identifier)) [1055-3614](https://search.worldcat.org/issn/1055-3614).
2. [1](./Prototype_pattern#cite_ref-GoF_2-0) [2](./Prototype_pattern#cite_ref-GoF_2-1) [3](./Prototype_pattern#cite_ref-GoF_2-2) [4](./Prototype_pattern#cite_ref-GoF_2-3) [5](./Prototype_pattern#cite_ref-GoF_2-4) [6](./Prototype_pattern#cite_ref-GoF_2-5) [7](./Prototype_pattern#cite_ref-GoF_2-6) [Gamma, Erich](./Erich_Gamma); Helm, Richard; [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm). Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
3. [↑](./Prototype_pattern#cite_ref-3) ["The Prototype design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=c04&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-17.

 
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