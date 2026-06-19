---
source: https://en.wikipedia.org/wiki/Decorator_pattern
fetched: 2026-06-19
---

Design pattern in object-oriented programming Not to be confused with [the concept of "decorators" in Python](./Python_syntax_and_semantics#Decorators). 

In [object-oriented programming](./Object-oriented_programming), the **decorator pattern** is a [design pattern](./Design_pattern_(computer_science)) that allows behavior to be added to an individual [object](./Object_(computer_science)) dynamically, without affecting the behavior of other instances of the same [class](./Class_(computer_science)).[[1]](./Decorator_pattern#cite_note-1) The decorator pattern is often useful for adhering to the [Single Responsibility Principle](./Single_responsibility_principle), as it enables functionality to be distributed across classes with distinct concerns.[[2]](./Decorator_pattern#cite_note-2) It also supports the [Open–Closed Principle](./Open-closed_principle), since a class's functionality can be extended without modifying its source code.[[3]](./Decorator_pattern#cite_note-3) Using decorators can be more flexible and efficient than subclassing, as an object's behavior can be augmented or combined at runtime without creating an entirely new class hierarchy.

 

## Overview

 

The *decorator*[[4]](./Decorator_pattern#cite_note-GoF-4) design pattern is one of the twenty-three *[Gang-of-Four design patterns](./Design_Patterns)*; these describe how to solve recurring design problems and design flexible and reusable object-oriented software—that is, objects which are easier to implement, change, test, and reuse.

 

The decorator pattern provides a flexible alternative to subclassing for extending functionality. When using subclassing, different subclasses extend a class in different ways. However, an extension is bound to the class at compile-time and can't be changed at run-time. The decorator pattern allows responsibilities to be added (and removed from) an object dynamically at run-time. It is achieved by defining `Decorator` objects that

 
- implement the interface of the extended (decorated) object (`Component`) transparently by forwarding all requests to it.
- perform additional functionality before or after forwarding a request.

 

This allows working with different `Decorator` objects to extend the functionality of an object dynamically at run-time.[[5]](./Decorator_pattern#cite_note-:0-5)

 

## Intent

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e9/Decorator_UML_class_diagram.svg/500px-Decorator_UML_class_diagram.svg.png)](./File:Decorator_UML_class_diagram.svg)Decorator [UML](./Unified_Modeling_Language) class diagram 

The decorator pattern can be used to extend (decorate) the functionality of a certain object statically, or in some cases at [run-time](./Run_time_(program_lifecycle_phase)), independently of other instances of the same [class](./Class_(computer_science)), provided some groundwork is done at design time. This is achieved by designing a new *Decorator* class that [wraps](./Wrapper_pattern) the original class. This wrapping could be achieved by the following sequence of steps:

 
1. Subclass the original *Component* class into a *Decorator* class (see UML diagram);
2. In the *Decorator* class, add a *Component* pointer as a field;
3. In the *Decorator* class, pass a *Component* to the *Decorator* constructor to initialize the *Component* pointer;
4. In the *Decorator* class, [forward](./Forwarding_(object-oriented_programming)) all *Component* methods to the *Component* pointer {{Clarify|No mention of this in the refs, and the phrase does not make clear which space is lost: the decorated object's, or the decorator's?|date=May 2011}} (This implies that all Decorator fields coming from the Component motherclass will never be used and their memory space will be wasted—That is an accepted drawback of the decorator pattern) ; and
5. In the ConcreteDecorator class, override any *Component* method(s) whose behavior needs to be modified.

 

This pattern is designed so that multiple decorators can be stacked on top of each other, each time adding a new functionality to the overridden method(s).

 

Note that decorators and the original class object share a common set of features. In the previous diagram, the operation() method was available in both the decorated and undecorated versions.

 

The decoration features (e.g., methods, properties, or other members) are usually defined by an interface, [mixin](./Mixin) (a.k.a. [trait](./Trait_(computer_programming))) or class inheritance which is shared by the decorators and the decorated object. In the previous example, the class *Component* is inherited by both the ConcreteComponent and the subclasses that descend from *Decorator*.

 

The decorator pattern is an alternative to [subclassing](./Subclass_(computer_science)). Subclassing introduces additional behavior by deriving new classes at [compile time](./Compile_time), and such modifications affect all instances of the original class. In contrast, the Decorator pattern allows new behaviors to be dynamically added to selected objects at [run-time](./Run_time_(program_lifecycle_phase)) without impacting other instances of the same class. This design enables more fine-grained and flexible behavior extension, thereby improving code reusability and maintainability.[[5]](./Decorator_pattern#cite_note-:0-5)

 

This difference becomes most important when there are several *independent* ways of extending functionality. In some [object-oriented programming languages](./Object-oriented_programming_language), classes cannot be created at runtime, and it is typically not possible to predict, at design time, what combinations of extensions will be needed. This would mean that a new class would have to be made for every possible combination. By contrast, decorators are objects, created at runtime, and can be combined on a per-use basis. The I/O Streams implementations of both [Java](./Java_Platform,_Standard_Edition#java.io) and the [.NET Framework](./.NET_Framework) incorporate the decorator pattern.[[5]](./Decorator_pattern#cite_note-:0-5)

 

## Motivation

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c6/UML2_Decorator_Pattern.png/500px-UML2_Decorator_Pattern.png)](./File:UML2_Decorator_Pattern.png)UML diagram for the window example 

As an example, consider a window in a [windowing system](./Windowing_system). To allow [scrolling](./Scrolling) of the window's contents, one may wish to add horizontal or vertical [scrollbars](./Scrollbar) to it, as appropriate. Assume windows are represented by instances of the *Window* interface, and assume this class has no functionality for adding scrollbars. One could create a subclass *ScrollingWindow* that provides them, or create a *ScrollingWindowDecorator* that adds this functionality to existing *Window* objects. At this point, either solution would be fine.

 

Now, assume one also desires the ability to add borders to windows. Again, the original *Window* class has no support. The *ScrollingWindow* subclass now poses a problem, because it has effectively created a new kind of window. If one wishes to add border support to many but not *all* windows, one must create subclasses *WindowWithBorder* and *ScrollingWindowWithBorder*, etc. This problem gets worse with every new feature or window subtype to be added. For the decorator solution, a new *BorderedWindowDecorator* is created. Any combination of *ScrollingWindowDecorator* or *BorderedWindowDecorator* can decorate existing windows. If the functionality needs to be added to all Windows, the base class can be modified. On the other hand, sometimes (e.g., using external frameworks) it is not possible, legal, or convenient to modify the base class.

 

In the previous example, the *SimpleWindow* and *WindowDecorator* classes implement the *Window* interface, which defines the *draw()* method and the *getDescription()* method that are required in this scenario, in order to decorate a window control.

 

## Common usecases

 

### Applying decorators

 

Adding or removing decorators on command (like a button press) is a common UI pattern, often implemented along with the [Command design pattern](./Command_pattern). For example, a text editing application might have a button to highlight text. On button press, the individual text glyphs currently selected will all be wrapped in decorators that modify their draw() function, causing them to be drawn in a highlighted manner (a real implementation would probably also use a demarcation system to maximize efficiency). 

 

Applying or removing decorators based on changes in state is another common use case. Depending on the scope of the state, decorators can be applied or removed in bulk. Similarly, the [State design pattern](./State_pattern) can be implemented using decorators instead of subclassed objects encapsulating the changing functionality. The use of decorators in this manner makes the State object's internal state and functionality more compositional and capable of handling arbitrary complexity.

 

### Usage in Flyweight objects

 Main article: [Flyweight pattern](./Flyweight_pattern) 

Decoration is also often used in the [Flyweight design pattern](./Flyweight_pattern). Flyweight objects are divided into two components: an invariant component that is shared between all flyweight objects; and a variant, decorated component that may be partially shared or completely unshared. This partitioning of the flyweight object is intended to reduce memory consumption. The decorators are typically cached and reused as well. The decorators will all contain a common reference to the shared, invariant object. If the decorated state is only partially variant, then the decorators can also be shared to some degree - though care must be taken not to alter their state while they're being used. iOS's UITableView implements the flyweight pattern in this manner - a tableview's reusable cells are decorators that contains a references to a common tableview row object, and the cells are cached / reused.

 

### Obstacles of interfacing with decorators

 

Applying combinations of decorators in diverse ways to a collection of objects introduces some problems interfacing with the collection in a way that takes full advantage of the functionality added by the decorators. The use of an [Adapter](./Adapter_Pattern) or [Visitor](./Visitor_Pattern) patterns can be useful in such cases. Adapter patterns can unify disparate interfaces into a common, expected API. Similarly, the Visitor pattern enables operations to be performed across a structure of decorated objects without embedding the operation logic within the objects themselves. Interfacing with multiple layers of decorators poses additional challenges and logic of Adapters and Visitors must be designed to account for that.

 

### Architectural relevance

 

Decorators support a [compositional](./Composition_over_inheritance) rather than a top-down, hierarchical approach to extending functionality. A decorator makes it possible to add or alter behavior of an interface at run-time. They can be used to wrap objects in a multilayered, arbitrary combination of ways. Doing the same with subclasses means implementing complex networks of multiple inheritance, which is memory-inefficient and at a certain point just cannot scale. Likewise, attempting to implement the same functionality with properties bloats each instance of the object with unnecessary properties. 
For the above reasons decorators are often considered a memory-efficient alternative to subclassing. 

 

Decorators can also be used to specialize objects which are not subclassable, whose characteristics need to be altered at runtime (as mentioned elsewhere), or generally objects that are lacking in some needed functionality.

 

### Usage in enhancing APIs

 

The decorator pattern also can augment the [Facade pattern](./Facade_pattern). A facade is designed to simply interface with the complex system it encapsulates, but it does not add functionality to the system. However, the wrapping of a complex system provides a space that may be used to introduce new functionality based on the coordination of subcomponents in the system. 
For example, a facade pattern may unify many different languages dictionaries under one multi-language dictionary interface. The new interface may also provide new functions for translating words between languages. 
This is a hybrid pattern - the unified interface provides a space for augmentation. Think of decorators as not being limited to wrapping individual objects, but capable of wrapping clusters of objects in this hybrid approach as well.

 

## Alternatives to decorators

 

As an alternative to the decorator pattern, the [adapter](./Adapter_pattern) can be used when the wrapper must respect a particular interface and must support [polymorphic](./Polymorphism_(computer_science)) behavior, and the [Facade](./Facade_pattern) when an easier or simpler interface to an underlying object is desired.[[6]](./Decorator_pattern#cite_note-6)

 
| Pattern | Intent |
| --- | --- |
| Adapter | Converts one interface to another so that it matches what the client is expecting |
| Decorator | Dynamically adds responsibility to the interface by wrapping the original code |
| Facade | Provides a simplified interface |

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/8/83/W3sDesign_Decorator_Design_Pattern_UML.jpg)](./File:W3sDesign_Decorator_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Decorator design pattern[[7]](./Decorator_pattern#cite_note-7) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), 
the abstract `Decorator` class maintains a reference (`component`) 
to the decorated object (`Component`) and forwards all requests to it
(`component.operation()`). 
This makes `Decorator` transparent (invisible) to clients of `Component`.

 

Subclasses (`Decorator1`,`Decorator2`) implement additional behavior
(`addBehavior()`) that should be added to the `Component` (before/after forwarding a request to it).

The sequence diagram 
shows the run-time interactions: The `Client` object 
works through `Decorator1` and `Decorator2` objects to
extend the functionality of a `Component1` object.

The `Client` calls `operation()` 
on `Decorator1`, which forwards the request to `Decorator2`.
`Decorator2` performs `addBehavior()` after forwarding 
the request to `Component1` and returns to
`Decorator1`, which performs `addBehavior()`  
and returns to the `Client`.

 

## Examples

  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Decorator  

### C++

 

This implementation (which uses C++23 features) is based on the pre C++98 implementation in the book.

 
```
import std;

using std::unique_ptr;

// Beverage interface.
class Beverage {
public:
    virtual void drink() = 0;
    virtual ~Beverage() = default;
};

// Drinks which can be decorated.
class Coffee: public Beverage {
public:
    virtual void drink() override {
        std::print("Drinking Coffee");
    }
};

class Soda: public Beverage {
public:
    virtual void drink() override {
        std::print("Drinking Soda");
    }
};

class BeverageDecorator: public Beverage {
private:
    unique_ptr<Beverage> component;
protected:
    void callComponentDrink() {
        if (component) {
            component->drink();
        }
    }
public:
    BeverageDecorator() = delete;

    explicit BeverageDecorator(unique_ptr<Beverage> component): 
        component{std::move(component)} {}
  
    virtual void drink() = 0;
};

class Milk: public BeverageDecorator {
private:
    float percentage;
public:
    Milk(unique_ptr<Beverage> component, float percentage):
        BeverageDecorator(std::move(component)), percentage{percentage} {}

    virtual void drink() override {
        callComponentDrink();
        std::print(", with milk of richness {}%", percentage);
    }
};

class IceCubes: public BeverageDecorator {
private:
    int count;
public:
    IceCubes(unique_ptr<Beverage> component, int count):
        BeverageDecorator(std::move(component)), count{count} {}

    virtual void drink() override {
        callComponentDrink();
        std::print(", with {} ice cubes", count);
    }
};

class Sugar: public BeverageDecorator {
private:
    int spoons = 1;
public:
    Sugar(unique_ptr<Beverage> component, int spoons):
        BeverageDecorator(std::move(component)), spoons{spoons} {}
  
    virtual void drink() override {
        callComponentDrink();
        std::print(", with {} spoons of sugar", spoons);
    }
};

int main(int argc, char* argv[]) { 
    unique_ptr<Beverage> soda = std::make_unique<Soda>();
    soda = std::make_unique<IceCubes>(std::move(soda), 3);
    soda = std::make_unique<Sugar>(std::move(soda), 1);

    soda->drink();
    std::println();
  
    unique_ptr<Beverage> coffee = std::make_unique<Coffee>();
    coffee = std::make_unique<IceCubes>(std::move(coffee), 16);
    coffee = std::make_unique<Milk>(std::move(coffee), 3.);
    coffee = std::make_unique<Sugar>(std::move(coffee), 2);

    coffee->drink();

    return 0;
}

```
 

The program output is like

 
```
Drinking Soda, with 3 ice cubes, with 1 spoons of sugar
Drinking Coffee, with 16 ice cubes, with milk of richness 3%, with 2 spoons of sugar

```
 

Full example can be tested on a [godbolt page](https://godbolt.org/z/s848nWozP).

 

### C++

 

Two options are presented here: first, a dynamic, runtime-composable decorator (has issues with calling decorated functions unless proxied explicitly) and a decorator that uses mixin inheritance.

 

#### Dynamic decorator

 
```
import std;

using std::string;

class Shape {
public:
    virtual ~Shape() = default;
    virtual string getName() const = 0;
};

class Circle: public Shape {
private:
    float radius = 10.0f;
public:
    void resize(float factor) noexcept { 
        radius *= factor; 
    }

    [[nodiscard]]
    string getName() const override {
        return std::format("A circle of radius {}", radius);
    }
};

class ColoredShape: public Shape {
private:
    string color;
    Shape& shape;
public:
    ColoredShape(const string& color, Shape& shape): 
        color{color}, shape{shape} {}

    [[nodiscard]]
    string getName() const override {
        return std::format("{} which is colored {}", shape.getName(), color);
    }
};

int main() {
    Circle circle;
    ColoredShape coloredShape{"red", circle};
    std::println("{}", coloredShape.getName());
}

```
 
```
import std;

using std::string;
using std::unique_ptr;

class WebPage {
public:
    virtual void display() = 0;
    virtual ~WebPage() = default;
};

class BasicWebPage: public WebPage {
private:
    string html;
public:
    void display() override {
        std::println("Basic WEB page");
    }
};

class WebPageDecorator: public WebPage {
private:
    unique_ptr<WebPage> webPage;
public:
    explicit WebPageDecorator(unique_ptr<WebPage> webPage): 
        webPage{std::move(webPage)} {}

    void display() override {
        webPage->display();
    }
};

class AuthenticatedWebPage: public WebPageDecorator {
public:
    explicit AuthenticatedWebPage(unique_ptr<WebPage> webPage):
        WebPageDecorator(std::move(webPage)) {}

    void authenticateUser() {
        std::println("authentication done");
    }

    void display() override {
        authenticateUser();
        WebPageDecorator::display();
    }
};

class AuthorizedWebPage: public WebPageDecorator {
public:
    explicit AuthorizedWebPage(unique_ptr<WebPage> webPage):
        WebPageDecorator(std::move(webPage)) {}

    void authorizedUser() {
        std::println("authorized done");
    }

    void display() override {
        authorizedUser();
        WebPageDecorator::display();
    }
};

int main(int argc, char* argv[]) {
    unique_ptr<WebPage> myPage = std::make_unique<BasicWebPage>();

    myPage = std::make_unique<AuthorizedWebPage>(std::move(myPage));
    myPage = std::make_unique<AuthenticatedWebPage>(std::move(myPage));
    myPage->display();
    std::println();
    return 0;
}

```
 

#### Static decorator (mixin inheritance)

 

This example demonstrates a static Decorator implementation, which is possible due to C++ ability to inherit from the template argument.

 
```
import std;

using std::string;

class Circle {
private:
    float radius = 10.0f;
public:
    void resize(float factor) noexcept { 
        radius *= factor; 
    }

    [[nodiscard]]
    string getName() const {
        return std::format("A circle of radius {}", radius);
    }
};

template <typename T>
class ColoredShape: public T {
private:
    string color;
public:
    explicit ColoredShape(const string& color): 
        color{color} {}
    
    [[nodiscard]]
    string getName() const {
        return std::format("{} which is colored {}", T::getName(), color);
    }
};

int main() {
    ColoredShape<Circle> redCircle{"red"};
    std::println("{}", redCircle.getName());
    redCircle.resize(1.5f);
    std::println("{}", redCircle.getName());
}

```
 

### Java

 

#### First example (window/scrolling scenario)

 

The following Java example illustrates the use of decorators using the window/scrolling scenario.

  
```
// The Window interface class
public interface Window {
    void draw(); // Draws the Window
    String getDescription(); // Returns a description of the Window
}

// Implementation of a simple Window without any scrollbars
class SimpleWindow implements Window {
    @Override
    public void draw() {
        // Draw window
    }

    @Override
    public String getDescription() {
        return "simple window";
    }
}

```
 

The following classes contain the decorators for all `Window` classes, including the decorator classes themselves.

 
```
// abstract decorator class - note that it implements Window
abstract class WindowDecorator implements Window {
    private final Window windowToBeDecorated; // the Window being decorated

    public WindowDecorator(Window windowToBeDecorated) {
        this.windowToBeDecorated = windowToBeDecorated;
    }

    @Override
    public void draw() {
        windowToBeDecorated.draw(); // Delegation
    }

    @Override
    public String getDescription() {
        return windowToBeDecorated.getDescription(); // Delegation
    }
}

// The first concrete decorator which adds vertical scrollbar functionality
class VerticalScrollBarDecorator extends WindowDecorator {
    public VerticalScrollBarDecorator(Window windowToBeDecorated) {
        super(windowToBeDecorated);
    }

    @Override
    public void draw() {
        super.draw();
        drawVerticalScrollBar();
    }

    private void drawVerticalScrollBar() {
        // Draw the vertical scrollbar
    }

    @Override
    public String getDescription() {
        return String.format("%s, including vertical scrollbars", super.getDescription());
    }
}

// The second concrete decorator which adds horizontal scrollbar functionality
class HorizontalScrollBarDecorator extends WindowDecorator {
    public HorizontalScrollBarDecorator(Window windowToBeDecorated) {
        super(windowToBeDecorated);
    }

    @Override
    public void draw() {
        super.draw();
        drawHorizontalScrollBar();
    }

    private void drawHorizontalScrollBar() {
        // Draw the horizontal scrollbar
    }

    @Override
    public String getDescription() {
        return String.format("%s, including horizontal scrollbars", super.getDescription());
    }
}

```
 

Here is a test program that creates a `Window` instance which is fully decorated (i.e., with vertical and horizontal scrollbars), and prints its description:

 
```
public class DecoratedWindowTest {
    public static void main(String[] args) {
        // Create a decorated Window with horizontal and vertical scrollbars
        Window decoratedWindow = new HorizontalScrollBarDecorator (
             new VerticalScrollBarDecorator(new SimpleWindow())
        );

        // Print the Window's description
        System.out.println(decoratedWindow.getDescription());
    }
}

```
 

The output of this program is "simple window, including vertical scrollbars, including horizontal scrollbars". Notice how the `getDescription` method of the two decorators first retrieve the decorated `Window`'s description and *decorates* it with a suffix.

 

Below is the JUnit test class for the Test Driven Development

 
```
import org.junit.Assert;
import org.junit.Test;

public class WindowDecoratorTest {
	@Test
	public void testWindowDecoratorTest() {
	    Window decoratedWindow = new HorizontalScrollBarDecorator(
            new VerticalScrollBarDecorator(new SimpleWindow())
        );
      	// assert that the description indeed includes horizontal + vertical scrollbars
        Assert.assertEquals("simple window, including vertical scrollbars, including horizontal scrollbars", decoratedWindow.getDescription());
	}
}

```
 

#### Second example (coffee making scenario)

 

The next Java example illustrates the use of decorators using coffee making scenario.
In this example, the scenario only includes cost and ingredients.

  
```
// The interface Coffee defines the functionality of Coffee implemented by decorator
public interface Coffee {
    public double getCost(); // Returns the cost of the coffee
    public String getIngredients(); // Returns the ingredients of the coffee
}

// Extension of a simple coffee without any extra ingredients
public class SimpleCoffee implements Coffee {
    @Override
    public double getCost() {
        return 1;
    }

    @Override
    public String getIngredients() {
        return "Coffee";
    }
}

```
 

The following classes contain the decorators for all Coffee classes, including the decorator classes themselves.

 
```
// Abstract decorator class - note that it implements Coffee interface
public abstract class CoffeeDecorator implements Coffee {
    private final Coffee decoratedCoffee;

    public CoffeeDecorator(Coffee c) {
        this.decoratedCoffee = c;
    }

    @Override
    public double getCost() { // Implementing methods of the interface
        return decoratedCoffee.getCost();
    }

    @Override
    public String getIngredients() {
        return decoratedCoffee.getIngredients();
    }
}

// Decorator WithMilk mixes milk into coffee.
// Note it extends CoffeeDecorator.
class WithMilk extends CoffeeDecorator {
    public WithMilk(Coffee c) {
        super(c);
    }

    @Override
    public double getCost() { // Overriding methods defined in the abstract superclass
        return super.getCost() + 0.5;
    }

    @Override
    public String getIngredients() {
        return String.format("%s, Milk", super.getIngredients());
    }
}

// Decorator WithSprinkles mixes sprinkles onto coffee.
// Note it extends CoffeeDecorator.
class WithSprinkles extends CoffeeDecorator {
    public WithSprinkles(Coffee c) {
        super(c);
    }

    @Override
    public double getCost() {
        return super.getCost() + 0.2;
    }

    @Override
    public String getIngredients() {
        return String.format("%s, Sprinkles", super.getIngredients());
    }
}

```
 

Here's a test program that creates a Coffee instance which is fully decorated (with milk and sprinkles), and calculate cost of coffee and prints its ingredients:

 
```
public class Main {
    public static void printInfo(Coffee c) {
        System.out.printf("Cost: %s; Ingredients: %s%n", c.getCost(), c.getIngredients());
    }

    public static void main(String[] args) {
        Coffee c = new SimpleCoffee();
        printInfo(c);

        c = new WithMilk(c);
        printInfo(c);

        c = new WithSprinkles(c);
        printInfo(c);
    }
}

```
 

The output of this program is given below:

 
```
Cost: 1.0; Ingredients: Coffee
Cost: 1.5; Ingredients: Coffee, Milk
Cost: 1.7; Ingredients: Coffee, Milk, Sprinkles

```
 

### PHP

 
```
abstract class Component
{
    protected $data;
    protected $value;

    abstract public function getData();

    abstract public function getValue();
}

class ConcreteComponent extends Component
{
    public function __construct()
    {
        $this->value = 1000;
        $this->data = "Concrete Component:\t{$this->value}\n";
    }

    public function getData()
    {
        return $this->data;
    }

    public function getValue()
    {
        return $this->value;
    }
}

abstract class Decorator extends Component
{
    
}

class ConcreteDecorator1 extends Decorator
{
    public function __construct(Component $data)
    {
        $this->value = 500;
        $this->data = $data;
    }

    public function getData()
    {
        return $this->data->getData() . "Concrete Decorator 1:\t{$this->value}\n";
    }

    public function getValue()
    {
        return $this->value + $this->data->getValue();
    }
}

class ConcreteDecorator2 extends Decorator
{
    public function __construct(Component $data)
    {
        $this->value = 500;
        $this->data = $data;
    }

    public function getData()
    {
        return $this->data->getData() . "Concrete Decorator 2:\t{$this->value}\n";
    }

    public function getValue()
    {
        return $this->value + $this->data->getValue();
    }
}

class Client
{
    private $component;

    public function __construct()
    {
        $this->component = new ConcreteComponent();
        $this->component = $this->wrapComponent($this->component);

        echo $this->component->getData();
        echo "Client:\t\t\t";
        echo $this->component->getValue();
    }

    private function wrapComponent(Component $component)
    {
        $component1 = new ConcreteDecorator1($component);
        $component2 = new ConcreteDecorator2($component1);
        return $component2;
    }
}

$client = new Client();

// Result: #quanton81

//Concrete Component:	1000
//Concrete Decorator 1:	500
//Concrete Decorator 2:	500
//Client:               2000

```
 

### Python

 

The following Python example, taken from [Python Wiki - DecoratorPattern](https://wiki.python.org/moin/DecoratorPattern), shows us how to pipeline decorators to dynamically add many behaviors in an object:

 
```
"""
Demonstrated decorators in a world of a 10x10 grid of values 0–255. 
"""

import random
from typing import Any

def s32_to_u16(x: int) -> int:
    sign: int
    if x < 0:
        sign = 0xF000
    else:
        sign = 0
    bottom: int = x & 0x00007FFF
    return bottom | sign

def seed_from_xy(x: int, y: int) -> int:
    return s32_to_u16(x) | (s32_to_u16(y) << 16)

class RandomSquare:
    def __init__(self, seed_modifier: int) -> None:
        self.seed_modifier: int = seed_modifier

    def get(self, x: int, y: int) -> int:
        seed: int = seed_from_xy(x, y) ^ self.seed_modifier
        random.seed(seed)
        return random.randint(0, 255)

class DataSquare:
    def __init__(self, initial_value: int = None) -> None:
        self.data: list[int] = [initial_value] * 10 * 10

    def get(self, x: int, y: int) -> int:
        return self.data[(y * 10) + x]  # yes: these are all 10x10

    def set(self, x: int, y: int, u: int) -> None:
        self.data[(y * 10) + x] = u

class CacheDecorator:
    def __init__(self, decorated: Any) -> None:
        self.decorated: Any = decorated
        self.cache: DataSquare = DataSquare()

    def get(self, x: int, y: int) -> int:
        if self.cache.get(x, y) == None:
            self.cache.set(x, y, self.decorated.get(x, y))
        return self.cache.get(x, y)

class MaxDecorator:
    def __init__(self, decorated: Any, max: int) -> None:
        self.decorated: Any = decorated
        self.max: int = max

    def get(self, x: int, y: int) -> None:
        if self.decorated.get(x, y) > self.max:
            return self.max
        return self.decorated.get(x, y)

class MinDecorator:
    def __init__(self, decorated: Any, min: int) -> None:
        self.decorated: Any = decorated
        self.min: int = min

    def get(self, x: int, y: int) -> int:
        if self.decorated.get(x, y) < self.min:
            return self.min
        return self.decorated.get(x, y)

class VisibilityDecorator:
    def __init__(self, decorated: Any) -> None:
        self.decorated: Any = decorated

    def get(self, x: int, y: int) -> int:
        return self.decorated.get(x, y)

    def draw(self) -> None:
        for y in range(10):
            for x in range(10):
                print("%3d" % self.get(x, y), end=' ')
            print()

if __name__ == "__main__":
    # Now, build up a pipeline of decorators:

    random_square: RandomSquare = RandomSquare(635)
    random_cache: CacheDecorator = CacheDecorator(random_square)
    max_filtered: MaxDecorator = MaxDecorator(random_cache, 200)
    min_filtered: MinDecorator = MinDecorator(max_filtered, 100)
    final: VisibilityDecorator = VisibilityDecorator(min_filtered)

    final.draw()

```
 

**Note:**

 

The Decorator Pattern (or an implementation of this design pattern in Python - as the above example) should not be confused with [Python Decorators](./Python_syntax_and_semantics#Decorators), a language feature of Python. They are different things.

 

Second to the Python Wiki:

 

The Decorator Pattern is a pattern described in the Design Patterns Book. It is a way of apparently modifying an object's behavior, by enclosing it inside a decorating object with a similar interface.
This is not to be confused with Python Decorators, which is a language feature for dynamically modifying a function or class.[[8]](./Decorator_pattern#cite_note-8)

 

### Crystal

 
```
abstract class Coffee
  abstract def cost
  abstract def ingredients
end

# Extension of a simple coffee
class SimpleCoffee < Coffee
  def cost
    1.0
  end

  def ingredients
    "Coffee"
  end
end

# Abstract decorator
class CoffeeDecorator < Coffee
  protected getter decorated_coffee : Coffee

  def initialize(@decorated_coffee)
  end

  def cost
    decorated_coffee.cost
  end

  def ingredients
    decorated_coffee.ingredients
  end
end

class WithMilk < CoffeeDecorator
  def cost
    super + 0.5
  end

  def ingredients
    super + ", Milk"
  end
end

class WithSprinkles < CoffeeDecorator
  def cost
    super + 0.2
  end

  def ingredients
    super + ", Sprinkles"
  end
end

class Program
  def print(coffee : Coffee)
    puts "Cost: #{coffee.cost}; Ingredients: #{coffee.ingredients}"
  end

  def initialize
    coffee = SimpleCoffee.new
    print(coffee)

    coffee = WithMilk.new(coffee)
    print(coffee)

    coffee = WithSprinkles.new(coffee)
    print(coffee)
  end
end

Program.new

```
 

Output:

 
```
Cost: 1.0; Ingredients: Coffee
Cost: 1.5; Ingredients: Coffee, Milk
Cost: 1.7; Ingredients: Coffee, Milk, Sprinkles

```
 

### C#

 
```
namespace Wikipedia.Examples;

interface IBike
{
    string GetDetails();
    double GetPrice();
}

class AluminiumBike : IBike
{
    public double GetPrice() => 100.0;

    public string GetDetails() => "Aluminium Bike";
}

class CarbonBike : IBike
{
    public double GetPrice() => 1000.0;

    public string GetDetails() => "Carbon";
}

abstract class BikeAccessories : IBike
{
    private readonly IBike _bike;

    public BikeAccessories(IBike bike)
    {
        _bike = bike;
    }

    public virtual double GetPrice() => _bike.GetPrice();

    public virtual string GetDetails() => _bike.GetDetails();
}

class SecurityPackage : BikeAccessories
{
    public SecurityPackage(IBike bike) : base(bike)
    {
        // ...
    }

    public override string GetDetails() => $"{base.GetDetails()} + Security Package";

    public override double GetPrice() => base.GetPrice() + 1;
}

class SportPackage : BikeAccessories
{
    public SportPackage(IBike bike) : base(bike)
    {
        // ...
    }

    public override string GetDetails() => $"{base.GetDetails()} + Sport Package";

    public override double GetPrice() => base.GetPrice() + 10;
}

public class BikeShop
{
    public void UpgradeBike()
    {
        AluminiumBike basicBike = new AluminiumBike();
        BikeAccessories upgraded = new SportPackage(basicBike);
        upgraded = new SecurityPackage(upgraded);

        Console.WriteLine($"Bike: '{upgraded.GetDetails()}' Cost: {upgraded.GetPrice()}");
    }

    static void Main(string[] args)
    {
        UpgradeBike();
    }
}

```
 

Output:

 
```
Bike: 'Aluminium Bike + Sport Package + Security Package' Cost: 111

```
 

### Ruby

 
```
class AbstractCoffee
  def print
    puts "Cost: #{cost}; Ingredients: #{ingredients}"
  end
end

class SimpleCoffee < AbstractCoffee
  def cost
    1.0
  end

  def ingredients
    "Coffee"
  end
end

class WithMilk < SimpleDelegator
  def cost
    __getobj__.cost + 0.5
  end

  def ingredients
    __getobj__.ingredients + ", Milk"
  end
end

class WithSprinkles < SimpleDelegator
  def cost
    __getobj__.cost + 0.2
  end

  def ingredients
    __getobj__.ingredients + ", Sprinkles"
  end
end

coffee = SimpleCoffee.new
coffee.print

coffee = WithMilk.new(coffee)
coffee.print

coffee = WithSprinkles.new(coffee)
coffee.print

```
 

 

Output:

 
```
Cost: 1.0; Ingredients: Coffee
Cost: 1.5; Ingredients: Coffee, Milk
Cost: 1.7; Ingredients: Coffee, Milk, Sprinkles

```
 

## See also

 
- [Composite pattern](./Composite_pattern)
- [Adapter pattern](./Adapter_pattern)
- [Abstract class](./Abstract_class)
- [Abstract factory](./Abstract_factory)
- [Aspect-oriented programming](./Aspect-oriented_programming)
- [Immutable object](./Immutable_object)

 

## References

  
1. [↑](./Decorator_pattern#cite_ref-1) Gamma, Erich; et al. (1995). [*Design Patterns*](https://archive.org/details/designpatternsel00gamm/page/175). Reading, MA: Addison-Wesley Publishing Co, Inc. pp. [175ff](https://archive.org/details/designpatternsel00gamm/page/175). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Decorator_pattern#cite_ref-2) ["How to Implement a Decorator Pattern"](https://web.archive.org/web/20150707165957/http://sam-burns.co.uk/57/how-to-implement-a-decorator-pattern/). Archived from the original on 2015-07-07.
3. [↑](./Decorator_pattern#cite_ref-3) ["The Decorator Pattern, Why We Stopped Using It, and the Alternative"](https://betterprogramming.pub/the-decorator-pattern-why-i-stopped-using-it-and-the-alternative-2ae447f9de08). 8 March 2022.
4. [↑](./Decorator_pattern#cite_ref-GoF_4-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/175). Addison Wesley. pp. [175ff](https://archive.org/details/designpatternsel00gamm/page/175). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
5. [1](./Decorator_pattern#cite_ref-:0_5-0) [2](./Decorator_pattern#cite_ref-:0_5-1) [3](./Decorator_pattern#cite_ref-:0_5-2) ["The Decorator design pattern - Problem, Solution, and Applicability"](https://web.archive.org/web/20230408204922/http://w3sdesign.com/?gr=s04&ugr=proble#gf). *w3sDesign*. Archived from [the original](http://w3sdesign.com/?gr=s04&ugr=proble) on 2023-04-08. Retrieved 2017-08-12.
6. [↑](./Decorator_pattern#cite_ref-6) Freeman, Eric; Freeman, Elisabeth; Sierra, Kathy; Bates, Bert (2004). Hendrickson, Mike; Loukides, Mike (eds.). *Head First Design Patterns* (paperback). Vol. 1. O'Reilly. pp. 243, 252, 258, 260. [ISBN](./ISBN_(identifier)) [978-0-596-00712-6](./Special:BookSources/978-0-596-00712-6).
7. [↑](./Decorator_pattern#cite_ref-7) ["The Decorator design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=s04&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.
8. [↑](./Decorator_pattern#cite_ref-8) ["DecoratorPattern - Python Wiki"](https://wiki.python.org/moin/DecoratorPattern). *wiki.python.org*.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Decorator implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Decorator)***  
- [Decorator Pattern](https://web.archive.org/web/20180418005440/http://designpattern.co.il/Decorator.html) implementation in Java
- [Decorator pattern description from the Portland Pattern Repository](https://wiki.c2.com/?DecoratorPattern)

 
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