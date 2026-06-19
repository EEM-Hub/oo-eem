---
source: sources/wiki-Proxy_pattern.md
source_url: https://en.wikipedia.org/wiki/Proxy_pattern
---

## Proxy Pattern (Structural Design Pattern)

The Proxy pattern provides a surrogate or placeholder object that controls access to another object. It is one of the 23 GoF structural design patterns. The proxy implements the same interface as the real subject, making it transparent to clients, while adding behavior such as lazy loading, access control, or remote communication.

## Key Concepts

- **Core idea**: A proxy is a wrapper object that the client calls instead of the real object; both implement the same interface (`Subject`), so clients cannot distinguish between them.
- **Intent**: Control access to an object and/or add additional functionality (caching, logging, access checks) without modifying the real object.
- **Structure**: Three participants — `Subject` (interface), `RealSubject` (the actual object), and `Proxy` (holds a reference to `RealSubject`, forwards requests to it).
- **The proxy maintains a reference** (`realSubject`) to the real object and delegates calls via `realSubject.operation()`.
- **Transparency**: Clients interact with the proxy exactly as they would with the real subject — same interface contract.

## Proxy Variants

- **Remote Proxy**: Represents an object in a different address space (e.g., an ATM holding proxy objects for bank data on a remote server). Method calls on the proxy translate to remote method invocations.
- **Virtual Proxy**: Defers creation of expensive objects until actually needed (lazy loading). A skeleton stands in until the real object is loaded on demand.
- **Protection Proxy**: Controls access to a resource based on access rights or preconditions. Checks permissions before forwarding the request.

## Commands and Syntax

C++ example demonstrating a virtual proxy with lazy loading:

```cpp
// Subject interface
class Image {
public:
    virtual void display() const = 0;
    virtual ~Image() = default;
};

// RealSubject — expensive to construct
class RealImage : public Image {
    string filename;
public:
    explicit RealImage(const string& file) : filename{file} { loadFromDisk(); }
    void display() const override { /* show image */ }
private:
    void loadFromDisk() const { /* heavy I/O */ }
};

// Proxy — defers construction of RealImage until first use
class ProxyImage : public Image {
    string filename;
    mutable unique_ptr<RealImage> realImage;
public:
    explicit ProxyImage(const string& file) : filename{file} {}
    void display() const override {
        if (!realImage)
            realImage = std::make_unique<RealImage>(filename);
        realImage->display();
    }
};
```

- First call to `display()` triggers the expensive load; subsequent calls reuse the cached real object.

## Relationships

- **Decorator pattern**: Both wrap an object, but Decorator adds behavior while Proxy controls access. Decorator typically stacks multiple wrappers; Proxy usually stands alone.
- **Adapter pattern**: Adapter changes the interface of the wrapped object; Proxy preserves the same interface.
- **Facade pattern**: Facade simplifies a complex subsystem behind a new interface; Proxy wraps a single object with the same interface.
- **Composite pattern**: Both can involve recursive or delegating structures, but Composite models part-whole hierarchies.
- **Lazy initialization**: Virtual proxy is a common implementation mechanism for lazy loading.
- **Forwarding (OOP)**: The proxy delegates calls to the real subject — forwarding is the core mechanism.

## Exam-Relevant Points

- Proxy is a **structural** GoF pattern — know its classification.
- The proxy and real subject **must implement the same interface** — this is what makes the pattern transparent to clients.
- Know the three main proxy types and when each applies: **Remote** (different address space), **Virtual** (deferred creation), **Protection** (access control).
- The proxy **holds a reference** to the real subject and forwards requests — it does not inherit from the real subject.
- Distinguish Proxy from Decorator: Proxy controls **access**, Decorator adds **behavior**. Proxy typically manages the lifecycle of the real object; Decorator does not.
- Distinguish Proxy from Adapter: Proxy keeps the **same interface**; Adapter **changes** the interface.
- Virtual proxy is the classic example of the **lazy loading** technique applied via a design pattern.
- The pattern enables adding cross-cutting concerns (caching, logging, security checks) without modifying the real subject — supports the **Open/Closed Principle**.
