---
source: sources/wiki-Factory_method_pattern.md
source_url: https://en.wikipedia.org/wiki/Factory_method_pattern
---

## Factory Method Pattern

The Factory Method pattern is a creational design pattern from the Gang of Four catalog that solves the problem of creating objects without specifying their exact classes. Instead of calling a constructor directly, a factory method is invoked, allowing subclasses to determine which concrete class to instantiate. This decouples object creation from the code that uses the objects.

## Key Concepts

- **Intent**: "Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory method lets a class defer instantiation to subclasses." (GoF definition)
- **Core mechanism**: Relies on **inheritance** — object creation is delegated to subclasses that implement or override a factory method
- **Can also rely on interface implementation** as an alternative to subclassing
- **Solves two fundamental problems**:
  - How can a subclass redefine which concrete class gets instantiated?
  - How can object instantiation be deferred to a subclass?
- **Participants in the structure**:
  - **Creator**: Declares the factory method (abstract or with a default implementation)
  - **ConcreteCreator**: Overrides the factory method to return a specific ConcreteProduct
  - **Product**: Defines the interface for objects the factory method creates
  - **ConcreteProduct**: Implements the Product interface
- **Makes the `new` operator redundant** in client code — callers are decoupled from concrete class names
- **Supports the Open-Closed Principle**: New product types can be added by creating new subclasses without modifying existing creator code
- Object creation logic that is complex, duplicative, or requires information inaccessible to the composing object is a signal to use this pattern

## Commands and Syntax

**Java — canonical MazeGame example:**
```java
public abstract class MazeGame {
    private final List<Room> rooms = new ArrayList<>();
    public MazeGame() {
        Room room1 = makeRoom();
        Room room2 = makeRoom();
        room1.connect(room2);
        rooms.add(room1);
        rooms.add(room2);
    }
    abstract protected Room makeRoom();  // factory method
}

public class MagicMazeGame extends MazeGame {
    @Override
    protected MagicRoom makeRoom() {
        return new MagicRoom();  // subclass decides the concrete type
    }
}
```

**Python equivalent:**
```python
class MazeGame(ABC):
    @abstractmethod
    def make_room(self):
        raise NotImplementedError("You should implement this!")

class MagicMazeGame(MazeGame):
    def make_room(self) -> "MagicRoom":
        return MagicRoom()
```

**C# — interface-based approach with abstract factory method:**
```csharp
public abstract class ProductAbstractFactory {
    protected abstract IProduct MakeProduct();  // factory method
    public IProduct GetObject() {
        return this.MakeProduct();
    }
}
public class PhoneConcreteFactory : ProductAbstractFactory {
    protected override IProduct MakeProduct() {
        IProduct product = new Phone();
        product.SetPrice(20.30);
        return product;
    }
}
```

## Relationships

- **Abstract Factory Pattern**: Often implemented *using* factory methods; Abstract Factory creates families of related objects while Factory Method creates a single object
- **Template Method Pattern**: The MazeGame constructor is itself a template method that calls the factory method — these two patterns frequently collaborate
- **Builder Pattern**: Another creational pattern; Builder constructs complex objects step-by-step whereas Factory Method delegates instantiation of a single type to subclasses
- **Prototype Pattern**: Alternative creational approach that clones existing objects rather than deferring to subclasses
- **Singleton Pattern**: Fellow creational pattern from the GoF catalog
- **Open-Closed Principle**: Factory Method directly supports this SOLID principle by allowing extension without modification
- **Static Factory Method** (Joshua Bloch): A related but distinct concept with no direct equivalent in the GoF book — a static method on the class itself rather than an overridable instance method

## Exam-Relevant Points

- Factory Method is classified as a **creational** pattern, one of 23 GoF patterns
- The pattern **relies on inheritance** (subclassing) to vary the product being created — this distinguishes it from Abstract Factory which uses object composition
- The factory method can be **abstract** (forcing subclasses to implement) or **concrete with a default** (allowing optional override)
- The Creator does **not** instantiate ConcreteProduct directly — it calls the factory method, maintaining loose coupling
- Real-world framework examples: `Document.createElement()` (HTML5 DOM), `QMainWindow::createPopupMenu` (Qt), `javax.xml.parsers.DocumentBuilderFactory` (Java), `IDbCommand.CreateParameter` (ADO.NET)
- Factory Method makes code adhere to the **Open-Closed Principle**: adding a new product type requires only a new ConcreteCreator subclass
- The MazeGame example demonstrates how Factory Method **combines with Template Method**: the constructor defines the algorithm skeleton while `makeRoom()` is the hook that varies
- Distinguish from Simple Factory (not a GoF pattern) and Abstract Factory (creates families of objects, uses composition over inheritance)
