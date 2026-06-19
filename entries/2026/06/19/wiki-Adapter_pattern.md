---
source: sources/wiki-Adapter_pattern.md
source_url: https://en.wikipedia.org/wiki/Adapter_pattern
---

## Adapter Pattern (Structural Design Pattern)

The Adapter pattern (also called Wrapper) is a structural GoF design pattern that allows an existing class's interface to be used as a different interface, enabling classes with incompatible interfaces to work together without modifying their source code. It is one of the 23 Gang of Four patterns from *Design Patterns: Elements of Reusable Object-Oriented Software* (1994).

## Key Concepts

- **Core purpose**: Convert the interface of a class (the *adaptee*) into another interface (the *target*) that clients expect
- **Three roles**: **Client** (needs the target interface), **Adaptee** (has useful functionality but wrong interface), **Adapter** (bridges the two)
- **Two structural variants**:
  - **Object adapter**: Holds a reference to the adaptee and delegates calls at runtime (uses composition). More flexible — can adapt an adaptee and all its subclasses.
  - **Class adapter**: Inherits from both the target interface and the adaptee (uses multiple inheritance). Limited to languages supporting multiple inheritance; adapts a specific concrete class only.
- **Transparency**: Clients don't know whether they're working with a target directly or through an adapter
- **No source modification**: The adaptee's code is never changed — the adapter wraps it
- **Runtime adapter variant**: Uses a registry/factory to look up adapters dynamically, enabling multiple "views" of the same data source without altering class hierarchies

## Commands and Syntax

**Naming convention for adapter classes:**
```
[ClassName]To[Interface]Adapter
```
Example: `DAOToProviderAdapter`, `LightningToMicroUsbAdapter`

**Object adapter structure (Java):**
```java
class LightningToMicroUsbAdapter implements IMicroUsbPhone {
    private final ILightningPhone lightningPhone;  // holds adaptee

    public LightningToMicroUsbAdapter(ILightningPhone lightningPhone) {
        this.lightningPhone = lightningPhone;       // inject adaptee
    }

    @Override
    public void useMicroUsb() {
        lightningPhone.useLightning();              // delegate to adaptee
    }

    @Override
    public void recharge() {
        lightningPhone.recharge();                  // delegate to adaptee
    }
}
```

**Runtime adapter with factory/registry:**
```java
// Register adapter
AdapterFactory.getInstance().registerAdapter(
    ClassA.class, ClassAFormat1Adapter.class, "format1");

// Look up and use adapter at runtime
Adapter adapter = AdapterFactory.getInstance()
    .getAdapterFromTo(ClassA.class, StringProvider.class, "format1");
StringProvider provider = (StringProvider) adapter.adapt(classA);
String string = provider.getStringData();
```

## Relationships

- **Decorator pattern**: Both are "wrappers," but Decorator adds/alters behavior at runtime while Adapter converts an interface. Decorator preserves the same interface; Adapter changes it.
- **Facade pattern**: Simplifies an interface (often to a subsystem); Adapter converts one interface to another. Facade creates a new simplified interface; Adapter matches an existing expected interface.
- **Delegation pattern**: Object adapters are a specific application of delegation (composition over inheritance)
- **Dependency Inversion Principle**: Can be viewed as the high-level module defining its own adapter interface to the low-level module
- **Ports and Adapters Architecture** (Hexagonal): Uses adapters as a core architectural concept to decouple domain logic from external systems
- **Bridge pattern**: Both involve indirection, but Bridge separates abstraction from implementation up front; Adapter retrofits compatibility after the fact
- **Proxy pattern**: Also wraps an object but provides the same interface; Adapter provides a different interface

## Exam-Relevant Points

- The Adapter pattern is classified as a **structural** pattern in the GoF catalog
- **Object adapter uses composition** (has-a); **class adapter uses inheritance** (is-a via multiple inheritance)
- Object adapters are generally preferred because they don't require multiple inheritance and can adapt any subclass of the adaptee
- Class adapters are constrained in languages like Java (pre-JDK 1.8) that don't support multiple inheritance of classes — the target must be defined as an interface
- The adapter does **not** modify the adaptee — it wraps it
- Distinguish from Decorator (same interface, adds behavior), Facade (simplified interface), and Proxy (same interface, controls access)
- The pattern solves three specific problems: reusing a class lacking the required interface, making incompatible interfaces work together, and providing an alternative interface for a class
- The adapter constructor typically takes the adaptee as a parameter and stores it as an instance variable
