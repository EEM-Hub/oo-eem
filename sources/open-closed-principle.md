---
source: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
fetched: 2026-06-17
---

# Open-Closed Principle

The open-closed principle (OCP) is a concept in object-oriented programming and one of the five SOLID principles of object-oriented design (the "O" in SOLID).

## Definition

The principle states that "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification." In practice, this means a software entity should allow its behavior to be extended without requiring changes to its source code.

The term has been applied in two distinct ways over the years. Both approaches use generalizations such as inheritance or delegate functions to address the core tension, though they differ in goals, techniques, and outcomes.

## Meyer's Open-Closed Principle

Bertrand Meyer is widely credited with coining the term, which first appeared in his 1988 book *Object-Oriented Software Construction*.

Meyer defined openness and closedness as follows:

- **Open**: A module is open "if it is still available for extension," such as adding new fields to data structures or new functions.
- **Closed**: A module is closed when it "is available for use by other modules," meaning it has a stable, well-defined interface.

When Meyer wrote, adding fields or functions to a library typically forced changes in all dependent programs. His solution relied on object-oriented **implementation inheritance**:

A class could be compiled, stored in a library, and used by clients (making it closed), yet any new class could inherit from it and add features (making it open). Defining a descendant class wouldn't require modifying the original class or disturbing its existing clients.

## Polymorphic Open-Closed Principle

During the 1990s, the principle was popularly redefined around **abstracted interfaces**. Under this interpretation, implementations can be changed and multiple implementations can be polymorphically substituted for one another.

Unlike Meyer's version -- which emphasized inheriting concrete implementations -- this approach advocates inheritance from **abstract base classes**. Interface specifications are reused through inheritance, but the underlying implementation need not be. The existing interface remains closed to modification, while new implementations must at minimum satisfy that interface.

### Key Contributors

- **Robert C. Martin** published "The Open-Closed Principle" in *C++ Report* (January 1996), which became one of the seminal works advocating this polymorphic approach.
- **Craig Larman** (2001) connected the open-closed principle to Alistair Cockburn's *Protected Variations* pattern and to David Parnas's work on **information hiding**, published in *IEEE Software*.

## See Also

- SOLID
- Robustness principle

## References

1. Meyer, Bertrand (1988). *Object-Oriented Software Construction*. Prentice Hall. ISBN 0-13-629049-3.
2. Robert C. Martin, "The Open-Closed Principle," *C++ Report*, January 1996.
3. Larman, Craig (May-June 2001). "Protected Variation: The Importance of Being Closed." *IEEE Software*, 18(2), pp. 89-91. doi:10.1109/52.922731.
