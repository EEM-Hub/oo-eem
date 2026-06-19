---
source: sources/wiki-Template_method_pattern.md
source_url: https://en.wikipedia.org/wiki/Template_method_pattern
---

## Template Method Pattern

The Template Method is a behavioral design pattern from the Gang of Four catalog that defines the skeleton of an algorithm in a superclass method, deferring specific steps to subclasses. The superclass controls the overall workflow while subclasses customize variable parts through overriding, without changing the algorithm's structure.

## Key Concepts

- **Template method**: A method in an abstract base class that implements the invariant parts of an algorithm and calls helper methods for the variable parts
- **Abstract methods (primitive operations)**: Helper methods with no implementation in the base class; subclasses *must* provide concrete implementations
- **Hook methods**: Helper methods with empty (do-nothing) bodies in the base class; subclasses *may* override them to customize behavior
- **Subclasses must not override the template method itself** — only the helper methods (abstract or hook)
- The pattern is an example of **inversion of control**: the high-level algorithm in the base class calls down to lower-level steps selected at runtime by the concrete subclass
- At runtime, the template method executes via **self-message dispatch**: when the base class sends a message to `self`, polymorphism routes it to the subclass's overridden implementation if one exists
- The pattern has two structural parts: (1) the base class with the template method and default/abstract helpers, and (2) concrete subclasses that fill in the variant parts

## Commands and Syntax

**Structural pattern (C++ example):**
```cpp
class AbstractClass {
public:
    // Template method — do NOT override in subclasses
    void templateMethod() {
        invariantStep();
        primitiveOperation1();  // abstract — subclass must implement
        hookMethod();           // hook — subclass may override
        primitiveOperation2();  // abstract
    }
    virtual void primitiveOperation1() = 0;
    virtual void primitiveOperation2() = 0;
    virtual void hookMethod() {}  // default empty body
    virtual ~AbstractClass() = default;
private:
    void invariantStep() { /* fixed logic */ }
};

class ConcreteClass : public AbstractClass {
public:
    void primitiveOperation1() override { /* variant logic */ }
    void primitiveOperation2() override { /* variant logic */ }
};
```

## Relationships

- **Strategy pattern**: Both allow varying an algorithm, but Strategy uses composition (swap entire algorithm object), while Template Method uses inheritance (override individual steps). Template Method is white-box reuse; Strategy is black-box reuse
- **Inversion of control**: Template Method is a foundational mechanism for IoC — the framework (base class) calls application code (subclass), not the reverse ("Hollywood Principle")
- **Adapter pattern**: Can work alongside Template Method when adapting interfaces within the hook/primitive methods
- **Frameworks**: Template Method is used prominently in frameworks to define invariant architecture while exposing hook points for application-specific customization
- **Generation Gap pattern**: When combined with code generators, the generated code forms the abstract superclass and hand-written customizations go in subclasses, preventing regeneration from overwriting custom code
- **Inheritance and method overriding**: The pattern depends fundamentally on these OO mechanisms

## Exam-Relevant Points

- Template Method is a **behavioral** pattern (not structural or creational)
- The template method should be **non-virtual / final** — subclasses override only the helper methods, never the template method itself
- Two types of helper methods: **abstract methods** (mandatory override) vs. **hook methods** (optional override with empty default)
- The pattern **controls where specialization is permitted** — subclasses can only vary specific steps, not the overall workflow
- Key benefit: **eliminates code duplication** by factoring the common algorithm into the base class
- It is an example of **inversion of control** — the base class drives execution, not the subclass
- Defined by Gamma, Helm, Johnson, and Vlissides (GoF) in *Design Patterns* (1994), pages 325–330
- Distinguish from **Template processor** (unrelated text-substitution concept)
- The **Generation Gap pattern** is a specialized application of Template Method for code generation scenarios
