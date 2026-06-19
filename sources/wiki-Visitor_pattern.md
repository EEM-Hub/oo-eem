---
source: https://en.wikipedia.org/wiki/Visitor_pattern
fetched: 2026-06-19
---

|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Visitor pattern"–news·newspapers·books·scholar·JSTOR(January 2022)(Learn how and when to remove this message) |
| --- | --- |

 Software design pattern 

A **visitor pattern** is a [software design pattern](./Software_design_pattern) that separates the [algorithm](./Algorithm) from the [object](./Object_(computer_science)) structure. Because of this separation, new operations can be added to existing object structures without modifying the structures. It is one way to follow the [open/closed principle](./Open/closed_principle) in [object-oriented programming](./Object-oriented_programming) and [software engineering](./Software_engineering). 

 

In essence, the visitor allows adding new [virtual functions](./Virtual_function) to a family of [classes](./Class_(programming)), without modifying the classes. Instead, a visitor class is created that implements all of the appropriate specializations of the virtual function. The visitor takes the instance reference as input, and implements the goal through [double dispatch](./Double_dispatch).

 

Programming languages with [sum types](./Tagged_union) and [pattern matching](./Pattern_matching) obviate many of the benefits of the visitor pattern, as the visitor class is able to both easily branch on the type of the object and generate a compiler error if a new object type is defined which the visitor does not yet handle.

 

## Overview

 

The Visitor[[1]](./Visitor_pattern#cite_note-GoF-1)
design pattern is one of the twenty-three *[Gang of Four design patterns](./Design_Patterns)*.

 

### Problems the pattern can solve

 
- It should be possible to define a new operation for (some) classes of an object structure without changing the classes.

 

When new operations are needed frequently and the object structure consists of many unrelated classes,
it's inflexible to add new subclasses each time a new operation is required
because "distributing all these operations across the various node classes leads to a system that's hard to understand, maintain, and change."[[1]](./Visitor_pattern#cite_note-GoF-1)

 

### Solution described by the pattern

 
- Define a separate (visitor) object that implements an operation to be performed on elements of an object structure.
- Clients traverse the object structure and call a *dispatching operation accept (visitor)* on an element — that "dispatches" (delegates) the request to the "accepted visitor object". The visitor object then performs the operation on the element ("visits the element").

 

This makes it possible to create new operations independently from the classes of an object structure
by adding new visitor objects.

 

See also the UML class and sequence diagram below.

 

## Definition

 

The [Gang of Four](./Design_Patterns) defines the Visitor as:

 

Represent[ing] an operation to be performed on elements of an object structure. Visitor lets you define a new operation without changing the classes of the elements on which it operates.

 

The nature of the Visitor makes it an ideal pattern to plug into public APIs, thus allowing its clients to perform operations on a class using a "visiting" class without having to modify the source.[[2]](./Visitor_pattern#cite_note-2)

 

## Advantages

 

Moving operations into visitor classes is beneficial when

 
- many unrelated operations on an object structure are required,
- the classes that make up the object structure are known and not expected to change,
- new operations need to be added frequently,
- an algorithm involves several classes of the object structure, but it is desired to manage it in one single location,
- an algorithm needs to work across several independent class hierarchies.

 

A drawback to this pattern, however, is that it makes extensions to the class hierarchy more difficult, as new classes typically require a new `visit` method to be added to each visitor.

 

## Application

 

Consider the design of a 2D [computer-aided design](./Computer-aided_design) (CAD) system. At its core, there are several types to represent basic geometric shapes like circles, lines, and arcs. The entities are ordered into layers, and at the top of the type hierarchy is the drawing, which is simply a list of layers, plus some added properties.

 

A fundamental operation on this type hierarchy is saving a drawing to the system's native file format. At first glance, it may seem desirable to add local save methods to all types in the hierarchy. But it can also be useful to save drawings to other file formats. Adding ever more methods for saving into many different file formats can complicate the original geometric data structure.

 

A naive way to solve this would be to maintain separate functions for each file format. Such a save function would take a drawing as input, traverse it, and encode into that specific file format. As this is done for each added different format, duplication between the functions accumulates. For example, saving a circle shape in a raster format requires very similar code no matter what specific raster form is used, and is different from other primitive shapes. The case for other primitive shapes like lines and polygons is similar. Thus, the code becomes a large outer loop traversing through the objects, with a large decision tree inside the loop querying the type of the object. Another problem with this approach is that it is very easy to miss a shape in one or more savers, or a new primitive shape is introduced, but the save routine is implemented only for one file type and not others, leading to code extension and maintenance problems. As the versions of the same file grows it becomes more complicated to maintain it.

 

Instead, the visitor pattern can be applied. It encodes the logical operation (i.e. save(image_tree)) on the whole hierarchy into one class (i.e. Saver) that implements the common methods for traversing the tree and describes virtual helper methods (i.e. save_circle, save_square, etc.) to be implemented for format specific behaviors. In the case of the CAD example, such format specific behaviors would be implemented by a subclass of Visitor (i.e. SaverPNG). As such, all duplication of type checks and traversal steps is removed. Additionally, the compiler now complains if a shape is omitted since it is now expected by the common base traversal/save function.

 

### Iteration loops

 See also: [Iterator pattern](./Iterator_pattern) 

The visitor pattern may be used for iteration over [container](./Container_(abstract_data_type))-like data structures just like [Iterator pattern](./Iterator_pattern) but with limited functionality.[[3]](./Visitor_pattern#cite_note-Budd1997-3): 288  For example, [iteration](./Iteration) over a directory structure could be implemented by a function class <&#x2D; this is not a mistake, it means class Function {...}  instead of more conventional [loop pattern](./Loop_(programming)). This would allow deriving various useful information from directories content by implementing a visitor functionality for every item while [reusing](./Code_reuse) the iteration code. It's widely employed in Smalltalk systems and can be found in C++ as well.[[3]](./Visitor_pattern#cite_note-Budd1997-3): 289  A drawback of this approach, however, is that you can't break out of the loop easily or iterate concurrently (in parallel i.e. traversing two containers at the same time by a single `i` variable).[[3]](./Visitor_pattern#cite_note-Budd1997-3): 289  The latter would require writing additional functionality for a visitor to support these features.[[3]](./Visitor_pattern#cite_note-Budd1997-3): 289 

 

## Structure

 

### UML class and sequence diagram

 [![](//upload.wikimedia.org/wikipedia/commons/0/00/W3sDesign_Visitor_Design_Pattern_UML.jpg)](./File:W3sDesign_Visitor_Design_Pattern_UML.jpg)A sample [UML](./Unified_Modeling_Language) class diagram and [sequence diagram](./Sequence_diagram) for the Visitor design pattern.[[4]](./Visitor_pattern#cite_note-4) 

In the [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram) above, the `ElementA` class doesn't implement a new operation directly.
Instead, `ElementA` implements a *dispatching operation* `accept(visitor)` that "dispatches" (delegates) a request to the "accepted visitor object" (`visitor.visitElementA(this)`). The `Visitor1` class implements the operation (`visitElementA(e:ElementA)`).

 `ElementB` then implements `accept(visitor)` by dispatching to `visitor.visitElementB(this)`. The `Visitor1` class implements the operation (`visitElementB(e:ElementB)`).

 

The [UML](./Unified_Modeling_Language) [sequence diagram](./Sequence_diagram)
shows the run-time interactions: The `Client` object traverses the elements of an object structure (`ElementA,ElementB`) and calls `accept(visitor)` on each element.

First, the `Client` calls `accept(visitor)` on
`ElementA`, which calls `visitElementA(this)` on the accepted `visitor` object.
The element itself (`this`) is passed to the `visitor` so that 
it can "visit" `ElementA` (call `operationA()`).

Thereafter, the `Client` calls `accept(visitor)` on
`ElementB`, which calls `visitElementB(this)` on the `visitor` that "visits" `ElementB` (calls `operationB()`).

 

### Class diagram

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/eb/Visitor_design_pattern.svg/500px-Visitor_design_pattern.svg.png)](./File:Visitor_design_pattern.svg)Visitor in [Unified Modeling Language](./Unified_Modeling_Language) (UML).[[5]](./Visitor_pattern#cite_note-5): 381  [![](//upload.wikimedia.org/wikipedia/commons/d/d8/Visitor_pattern_class_diagram_in_LePUS3.gif)](./File:Visitor_pattern_class_diagram_in_LePUS3.gif)Visitor in [LePUS3](./Lepus3?action=edit&redlink=1) ([legend](http://lepus.org.uk/ref/legend/legend.xml)) 

## Details

 

The visitor pattern requires a [programming language](./Programming_language) that supports [single dispatch](./Single_dispatch), as common object-oriented languages (such as [C++](./C++), [Java](./Java_(programming_language)), [Smalltalk](./Smalltalk), [Objective-C](./Objective-C), [Swift](./Swift_(programming_language)), [JavaScript](./JavaScript), [Python](./Python_(programming_language)) and [C#](./C_Sharp_(programming_language))) do. Under this condition, consider two objects, each of some class type; one is termed the *element*, and the other is *visitor*.

 

### Objects

 

#### Visitor

 

The *visitor* declares a `visit` method, which takes the element as an argument, for each class of element. *Concrete visitors* are derived from the visitor class and implement these `visit` methods, each of which implements part of the algorithm operating on the object structure. The state of the algorithm is maintained locally by the concrete visitor class.

 

#### Element

 

The *element* declares an `accept` method to accept a visitor, taking the visitor as an argument. *Concrete elements*, derived from the element class, implement the `accept` method. In its simplest form, this is no more than a call to the visitor's `visit` method. [Composite](./Composite_pattern) elements, which maintain a list of child objects, typically iterate over these, calling each child's `accept` method.

 

#### Client

 

The *client* creates the object structure, directly or indirectly, and instantiates the concrete visitors. When an operation is to be performed which is implemented using the Visitor pattern, it calls the `accept` method of the top-level element(s).

 

### Methods

 

#### Accept

 

When the `accept` method is called in the program, its implementation is chosen based on both the dynamic type of the element and the static type of the visitor. When the associated `visit` method is called, its implementation is chosen based on both the dynamic type of the visitor and the static type of the element, as known from within the implementation of the `accept` method, which is the same as the dynamic type of the element. (As a bonus, if the visitor can't handle an argument of the given element's type, then the compiler will catch the error.)

 

#### Visit

 

Thus, the implementation of the `visit` method is chosen based on both the dynamic type of the element and the dynamic type of the visitor. This effectively implements [double dispatch](./Double_dispatch). For languages whose object systems support multiple dispatch, not only single dispatch, such as [Common Lisp](./Common_Lisp) or [C#](./C_Sharp_(programming_language)) via the [Dynamic Language Runtime](./Dynamic_Language_Runtime) (DLR), implementation of the visitor pattern is greatly simplified (a.k.a. Dynamic Visitor) by allowing use of simple function overloading to cover all the cases being visited. A dynamic visitor, provided it operates on public data only, conforms to the [open/closed principle](./Open/closed_principle) (since it does not modify extant structures) and to the [single responsibility principle](./Single_responsibility_principle) (since it implements the Visitor pattern in a separate component).

 

In this way, one algorithm can be written to traverse a graph of elements, and many different kinds of operations can be performed during that traversal by supplying different kinds of visitors to interact with the elements based on the dynamic types of both the elements and the visitors.

 

## Examples

 

### C#

 

This example declares a separate `ExpressionPrintingVisitor` class that takes care of the printing. If the introduction of a new concrete visitor is desired, a new class will be created to implement the Visitor interface, and new implementations for the Visit methods will be provided. The existing classes (Literal and Addition) will remain unchanged.

 
```
namespace Wikipedia.Examples;

using System;

interface IVisitor
{
    void Visit(Literal literal);  
    void Visit(Addition addition);
}

class ExpressionPrintingVisitor : IVisitor
{
    public void Visit(Literal literal)
    {
        Console.WriteLine(literal.Value);
    }

    public void Visit(Addition addition)
    {
        double leftValue = addition.Left.GetValue();
        double rightValue = addition.Right.GetValue();
        double sum = addition.GetValue();
        Console.WriteLine($"{leftValue} + {rightValue} = {sum}");
    }
 }

abstract class Expression
{
    public abstract void Accept(IVisitor visitor);
   
    public abstract double GetValue();
}

class Literal : Expression
{
    public Literal(double value)
    {
        this.Value = value;
    }

    public double Value { get; set; }

    public override void Accept(IVisitor visitor)
    {
        visitor.Visit(this);
    }
 
    public override double GetValue()
    {
        return Value;
    }
}

class Addition : Expression
{
    public Addition(Expression left, Expression right)
    {
        Left = left;
        Right = right;
    }

    public Expression Left { get; set; }
    public Expression Right { get; set; }

    public override void Accept(IVisitor visitor)
    {
        Left.Accept(visitor);
        Right.Accept(visitor);
        visitor.Visit(this);
    }
  
    public override double GetValue()
    {
        return Left.GetValue() + Right.GetValue();
    }
}

public static class Program
{
    public static void Main(string[] args)
    {
        // Emulate 1 + 2 + 3
        Addition e = new(
            new Addition(
                new Literal(1),
                new Literal(2)
            ),
            new Literal(3)
        );

        ExpressionPrintingVisitor printingVisitor = new();
        e.Accept(printingVisitor);
        Console.ReadKey();
    }
}

```
 

### Smalltalk

  There must be an Smalltalk example because it was Dan Ingalls who first described double dispatch in Smalltalk:

Daniel H. H. Ingalls. A Simple Technique for Handling Multiple Polymorphism. In Proceedings of OOPSLA '86, Object–Oriented Programming Systems, Languages and Applications, pages 347–349, November 1986. Printed as SIGPLAN Notices, 21(11).
 

In this case, it is the object's responsibility to know how to print itself on a stream. The visitor here is then the object, not the stream.

 
```
"There's no syntax for creating a class. Classes are created by sending messages to other classes."
WriteStream subclass: #ExpressionPrinter
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'Wikipedia'.

ExpressionPrinter>>write: anObject
    "Delegates the action to the object. The object doesn't need to be of any special
    class; it only needs to be able to understand the message #putOn:"
    anObject putOn: self.
    ^ anObject.

Object subclass: #Expression
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'Wikipedia'.

Expression subclass: #Literal
    instanceVariableNames: 'value'
    classVariableNames: ''
    package: 'Wikipedia'.

Literal class>>with: aValue
    "Class method for building an instance of the Literal class"
    ^ self new
        value: aValue;
        yourself.

Literal>>value: aValue
  "Setter for value"
  value := aValue.

Literal>>putOn: aStream
    "A Literal object knows how to print itself"
    aStream nextPutAll: value asString.

Expression subclass: #Addition
    instanceVariableNames: 'left right'
    classVariableNames: ''
    package: 'Wikipedia'.

Addition class>>left: a right: b
    "Class method for building an instance of the Addition class"
    ^ self new
        left: a;
        right: b;
        yourself.

Addition>>left: anExpression
    "Setter for left"
    left := anExpression.

Addition>>right: anExpression
    "Setter for right"
    right := anExpression.

Addition>>putOn: aStream
    "An Addition object knows how to print itself"
    aStream nextPut: $(.
    left putOn: aStream.
    aStream nextPut: $+.
    right putOn: aStream.
    aStream nextPut: $).

Object subclass: #Program
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'Wikipedia'.

Program>>main
    | expression stream |
    expression := Addition
                    left: (Addition
                            left: (Literal with: 1)
                            right: (Literal with: 2))
                    right: (Literal with: 3).
    stream := ExpressionPrinter on: (String new: 100).
    stream write: expression.
    Transcript show: stream contents.
    Transcript flush.

```
 

  This article exists to explain a design pattern, not to show how it interacts with the subtleties of many languages. Wikipedia is not a list of examples, but there must be a C++ one. Add no examples from other programming languages here. Instead, add them to: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Visitor  

 

### Go

 

Go does not support method overloading, so the visit methods need different names. A typical visitor interface might be

 
```
type Visitor interface {
	visitWheel(wheel Wheel) string
	visitEngine(engine Engine) string
	visitBody(body Body) string
	visitCar(car Car) string
}

```
 

### Java

  This article exists to explain a design pattern, not to show how it interacts with the subtleties of many languages. Wikipedia is not a list of examples. Add no examples from other programming languages here. Instead, add them to: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Visitor  

The following example is in the language [Java](./Java_(programming_language)), and shows how the contents of a tree of nodes (in this case describing the components of a car) can be printed. Instead of creating `print` methods for each node subclass (`Wheel`, `Engine`, `Body`, and `Car`), one visitor class (`CarElementPrintVisitor`) performs the required printing action. Because different node subclasses require slightly different actions to print properly, `CarElementPrintVisitor` dispatches actions based on the class of the argument passed to its `visit` method. `CarElementDoVisitor`, which is analogous to a save operation for a different file format, does likewise.

 

#### Diagram

 

[![UML diagram of the Visitor pattern example with Car Elements](//upload.wikimedia.org/wikipedia/commons/d/d9/UML_diagram_of_an_example_of_the_Visitor_design_pattern.png)](./File:UML_diagram_of_an_example_of_the_Visitor_design_pattern.png)

 

#### Sources

 
```
package org.wikipedia.examples;

import java.util.List;

interface CarElement {
    void accept(CarElementVisitor visitor);
}

interface CarElementVisitor {
    void visit(Body body);
    void visit(Car car);
    void visit(Engine engine);
    void visit(Wheel wheel);
}

class Wheel implements CarElement {
    private final String name;

    public Wheel(final String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    @Override
    public void accept(CarElementVisitor visitor) {
        /*
         * accept(CarElementVisitor) in Wheel implements
         * accept(CarElementVisitor) in CarElement, so the call
         * to accept is bound at run time. This can be considered
         * the *first* dispatch. However, the decision to call
         * visit(Wheel) (as opposed to visit(Engine) etc.) can be
         * made during compile time since 'this' is known at compile
         * time to be a Wheel. Moreover, each implementation of
         * CarElementVisitor implements the visit(Wheel), which is
         * another decision that is made at run time. This can be
         * considered the *second* dispatch.
         */
        visitor.visit(this);
    }
}

class Body implements CarElement {
    @Override
    public void accept(CarElementVisitor visitor) {
        visitor.visit(this);
    }
}

class Engine implements CarElement {
    @Override
    public void accept(CarElementVisitor visitor) {
        visitor.visit(this);
    }
}

class Car implements CarElement {
    private final List<CarElement> elements;

    public Car() {
        this.elements = List.of(
            new Wheel("front left"), 
            new Wheel("front right"),
            new Wheel("back left"), 
            new Wheel("back right"),
            new Body(), 
            new Engine()
        );
    }

    @Override
    public void accept(CarElementVisitor visitor) {
        for (CarElement element : elements) {
            element.accept(visitor);
        }
        visitor.visit(this);
    }
}

class CarElementDoVisitor implements CarElementVisitor {
    @Override
    public void visit(Body body) {
        System.out.println("Moving my body");
    }

    @Override
    public void visit(Car car) {
        System.out.println("Starting my car");
    }

    @Override
    public void visit(Wheel wheel) {
        System.out.printf("Kicking my %s wheel%n", wheel.getName());
    }

    @Override
    public void visit(Engine engine) {
        System.out.println("Starting my engine");
    }
}

class CarElementPrintVisitor implements CarElementVisitor {
    @Override
    public void visit(Body body) {
        System.out.println("Visiting body");
    }

    @Override
    public void visit(Car car) {
        System.out.println("Visiting car");
    }

    @Override
    public void visit(Engine engine) {
        System.out.println("Visiting engine");
    }

    @Override
    public void visit(Wheel wheel) {
        System.out.printf("Visiting %s wheel%n", wheel.getName());
    }
}

public class VisitorDemo {
    public static void main(String[] args) {
        Car car = new Car();

        car.accept(new CarElementPrintVisitor());
        car.accept(new CarElementDoVisitor());
    }
}

```
 

  This article exists to explain a design pattern, not to show how it interacts with the subtleties of many languages. Wikipedia is not a list of examples. Add no examples from other programming languages here. Instead, add them to: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Visitor  

 

#### Output

 
```
Visiting front left wheel
Visiting front right wheel
Visiting back left wheel
Visiting back right wheel
Visiting body
Visiting engine
Visiting car
Kicking my front left wheel
Kicking my front right wheel
Kicking my back left wheel
Kicking my back right wheel
Moving my body
Starting my engine
Starting my car

```
 

### Common Lisp

 

#### Sources

 
```
(defclass auto ()
  ((elements :initarg :elements)))

(defclass auto-part ()
  ((name :initarg :name :initform "<unnamed-car-part>")))

(defmethod print-object ((p auto-part) stream)
  (print-object (slot-value p 'name) stream))

(defclass wheel (auto-part) ())

(defclass body (auto-part) ())

(defclass engine (auto-part) ())

(defgeneric traverse (function object other-object))

(defmethod traverse (function (a auto) other-object)
  (with-slots (elements) a
    (dolist (e elements)
      (funcall function e other-object))))

;; do-something visitations

;; catch all
(defmethod do-something (object other-object)
  (format t "don't know how ~s and ~s should interact~%" object other-object))

;; visitation involving wheel and integer
(defmethod do-something ((object wheel) (other-object integer))
  (format t "kicking wheel ~s ~s times~%" object other-object))

;; visitation involving wheel and symbol
(defmethod do-something ((object wheel) (other-object symbol))
  (format t "kicking wheel ~s symbolically using symbol ~s~%" object other-object))

(defmethod do-something ((object engine) (other-object integer))
  (format t "starting engine ~s ~s times~%" object other-object))

(defmethod do-something ((object engine) (other-object symbol))
  (format t "starting engine ~s symbolically using symbol ~s~%" object other-object))

(let ((a (make-instance 'auto
                        :elements `(,(make-instance 'wheel :name "front-left-wheel")
                                    ,(make-instance 'wheel :name "front-right-wheel")
                                    ,(make-instance 'wheel :name "rear-left-wheel")
                                    ,(make-instance 'wheel :name "rear-right-wheel")
                                    ,(make-instance 'body :name "body")
                                    ,(make-instance 'engine :name "engine")))))
  ;; traverse to print elements
  ;; stream *standard-output* plays the role of other-object here
  (traverse #'print a *standard-output*)

  (terpri) ;; print newline

  ;; traverse with arbitrary context from other object
  (traverse #'do-something a 42)

  ;; traverse with arbitrary context from other object
  (traverse #'do-something a 'abc))

```
 

#### Output

 
```
"front-left-wheel"
"front-right-wheel"
"rear-left-wheel"
"rear-right-wheel"
"body"
"engine"
kicking wheel "front-left-wheel" 42 times
kicking wheel "front-right-wheel" 42 times
kicking wheel "rear-left-wheel" 42 times
kicking wheel "rear-right-wheel" 42 times
don't know how "body" and 42 should interact
starting engine "engine" 42 times
kicking wheel "front-left-wheel" symbolically using symbol ABC
kicking wheel "front-right-wheel" symbolically using symbol ABC
kicking wheel "rear-left-wheel" symbolically using symbol ABC
kicking wheel "rear-right-wheel" symbolically using symbol ABC
don't know how "body" and ABC should interact
starting engine "engine" symbolically using symbol ABC
```
 

#### Notes

 

The `other-object` parameter is superfluous in `traverse`. The reason is that it is possible to use an anonymous function that calls the desired target method with a lexically captured object:

 
```
(defmethod traverse (function (a auto)) ;; other-object removed
  (with-slots (elements) a
    (dolist (e elements)
      (funcall function e)))) ;; from here too

  ;; ...

  ;; alternative way to print-traverse
  (traverse (lambda (o) (print o *standard-output*)) a)

  ;; alternative way to do-something with
  ;; elements of a and integer 42
  (traverse (lambda (o) (do-something o 42)) a)

```
 

Now, the multiple dispatch occurs in the call issued from the body of the anonymous function, and so `traverse` is just a mapping function that distributes a function application over the elements of an object. Thus all traces of the Visitor Pattern disappear, except for the mapping function, in which there is no evidence of two objects being involved. All knowledge of there being two objects and a dispatch on their types is in the lambda function.

 

### Python

 

Python does not support method overloading in the classical sense (polymorphic behavior according to type of passed parameters), so the "visit" methods for the different model types need to have different names.

 

#### Sources

 
```
"""
Visitor pattern example.
"""

from abc import ABCMeta, abstractmethod
from typing import NoReturn

NOT_IMPLEMENTED: str = "You should implement this."

class CarElement(metaclass = ABCMeta):
    @abstractmethod
    def accept(self, visitor: CarElementVisitor) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

class Body(CarElement):
    def accept(self, visitor: CarElementVisitor) -> None:
        visitor.visit_body(self)

class Engine(CarElement):
    def accept(self, visitor: CarElementVisitor) -> None:
        visitor.visit_engine(self)

class Wheel(CarElement):
    def __init__(self, name: str) -> None:
        self.name = name

    def accept(self, visitor: CarElementVisitor) -> None:
        visitor.visit_wheel(self)

class Car(CarElement):
    def __init__(self) -> None:
        self.elements: list[CarElement] = [
            Wheel("front left"), 
            Wheel("front right"),
            Wheel("back left"), 
            Wheel("back right"),
            Body(), 
            Engine()
        ]

    def accept(self, visitor):
        for element in self.elements:
            element.accept(visitor)
        visitor.visit_car(self)

class CarElementVisitor(metaclass = ABCMeta):
    @abstractmethod
    def visit_body(self, element: CarElement) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

    @abstractmethod
    def visit_engine(self, element: CarElement) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

    @abstractmethod
    def visit_wheel(self, element: CarElement) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

    @abstractmethod
    def visit_car(self, element: CarElement) -> NoReturn:
        raise NotImplementedError(NOT_IMPLEMENTED)

class CarElementDoVisitor(CarElementVisitor):
    def visit_body(self, body: Body) -> None:
        print("Moving my body.")

    def visit_car(self, car: Car) -> None:
        print("Starting my car.")

    def visit_wheel(self, wheel: Wheel) -> None:
        print(f"Kicking my {wheel.name} wheel.")

    def visit_engine(self, engine: Engine) -> None:
        print("Starting my engine.")

class CarElementPrintVisitor(CarElementVisitor):
    def visit_body(self, body: Body) -> None:
        print("Visiting body.")

    def visit_car(self, car: Car) -> None:
        print("Visiting car.")

    def visit_wheel(self, wheel: Wheel) -> None:
        print(f"Visiting {wheel.name} wheel.")

    def visit_engine(self, engine: Engine) -> None:
        print("Visiting engine.")

if __name__ == "__main__":
    car: Car = Car()
    car.accept(CarElementPrintVisitor())
    car.accept(CarElementDoVisitor())

```
 

#### Output

 
```
Visiting front left wheel.
Visiting front right wheel.
Visiting back left wheel.
Visiting back right wheel.
Visiting body.
Visiting engine.
Visiting car.
Kicking my front left wheel.
Kicking my front right wheel.
Kicking my back left wheel.
Kicking my back right wheel.
Moving my body.
Starting my engine.
Starting my car.

```
 

#### Abstraction

 

Using Python 3 or above allows to make a general implementation of the accept method:

 
```
class Visitable:
    def accept(self, visitor: Visitor) -> Any:
        lookup: str = f"visit_{self.__qualname__.replace(".", "_")}"
        return getattr(visitor, lookup)(self)

```
 

One could extend this to iterate over the class's method resolution order if they would like to fall back on already-implemented classes. They could also use the subclass hook feature to define the lookup in advance.

 

## Related design patterns

 
- [Iterator pattern](./Iterator_pattern) – defines a traversal principle like the visitor pattern, without making a type differentiation within the traversed objects
- [Church encoding](./Church_encoding) – a related concept from functional programming, in which [tagged union/sum types](./Tagged_union) may be modeled using the behaviors of "visitors" on such types, and which enables the visitor pattern to emulate variants and [patterns](./Pattern_matching).

 

## See also

 
- [Algebraic data type](./Algebraic_data_type)
- [Double dispatch](./Double_dispatch)
- [Multiple dispatch](./Multiple_dispatch)
- [Function object](./Function_object)

 

## References

  
1. [1](./Visitor_pattern#cite_ref-GoF_1-0) [2](./Visitor_pattern#cite_ref-GoF_1-1) [Gamma, Erich](./Erich_Gamma); [Helm, Richard](./Richard_Helm); [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/331). Addison Wesley. pp. [331ff](https://archive.org/details/designpatternsel00gamm/page/331). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Visitor_pattern#cite_ref-2) Coogan, Corey (June 16, 2009). ["Visitor Pattern: A Real World Example"](https://coreycoogan.wordpress.com/2009/06/16/visitor-pattern-real-world-example) – via [WordPress.com](./WordPress.com).
3. [1](./Visitor_pattern#cite_ref-Budd1997_3-0) [2](./Visitor_pattern#cite_ref-Budd1997_3-1) [3](./Visitor_pattern#cite_ref-Budd1997_3-2) [4](./Visitor_pattern#cite_ref-Budd1997_3-3) Budd, Timothy (1997). *An introduction to object-oriented programming* (2nd ed.). Reading, Mass.: Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-82419-1](./Special:BookSources/0-201-82419-1). [OCLC](./OCLC_(identifier)) [34788238](https://search.worldcat.org/oclc/34788238).
4. [↑](./Visitor_pattern#cite_ref-4) ["The Visitor design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=b11&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.`{{cite web}}`:  CS1 maint: url-status ([link](./Category:CS1_maint:_url-status))
5. [↑](./Visitor_pattern#cite_ref-5) Reddy, Martin (2011). *API design for C++*. Boston: Morgan Kaufmann. [ISBN](./ISBN_(identifier)) [978-0-12-385004-1](./Special:BookSources/978-0-12-385004-1). [OCLC](./OCLC_(identifier)) [704559821](https://search.worldcat.org/oclc/704559821).

 

## External links

   [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Visitor pattern](https://commons.wikimedia.org/wiki/Category:Visitor%20pattern).    [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Visitor implementations in various languages](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Visitor)***  
- [The Visitor Family of Design Patterns](https://web.archive.org/web/20151022084246/http://objectmentor.com/resources/articles/visitor.pdf) at the [Wayback Machine](./Wayback_Machine) (archived October 22, 2015). Additional archives: [April 12, 2004](https://www.webcitation.org/66gH7HEVV?url=http://objectmentor.com/resources/articles/visitor.pdf), [March 5, 2002](https://drive.google.com/file/d/0BwhCYaYDn8EgNWIwZDg2YjUtNDRhNi00NzQ2LWFmNmMtYmYxNGI5ZjEwZDZj/view). A rough chapter from *The Principles, Patterns, and Practices of Agile Software Development*, [Robert C. Martin](./Robert_Cecil_Martin), Prentice Hall
- [Visitor pattern in UML and in LePUS3](http://www.lepus.org.uk/ref/companion/Visitor.xml) (a Design Description Language)
- Article "[Componentization: the Visitor Example](http://se.ethz.ch/~meyer/publications/computer/visitor.pdf) by [Bertrand Meyer](./Bertrand_Meyer) and Karine Arnout, *Computer* (IEEE), vol. 39, no. 7, July 2006, pages 23-30.
- Article [A Type-theoretic Reconstruction of the Visitor Pattern](http://www.cs.bham.ac.uk/~hxt/research/mfps-visitors.pdf)
- Article "[The Essence of the Visitor Pattern](http://web.cs.ucla.edu/~palsberg/paper/compsac98.pdf)" by [Jens Palsberg](./Jens_Palsberg?action=edit&redlink=1) and [C. Barry Jay](./C._Barry_Jay?action=edit&redlink=1). 1997 [IEEE-CS](./IEEE_Computer_Society) [COMPSAC](./Software_engineering) paper showing that accept() methods are unnecessary when reflection is available; introduces term 'Walkabout' for the technique.
- Article "[A Time for Reflection](https://web.archive.org/web/20030408205824/http://www.polyglotinc.com/reflection.html)" by Bruce Wallace – subtitled *"Java 1.2's reflection capabilities eliminate burdensome accept() methods from your Visitor pattern"*
- [Visitor Pattern](http://www.oodesign.com/oo_design_patterns/behavioral_patterns/visitor_pattern.html) using reflection(java).
- [PerfectJPattern Open Source Project](https://perfectjpattern.sourceforge.net/dp-visitor.html), Provides a context-free and type-safe implementation of the Visitor Pattern in Java based on Delegates.
- [Visitor Design Pattern](http://sourcemaking.com/design_patterns/visitor)

 
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

    Hidden categories below