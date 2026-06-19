---
source: https://en.wikipedia.org/wiki/Flyweight_pattern
fetched: 2026-06-19
---

Software design pattern for objects
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Flyweight pattern"–news·newspapers·books·scholar·JSTOR(March 2026)(Learn how and when to remove this message) |
| --- | --- |

[![A screenshot of LibreOffice's Writer package.](//upload.wikimedia.org/wikipedia/commons/thumb/d/da/Linux-Mint-20-MATE-writer.png/250px-Linux-Mint-20-MATE-writer.png)](./File:Linux-Mint-20-MATE-writer.png)Text editors, such as [LibreOffice Writer](./LibreOffice_Writer), often use the flyweight pattern.[*[vague](./Wikipedia:Vagueness)*] 

In [computer programming](./Computer_programming), the **flyweight** [software design pattern](./Software_design_pattern) refers to an [object](./Object_(computer_science)) that minimizes [memory](./Computer_memory) usage by sharing some of its data with other similar objects. The flyweight pattern is one of twenty-three *[GoF design patterns](./Design_Patterns)*.[[1]](./Flyweight_pattern#cite_note-GoF-1)

 

In other contexts, the idea of sharing data structures is called [hash consing](./Hash_consing).

 

The term was first coined, and the idea extensively explored, by [Paul Calder](./Paul_Calder?action=edit&redlink=1) and [Mark Linton](./Mark_Linton?action=edit&redlink=1) in 1990[[2]](./Flyweight_pattern#cite_note-2) to efficiently handle glyph information in a [WYSIWYG document editor](./WYSIWYG).[[3]](./Flyweight_pattern#cite_note-3) Similar techniques were already used in other systems, however, as early as 1988.[[4]](./Flyweight_pattern#cite_note-4)

 

## Overview

 

The flyweight pattern is useful when dealing with a large number of objects that share simple repeated elements which would use a large amount of memory if they were individually embedded. It is common to hold shared data in external [data structures](./Data_structure) and pass it to the objects temporarily when they are used.

 

A classic example are the data structures used representing characters in a [word processor](./Word_processor). Naively, each character in a document might have a [glyph](./Glyph) object containing its font outline, font metrics, and other formatting data. However, this would use hundreds or thousands of bytes of memory for each character. Instead, each character can have a [reference](./Reference_(computer_science)) to a glyph object shared by every instance of the same character in the document. This way, only the position of each character needs to be stored internally.

 

As a result, flyweight objects can:[[5]](./Flyweight_pattern#cite_note-5)

 
- store *intrinsic* state that is invariant, context-independent and shareable (for example, the code of character 'A' in a given character set)
- provide an interface for passing in *extrinsic* state that is variant, context-dependent and can't be shared (for example, the position of character 'A' in a text document)

 

Clients can reuse `Flyweight` objects and pass in extrinsic state as necessary, reducing the number of physically created objects.

 

### Structure

 [![](//upload.wikimedia.org/wikipedia/commons/4/4e/W3sDesign_Flyweight_Design_Pattern_UML.jpg)](./File:W3sDesign_Flyweight_Design_Pattern_UML.jpg)A sample UML class and [sequence diagram](./Sequence_diagram) for the Flyweight design pattern.[[6]](./Flyweight_pattern#cite_note-6) 

The above [UML](./UML) [class diagram](./Class_diagram) shows:

 
- the `Client` class, which uses the flyweight pattern
- the `FlyweightFactory` class, which [creates and shares `Flyweight` objects](./Factory_class)
- the `Flyweight` [interface](./Interface_(computing)), which takes in extrinsic state and performs an operation
- the `Flyweight1` class, which implements `Flyweight` and stores intrinsic state

 

The sequence diagram shows the following [run-time](./Runtime_(program_lifecycle_phase)) interactions:

 
1. The `Client` object calls `getFlyweight(key)` on the `FlyweightFactory`, which returns a `Flyweight1` object.
2. After calling `operation(extrinsicState)` on the returned `Flyweight1` object, the `Client` again calls `getFlyweight(key)` on the `FlyweightFactory`.
3. The `FlyweightFactory` returns the already-existing `Flyweight1` object.

 

## Implementation details

 

There are multiple ways to implement the flyweight pattern. One example is mutability: whether the objects storing extrinsic flyweight state can change.

 

[Immutable](./Immutable) objects are easily shared, but require creating new extrinsic objects whenever a change in state occurs. In contrast, mutable objects can share state. Mutability allows better object reuse via the caching and re-initialization of old, unused objects. Sharing is usually nonviable when state is highly variable.

 

Other primary concerns include retrieval (how the end-client accesses the flyweight), [caching](./Caching) and [concurrency](./Concurrency_(computer_science)).

 

### Retrieval

 

The [factory](./Factory_(object-oriented_programming)) interface for creating or reusing flyweight objects is often a [facade](./Facade_pattern) for a complex underlying system. For example, the factory interface is commonly implemented as a [singleton](./Singleton_pattern) to provide global access for creating flyweights.

 

Generally speaking, the retrieval algorithm begins with a request for a new object via the factory interface.

 

The request is typically forwarded to an appropriate [cache](./Cache_(computing)) based on what kind of object it is. If the request is fulfilled by an object in the cache, it may be reinitialized and returned. Otherwise, a new object is instantiated. If the object is partitioned into multiple extrinsic sub-components, they will be pieced together before the object is returned.

 

### Caching

 

There are two ways to [cache](./Cache_(computing)) flyweight objects: maintained and unmaintained caches.

 

Objects with highly variable state can be cached with a [FIFO](./FIFO_(computing_and_electronics)) structure. This structure maintains unused objects in the cache, with no need to search the cache.

 

In contrast, unmaintained caches have less upfront overhead: objects for the caches are initialized in bulk at compile time or startup. Once objects populate the cache, the object retrieval algorithm might have more overhead associated than the push/pop operations of a maintained cache.

 

When retrieving extrinsic objects with immutable state one must simply search the cache for an object with the state one desires. If no such object is found, one with that state must be initialized. When retrieving extrinsic objects with mutable state, the cache must be searched for an unused object to reinitialize if no used object is found. If there is no unused object available, a new object must be instantiated and added to the cache.

 

Separate caches can be used for each unique subclass of extrinsic object. Multiple caches can be optimized separately, associating a unique search algorithm with each cache. This object caching system can be encapsulated with the [chain of responsibility](./Chain-of-responsibility_pattern) pattern, which promotes loose coupling between components.

 

### Concurrency

 

Special consideration must be taken into account where flyweight objects are created on multiple threads. If the list of values is finite and known in advance, the flyweights can be instantiated ahead of time and retrieved from a container on multiple threads with no contention. If flyweights are instantiated on multiple threads, there are two options:

 
1. Make flyweight instantiation single-threaded, thus introducing contention and ensuring one instance per value.
2. Allow concurrent threads to create multiple flyweight instances, thus eliminating contention and allowing multiple instances per value.

 

To enable safe sharing between clients and threads, flyweight objects can be made into [immutable](./Immutable) [value objects](./Value_object), where two instances are considered equal if their values are equal.

 

## Examples

 

### C#

 

In this example, every instance of the `MyObject` class uses a `Pointer` class to provide data.

 
```
// Defines Flyweight object that repeats itself.
public class Flyweight
{
    public string Name { get; set; }
    public string Location { get; set; }
    public string Website { get; set; }
    public byte[] Logo { get; set; }
}

public static class Pointer
{
    public static readonly Flyweight Company = new Flyweight { Name = "ABC", Location = "XYZ", Website = "www.example.com" };
}

public class MyObject
{
    public string Name { get; set; }
    public string Company => Pointer.Company.Name;
}

```
 

### C++

 

The C++ [Standard Template Library](./Standard_Template_Library) provides several containers that allow unique objects to be mapped to a key. The use of containers helps further reduce memory usage by removing the need for temporary objects to be created.

 
```
import std;

template <typename K, typename V>
using TreeMap = std::map<K, V>;
using String = std::string;
using StringView = std::string_view;
template <typename K, typename V>
using HashMap = std::unordered_map<K, V>;

// Instances of Tenant will be the Flyweights
class Tenant {
private:
    const String name;
public:
    explicit Tenant(StringView name): 
        name{name} {}

    [[nodiscard]]
    String getName() const noexcept {
        return name;
    }
};

// Registry acts as a factory and cache for Tenant flyweight objects
class Registry {
private:
    HashMap<String, Tenant> tenants;
public:
    Registry() = default;

    [[nodiscard]]
    Tenant& findByName(StringView name) {
        if (!tenants.contains(name)) {
            tenants[name] = Tenant{name};
        }
        return tenants[name];
    }
};

// Apartment maps a unique tenant to their room number.
class Apartment {
private:
    TreeMap<int, Tenant*> occupants;
    Registry registry;
public:
    Apartment() = default;

    void addOccupant(StringView name, int room) {
        occupants[room] = &registry.findByName(name);
    }

    void printTenants() {
        // room: int, tenant: Tenant
        for (const auto& [room, tenant] : occupants) {
            std::println("{} occupies room {}", tenant.name(), room);
        }
    }
};

int main(int argc, char* argv[]) {
    Apartment apartment;
    apartment.addOccupant("David", 1);
    apartment.addOccupant("Sarah", 3);
    apartment.addOccupant("George", 2);
    apartment.addOccupant("Sarah", 12);
    apartment.addOccupant("Michael", 10);
    apartment.printTenants();

    return 0;
}

```
 

### PHP

 
```
<?php

class CoffeeFlavour {

    private static array $CACHE = [];

    private function __construct(private string $name) {}

    public static function intern(string $name): self {
        self::$CACHE[$name] ??= new self($name);
        return self::$CACHE[$name];
    }

    public static function flavoursInCache(): int {
        return count(self::$CACHE);
    }

    public function __toString(): string {
        return $this->name;
    }

}

class Order {

    private function __construct(
        private CoffeeFlavour $flavour,
        private int $tableNumber
    ) {}

    public static function create(string $flavourName, int $tableNumber): self {
        $flavour = CoffeeFlavour::intern($flavourName);
        return new self($flavour, $tableNumber);
    }

    public function __toString(): string {
        return "Serving {$this->flavour} to table {$this->tableNumber}";
    }
}

class CoffeeShop {

    private array $orders = [];

    public function takeOrder(string $flavour, int $tableNumber) {
        $this->orders[] = Order::create($flavour, $tableNumber);
    }

    public function service() {
        print(implode(PHP_EOL, $this->orders).PHP_EOL);
    }
}

$shop = new CoffeeShop();
$shop->takeOrder("Cappuccino", 2);
$shop->takeOrder("Frappe", 1);
$shop->takeOrder("Espresso", 1);
$shop->takeOrder("Frappe", 897);
$shop->takeOrder("Cappuccino", 97);
$shop->takeOrder("Frappe", 3);
$shop->takeOrder("Espresso", 3);
$shop->takeOrder("Cappuccino", 3);
$shop->takeOrder("Espresso", 96);
$shop->takeOrder("Frappe", 552);
$shop->takeOrder("Cappuccino", 121);
$shop->takeOrder("Espresso", 121);
$shop->service();
print("CoffeeFlavor objects in cache: ".CoffeeFlavour::flavoursInCache().PHP_EOL);

```
 

## See also

 
- [Copy-on-write](./Copy-on-write)
- [Memoization](./Memoization)
- [Multiton](./Multiton)

 

## References

  
1. [↑](./Flyweight_pattern#cite_ref-GoF_1-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/195). Addison Wesley. pp. [195ff](https://archive.org/details/designpatternsel00gamm/page/195). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
2. [↑](./Flyweight_pattern#cite_ref-2) [Gamma, Erich](./Erich_Gamma); [Richard Helm](./Richard_Helm); [Ralph Johnson](./Ralph_Johnson_(computer_scientist)); [John Vlissides](./John_Vlissides) (1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](./Design_Patterns_(book)). [Addison-Wesley](./Addison-Wesley). pp. [205–206](https://archive.org/details/designpatternsel00gamm/page/205). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0). 
3. [↑](./Flyweight_pattern#cite_ref-3)  Calder, Paul R.; Linton, Mark A. (October 1990). "Glyphs: Flyweight Objects for User Interfaces". *Proceedings of the 3rd annual ACM SIGGRAPH symposium on User interface software and technology - UIST '90*. The 3rd Annual [ACM SIGGRAPH](./ACM_SIGGRAPH) Symposium on User Interface Software and Technology. Snowbird, Utah, United States. pp. 92–101. [doi](./Doi_(identifier)):[10.1145/97924.97935](https://doi.org/10.1145%2F97924.97935). [ISBN](./ISBN_(identifier)) [0-89791-410-4](./Special:BookSources/0-89791-410-4). 
4. [↑](./Flyweight_pattern#cite_ref-4)  Weinand, Andre; Gamma, Erich; Marty, Rudolf (1988). *ET++—an object oriented application framework in C++*. [OOPSLA](./OOPSLA) (Object-Oriented Programming Systems, Languages and Applications). San Diego, California, United States. pp. 46–57. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.471.8796](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.471.8796). [doi](./Doi_(identifier)):[10.1145/62083.62089](https://doi.org/10.1145%2F62083.62089). [ISBN](./ISBN_(identifier)) [0-89791-284-5](./Special:BookSources/0-89791-284-5). 
5. [↑](./Flyweight_pattern#cite_ref-5) ["Implementing Flyweight Patterns in Java"](https://www.developer.com/design/implementing-flyweight-patterns-in-java/). *Developer.com*. 2019-01-28. Retrieved 2021-06-12.
6. [↑](./Flyweight_pattern#cite_ref-6) ["The Flyweight design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=s06&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.

 

## External links

 
- [C like performance using flyweight wrappers](https://javaadvent.blogspot.com/)

 
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