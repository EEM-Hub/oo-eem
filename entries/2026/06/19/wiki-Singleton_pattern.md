---
source: sources/wiki-Singleton_pattern.md
source_url: https://en.wikipedia.org/wiki/Singleton_pattern
---

## Singleton Pattern

The Singleton pattern is a creational design pattern from the Gang of Four catalog that restricts a class to exactly one instance and provides a global access point to it. The term derives from the mathematical concept of a singleton (a set with exactly one element). It is one of the most widely known — and most debated — design patterns in object-oriented programming.

## Key Concepts

- **Single instance guarantee**: The class itself enforces that only one instance can ever exist
- **Global access point**: A static method (typically `getInstance()`) provides access to the sole instance
- **Controlled instantiation**: Constructors are made private to prevent external instantiation
- **Three core responsibilities**: (1) ensure only one instance, (2) provide easy access to it, (3) control instantiation
- **Preferred over global variables** because singletons don't pollute the global namespace and support lazy allocation/initialization
- **Lazy initialization**: Instance creation is deferred until first access, conserving resources
- **Thread safety concern**: Lazy initialization in multithreaded programs can cause race conditions, creating multiple instances
- **Double-checked locking**: A thread-safe lazy initialization technique using `volatile` + `synchronized` (Java 5+)
- **Meyers Singleton (C++)**: Uses a local static variable inside `getInstance()`, leveraging C++11 guarantees for thread-safe initialization without explicit locking

## Commands and Syntax

**Classic C++ implementation (pointer-based)**:
```cpp
class Singleton {
private:
    Singleton() = default;
    inline static Singleton* instance = nullptr;
public:
    static Singleton& getInstance() {
        if (!instance) instance = new Singleton();
        return *instance;
    }
    Singleton(const Singleton&) = delete;
    Singleton& operator=(const Singleton&) = delete;
    static void destroy() { delete instance; instance = nullptr; }
};
```

**Meyers Singleton (C++11+, preferred)**:
```cpp
static Singleton& getInstance() {
    static Singleton instance;  // thread-safe in C++11+
    return instance;
}
```

**Thread-safe Java (double-checked locking)**:
```java
public class Singleton {
    private static volatile Singleton instance = null;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) {
            synchronized (Singleton.class) {
                if (instance == null) {
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}
```

## Relationships

- **Creational pattern family**: One of five GoF creational patterns alongside Abstract Factory, Builder, Factory Method, and Prototype
- **Foundation for other patterns**: Often used as the implementation basis for Abstract Factory, Factory Method, Builder, and Prototype patterns
- **Facade objects** are frequently singletons since only one facade is typically needed
- **Multiton pattern**: The generalization of Singleton — manages a map of named instances rather than a single one
- **Initialization-on-demand holder idiom**: A Java-specific thread-safe alternative to double-checked locking
- **Violates Single Responsibility Principle**: The class manages both its own uniqueness and its domain logic
- **Tension with Dependency Injection**: Singletons introduce hidden dependencies; DI makes dependencies explicit and testable

## Exam-Relevant Points

- Singleton is a **creational** GoF pattern — know the classification
- The two key implementation steps: **private constructor** + **static accessor method** returning a reference to a private static instance
- **Lazy vs eager initialization**: Lazy defers creation to first use; eager creates at class load time
- **Thread safety**: Naive lazy initialization is **not thread-safe**; solutions include double-checked locking (Java), Meyers singleton (C++11), or initialization-on-demand holder idiom (Java)
- In Java, the `volatile` keyword on the instance field is **required** for double-checked locking to work correctly (Java 5+ memory model)
- **Anti-pattern criticism**: Introduces global state, increases coupling, hinders unit testing, violates SRP, prevents concurrent use of multiple instances
- **Copy/assignment prevention**: In C++, copy constructor and assignment operator must be deleted
- Common real-world use case: **logging** — all objects need a uniform access point writing to a single source
- Singleton is distinct from a global variable: it supports lazy initialization and doesn't pollute the global namespace
