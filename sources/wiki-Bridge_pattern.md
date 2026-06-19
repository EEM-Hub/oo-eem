---
source: https://en.wikipedia.org/wiki/Bridge_pattern
fetched: 2026-06-19
---

Design pattern used in software engineering 

The **bridge pattern** is a [design pattern](./Software_design_pattern) used in [software engineering](./Software_engineering) that is meant to *"decouple an [abstraction](./Abstraction_(computer_science)) from its [implementation](./Implementation) so that the two can vary independently"*, introduced by the [Gang of Four](./Design_Patterns).[[1]](./Bridge_pattern#cite_note-GoFp151-1) The *bridge* uses [encapsulation](./Encapsulation_(computer_science)), [aggregation](./Object_composition#Aggregation), and can use [inheritance](./Inheritance_(object-oriented_programming)) to separate responsibilities into different [classes](./Class_(computer_science)).

 

When a class varies often, the features of [object-oriented programming](./Object-oriented_programming) become very useful because changes to a [program](./Computer_program)'s [code](./Source_code) can be made easily with minimal prior knowledge about the program. The bridge pattern is useful when both the class and what it does vary often. The class itself can be thought of as the *abstraction* and what the class can do as the *implementation*. The bridge pattern can also be thought of as two layers of abstraction.

 

When there is only one fixed implementation, this pattern is known as the [Pimpl](./Pimpl) idiom in the [C++](./C++) world.

 

The bridge pattern is often confused with the [adapter pattern](./Adapter_pattern), and is often implemented using the [object adapter pattern](./Adapter_pattern#Object_adapter_pattern); e.g., in the Java code below.

 

Variant: The implementation can be decoupled even more by deferring the presence of the implementation to the point where the abstraction is utilized (as illustrated by the [[Visual Prolog]] example below).

 

## Overview

 

The Bridge design pattern is one of the twenty-three well-known *[GoF design patterns](./Design_Patterns)* that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.[[1]](./Bridge_pattern#cite_note-GoFp151-1)

 

What problems can the Bridge design pattern solve?[[2]](./Bridge_pattern#cite_note-2)

 
- An abstraction and its implementation should be defined and extended independently from each other.
- A compile-time binding between an abstraction and its implementation should be avoided so that an implementation can be selected at run-time.

 

When using subclassing, different subclasses implement an abstract class in different ways. But an implementation is bound to the abstraction at compile-time and cannot be changed at run-time.

 

What solution does the Bridge design pattern describe?

 
- Separate an abstraction (`Abstraction`) from its implementation (`Implementor`) by putting them in separate class hierarchies.
- Implement the `Abstraction` in terms of (by delegating to) an `Implementor` object.

 

This enables to configure an `Abstraction` with an `Implementor` object at run-time.

See also the [Unified Modeling Language](./Unified_Modeling_Language) class and sequence diagram below.

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/f/fd/W3sDesign_Bridge_Design_Pattern_UML.jpg)](./File:W3sDesign_Bridge_Design_Pattern_UML.jpg)A sample UML class and sequence diagram for the Bridge design pattern.[[3]](./Bridge_pattern#cite_note-3) 

In the above Unified Modeling Language [class diagram](./Class_diagram), an abstraction (`Abstraction`) is not implemented as usual in a single inheritance hierarchy.
Instead, there is one hierarchy for
an abstraction (`Abstraction`) and a separate hierarchy for its implementation (`Implementor`), which makes the two independent from each other.
The `Abstraction` interface (`operation()`) is implemented in terms of (by delegating to)
the `Implementor` interface (`imp.operationImp()`).

The [UML](./Unified_Modeling_Language) [sequence diagram](./Sequence_diagram)
shows the run-time interactions: The `Abstraction1` object delegates implementation to the `Implementor1` object (by calling `operationImp()` on `Implementor1`),
which performs the operation and returns to `Abstraction1`.

 

### Class diagram

 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Bridge_UML_class_diagram.svg/500px-Bridge_UML_class_diagram.svg.png)](./File:Bridge_UML_class_diagram.svg)

 Abstraction (abstract class) defines the abstract interface maintains the Implementor reference. RefinedAbstraction (normal class) extends the interface defined by Abstraction Implementor (interface) defines the interface for implementation classes ConcreteImplementor (normal class) implements the Implementor interface [![](//upload.wikimedia.org/wikipedia/commons/a/a8/Bridge_pattern_in_LePUS3.1.gif)](./File:Bridge_pattern_in_LePUS3.1.gif)Bridge in [LePUS3](./Lepus3?action=edit&redlink=1) ([legend](https://web.archive.org/web/20180314162121/http://www.lepus.org.uk/ref/legend/legend.xml))  

## Example

  Wikipedia is not a list of examples. Do not add examples from your favorite programming language here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language under the sun. Feel free to add examples here: http://en.wikibooks.org/wiki/Computer_Science/Design_Patterns/Bridge_pattern  

### C#

 

Bridge pattern compose objects in tree structure. It decouples abstraction from implementation. Here abstraction represents the client from which the objects will be called. An example implemented in C# is given below

 
```
namespace Wikipedia.Examples;

using System;

// Helps in providing truly decoupled architecture
interface IBridge
{
    void Function1();
    void Function2();
}

class Bridge1 : IBridge
{
    public void Function1()
    {
        Console.WriteLine("Bridge1.Function1");
    }

    public void Function2()
    {
        Console.WriteLine("Bridge1.Function2");
    }
}

class Bridge2 : IBridge
{
    public void Function1()
    {
        Console.WriteLine("Bridge2.Function1");
    }

    public void Function2()
    {
        Console.WriteLine("Bridge2.Function2");
    }
}

interface IAbstractBridge
{
    void CallMethod1();
    void CallMethod2();
}

class AbstractBridge : IAbstractBridge
{
    public IBridge bridge;

    public AbstractBridge(IBridge bridge)
    {
        this.bridge = bridge;
    }

    public void CallMethod1()
    {
        this.bridge.Function1();
    }

    public void CallMethod2()
    {
        this.bridge.Function2();
    }
}

```
 

The Bridge classes are the Implementation that uses the same interface-oriented architecture to create objects. On the other hand, the abstraction takes an instance of the implementation class and runs its method. Thus, they are completely decoupled from one another.

 

### Crystal

 
```
abstract class DrawingAPI
  abstract def draw_circle(x : Float64, y : Float64, radius : Float64)
end

class DrawingAPI1 < DrawingAPI
  def draw_circle(x : Float, y : Float, radius : Float)
    "API1.circle at #{x}:#{y} - radius: #{radius}"
  end
end

class DrawingAPI2 < DrawingAPI
  def draw_circle(x : Float64, y : Float64, radius : Float64)
    "API2.circle at #{x}:#{y} - radius: #{radius}"
  end
end

abstract class Shape
  protected getter drawing_api : DrawingAPI

  def initialize(@drawing_api)
  end

  abstract def draw
  abstract def resize_by_percentage(percent : Float64)
end

class CircleShape < Shape
  getter x : Float64
  getter y : Float64
  getter radius : Float64

  def initialize(@x, @y, @radius, drawing_api : DrawingAPI)
    super(drawing_api)
  end

  def draw
    @drawing_api.draw_circle(@x, @y, @radius)
  end

  def resize_by_percentage(percent : Float64)
    @radius *= (1 + percent/100)
  end
end

class BridgePattern
  def self.test
    shapes = [] of Shape
    shapes << CircleShape.new(1.0, 2.0, 3.0, DrawingAPI1.new)
    shapes << CircleShape.new(5.0, 7.0, 11.0, DrawingAPI2.new)

    shapes.each do |shape|
      shape.resize_by_percentage(2.5)
      puts shape.draw
    end
  end
end

BridgePattern.test

```
 

Output

 
```
API1.circle at 1.0:2.0 - radius: 3.075
API2.circle at 5.0:7.0 - radius: 11.275

```
 

### C++

 
```
import std;

using std::string;
using std::vector;

class DrawingAPI {
public:
    virtual ~DrawingAPI() = default;
    virtual string drawCircle(float x, float y, float radius) const = 0;
};

class DrawingAPI01: public DrawingAPI {
public:
    [[nodiscard]]
    string drawCircle(float x, float y, float radius) const override {
        return std::format("API01.circle at {}:{} - radius: {}", x, y, radius); 
    }
};

class DrawingAPI02: public DrawingAPI {
public:
    [[nodiscard]]
    string drawCircle(float x, float y, float radius) const override {
        return std::format("API02.circle at {}:{} - radius: {}", x, y, radius);
    }
};

class Shape {
protected:
    const DrawingAPI& drawingApi;
public:
    Shape(const DrawingAPI& api):
        drawingApi{api} {}

    virtual ~Shape() = default;

    virtual string draw() const = 0;
    virtual float resizeByPercentage(const float percent) noexcept = 0;
};

class CircleShape: public Shape {
private:
    float x;
    float y;
    float radius;
public:    
    CircleShape(const DrawingAPI& api, float x, float y, float radius): 
        Shape(api), x{x}, y{y}, radius{radius} {}

    [[nodiscard]]
    string draw() const override {
        return drawingApi.drawCircle(x, y, radius);
    }

    [[nodiscard]]
    float resizeByPercentage(float percent) noexcept override {
        return radius *= (1.0f + percent / 100.0f);
    }
};

int main(int argc, char* argv[]) {
    const DrawingAPI01 api1;
    const DrawingAPI02 api2;
    vector<CircleShape> shapes { 
        CircleShape{api1, 1.0f, 2.0f, 3.0f}, 
        CircleShape{api2, 5.0f, 7.0f, 11.0f} 
    }; 

    for (CircleShape& shape: shapes) {
        shape.resizeByPercentage(2.5);
        std::println("{}", shape.draw());
    }

    return 0;
}

```
 

Output:

 
```
API01.circle at 1.000000:2.000000 - radius: 3.075000
API02.circle at 5.000000:7.000000 - radius: 11.275000

```
 

Code requires a C++23 capable compiler, e.g. on Ubuntu 26.06 LTS with g++-15 the following 2-step build is required:

 
```
g++-15 -std=c++23 -c -fmodules -fmodule-only -fsearch-include-path bits/std.cc
g++-15 -std=c++23 -fmodules -o program program.cpp

```
 

### Java

 

The following [Java](./Java_(programming_language)) program defines a bank account that separates the account operations from the logging of these operations. 

 
```
package org.wikipedia.examples;

// Logger has two implementations: info and warning
@FunctionalInterface
interface Logger {
    void log(String message);
    
    static Logger info() {
        return message -> System.out.printf("info: %s%n", message);
    }
    static Logger warning() {
        return message -> System.out.printf("warning: %s%n", message);
    }
}

abstract class AbstractAccount {
    private Logger logger = Logger.info();
    
    public void setLogger(Logger logger) {
        this.logger = logger;
    }
    
    // the logging part is delegated to the Logger implementation
    protected void operate(String message, boolean result) {
        logger.log(String.format("%s result %s", message, result));
    }
}

class SimpleAccount extends AbstractAccount {
    private int balance;
    
    public SimpleAccount(int balance) {
        this.balance = balance;
    }
    
    public boolean isBalanceLow() {
        return balance < 50;
    }
    
    public void withdraw(int amount) {
        boolean shouldPerform = balance >= amount;
        if (shouldPerform) {
            balance -= amount;
        }
        operate(String.format("withdraw %s", amount, shouldPerform));
    }
}

public class BridgeDemo {
    public static void main(String[] args) {
        SimpleAccount account = new SimpleAccount(100);
        account.withdraw(75);
        
        if (account.isBalanceLow()) {
            // you can also change the Logger implementation at runtime
            account.setLogger(Logger.warning());
        }
        
        account.withdraw(10);
        account.withdraw(100);
    }
}

```
 

It will output:

 
```
info: withdraw 75 result true
warning: withdraw 10 result true
warning: withdraw 100 result false

```
 

### PHP

 
```
interface DrawingAPI
{
    function drawCircle($x, $y, $radius);
}

class DrawingAPI1 implements DrawingAPI
{
    public function drawCircle($x, $y, $radius)
    {
        echo "API1.circle at $x:$y radius $radius.\n";
    }
}

class DrawingAPI2 implements DrawingAPI
{
    public function drawCircle($x, $y, $radius)
    {
        echo "API2.circle at $x:$y radius $radius.\n";
    }
}

abstract class Shape
{
    protected $drawingAPI;

    public abstract function draw();
    public abstract function resizeByPercentage($pct);

    protected function __construct(DrawingAPI $drawingAPI)
    {
        $this->drawingAPI = $drawingAPI;
    }
}

class CircleShape extends Shape
{
    private $x;
    private $y;
    private $radius;

    public function __construct($x, $y, $radius, DrawingAPI $drawingAPI)
    {
        parent::__construct($drawingAPI);
        $this->x = $x;
        $this->y = $y;
        $this->radius = $radius;
    }

    public function draw()
    {
        $this->drawingAPI->drawCircle($this->x, $this->y, $this->radius);
    }

    public function resizeByPercentage($pct)
    {
        $this->radius *= $pct;
    }
}

class Tester
{
    public static function main()
    {
        $shapes = array(
            new CircleShape(1, 3, 7,  new DrawingAPI1()),
            new CircleShape(5, 7, 11, new DrawingAPI2()),
        );

        foreach ($shapes as $shape) {
            $shape->resizeByPercentage(2.5);
            $shape->draw();
        }
    }
}

Tester::main();

```
 

Output:

 
```
API1.circle at 1:3 radius 17.5
API2.circle at 5:7 radius 27.5
```
 

### Scala

 
```
trait DrawingAPI {
  def drawCircle(x: Double, y: Double, radius: Double)
}

class DrawingAPI1 extends DrawingAPI {
  def drawCircle(x: Double, y: Double, radius: Double) = println(s"API #1 $x $y $radius")
}

class DrawingAPI2 extends DrawingAPI {
  def drawCircle(x: Double, y: Double, radius: Double) = println(s"API #2 $x $y $radius")
}

abstract class Shape(drawingAPI: DrawingAPI) {
  def draw()
  def resizePercentage(pct: Double)
}

class CircleShape(x: Double, y: Double, var radius: Double, drawingAPI: DrawingAPI)
    extends Shape(drawingAPI: DrawingAPI) {

  def draw() = drawingAPI.drawCircle(x, y, radius)

  def resizePercentage(pct: Double) { radius *= pct }
}

object BridgePattern {
  def main(args: Array[String]) {
    Seq (
	new CircleShape(1, 3, 5, new DrawingAPI1),
	new CircleShape(4, 5, 6, new DrawingAPI2)
    ) foreach { x =>
        x.resizePercentage(3)
        x.draw()			
      }	
  }
}

```
 

### Python

 
```
"""
Bridge pattern example.
"""
from abc import ABCMeta, abstractmethod
from typing import NoReturn

NOT_IMPLEMENTED: str = "You should implement this."

class DrawingAPI:
    __metaclass__ = ABCMeta

    @abstractmethod
    def draw_circle(self, x: float, y: float, radius: float) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

class DrawingAPI1(DrawingAPI):
    def draw_circle(self, x: float, y: float, radius: float) -> str:
        return f"API1.circle at {x}:{y} - radius: {radius}"

class DrawingAPI2(DrawingAPI):
    def draw_circle(self, x: float, y: float, radius: float) -> str:
        return f"API2.circle at {x}:{y} - radius: {radius}"

class DrawingAPI3(DrawingAPI):
    def draw_circle(self, x: float, y: float, radius: float) -> str:
        return f"API3.circle at {x}:{y} - radius: {radius}"

class Shape:
    __metaclass__ = ABCMeta

    drawing_api: DrawingAPI = None
    def __init__(self, drawing_api: DrawingAPI) -> None:
        self.drawing_api = drawing_api

    @abstractmethod
    def draw(self) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

    @abstractmethod
    def resize_by_percentage(self, percent: float) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

class CircleShape(Shape):
    def __init__(self, x: float, y: float, radius: float, drawing_api: DrawingAPI):
        self.x = x
        self.y = y
        self.radius = radius
        super(CircleShape, self).__init__(drawing_api)

    def draw(self) -> str:
        return self.drawing_api.draw_circle(self.x, self.y, self.radius)

    def resize_by_percentage(self, percent: float) -> None:
        self.radius *= 1 + percent / 100

class BridgePattern:
    @staticmethod
    def test() -> None:
        shapes: list[CircleShape] = [
            CircleShape(1.0, 2.0, 3.0, DrawingAPI1()),
            CircleShape(5.0, 7.0, 11.0, DrawingAPI2()),
            CircleShape(5.0, 4.0, 12.0, DrawingAPI3()),
        ]

        for shape in shapes:
            shape.resize_by_percentage(2.5)
            print(shape.draw())

if __name__ == "__main__":
    BridgePattern.test()

```
 

## See also

 
- [Adapter pattern](./Adapter_pattern)
- [Strategy pattern](./Strategy_pattern)
- [Template method pattern](./Template_method_pattern)

 

## References

 
1. [1](./Bridge_pattern#cite_ref-GoFp151_1-0) [2](./Bridge_pattern#cite_ref-GoFp151_1-1) [Gamma, Erich](./Erich_Gamma); Helm, Richard; [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/). Addison-Wesley. p. [151](https://archive.org/details/designpatternsel00gamm/page/151). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Bridge_pattern#cite_ref-2) ["The Bridge design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=s02&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.
3. [↑](./Bridge_pattern#cite_ref-3) ["The Bridge design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=s02&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science/Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science/Design%20Patterns)* has a page on the topic of: ***[Bridge pattern implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science/Design%20Patterns/Bridge%20pattern)***  
- [Bridge in UML and in LePUS3](https://web.archive.org/web/20090426061003/http://www.lepus.org.uk/ref/companion/Bridge.xml) (a formal modelling language)
- [C# Design Patterns: The Bridge Pattern](http://www.informit.com/articles/article.aspx?p=30297) From: James W. Cooper (2003). [*C# Design Patterns: A Tutorial*](http://www.informit.com/store/product.aspx?isbn=0-201-84453-2). [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [0-201-84453-2](./Special:BookSources/0-201-84453-2).

 
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