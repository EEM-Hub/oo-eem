---
source: https://en.wikipedia.org/wiki/Mixin
fetched: 2026-06-19
---

Class in object-oriented programming languages This article is about the programming concept. For the ice cream, see [Mix-in](./Mix-in). For the company, see [Mixin Network](./Mixin_Network). 

In [object-oriented programming languages](./Object-oriented_programming_language), a **mixin** (or **mix-in**)[[1]](./Mixin#cite_note-:0-1)[[2]](./Mixin#cite_note-:1-2)[[3]](./Mixin#cite_note-:2-3)[[4]](./Mixin#cite_note-:3-4) is a [class](./Class_(computer_science)) that contains methods for use by other classes without having to be the parent class of those other classes. How those other classes gain access to the mixin's methods depends on the language. Mixins are sometimes described as being "included" rather than "inherited".

 

Mixins encourage [code reuse](./Code_reuse) and can be used to avoid the inheritance ambiguity that multiple inheritance can cause[[5]](./Mixin#cite_note-5) (the "[diamond problem](./Multiple_inheritance#The_diamond_problem)"), or to work around lack of support for multiple inheritance in a language.  A mixin can also be viewed as an [interface](./Interface_(object-oriented_programming)) with implemented [methods](./Method_(computer_science)). This pattern is an example of enforcing the [dependency inversion principle](./Dependency_inversion_principle).

 

## History

 

Mixins first appeared in [Symbolics](./Symbolics)'s object-oriented [Flavors](./Flavors_(computer_science)) system (developed by Howard Cannon), which was an approach to object-orientation used in [Lisp Machine Lisp](./Lisp_Machine_Lisp). The name was inspired by [Steve's Ice Cream Parlor](./Steve's_Ice_Cream) in Somerville, Massachusetts:[[1]](./Mixin#cite_note-:0-1) The owner of the ice cream shop offered a basic flavor of ice cream (vanilla, chocolate, etc.) and blended in a combination of extra items (nuts, cookies, fudge, etc.) and called the item a "[mix-in](./Mix-in)", his own trademarked term at the time.[[2]](./Mixin#cite_note-:1-2)

 

## Definition

 

Mixins are a language concept that allows a programmer to inject some code into a [class](./Class_(computer_programming)). Mixin programming is a style of [software development](./Software_development), in which units of functionality are created in a class and then mixed in with other classes.[[6]](./Mixin#cite_note-6)

 

A mixin class acts as the parent class, containing the desired functionality. A [subclass](./Subclass_(computer_science)) can then inherit or simply reuse this functionality, but not as a means of specialization. Typically, the mixin will export the desired functionality to a [child class](./Subclass_(computer_science)), without creating a rigid, single "is a" relationship. Here lies the important difference between the concepts of mixins and [inheritance](./Inheritance_(object-oriented_programming)), in that the child class can still inherit all the features of the parent class, but, the semantics about the child "being a kind of" the parent need not be necessarily applied.

 

## Advantages

 
1. It provides a mechanism for [multiple inheritance](./Multiple_inheritance) by allowing one class to use common functionality from multiple classes, but without the complex semantics of multiple inheritance.[[7]](./Mixin#cite_note-7)
2. [Code reusability](./Code_reuse): Mixins are useful when a programmer wants to share functionality between different classes. Instead of repeating the same code over and over again, the common functionality can simply be grouped into a mixin and then included into each class that requires it.[[8]](./Mixin#cite_note-8)
3. Mixins allow inheritance and use of only the desired features from the parent class, not necessarily all of the features from the parent class.[[9]](./Mixin#cite_note-9)

 

## Implementations

 

In [Simula](./Simula), classes are defined in a block in which attributes, methods and class initialization are all defined together; thus all the methods that can be invoked on a class are defined together, and the definition of the class is complete.

 

In [Flavors](./Flavors_(programming_language)), a mixin is a class from which another class can inherit slot definitions and methods. The mixin usually does not have direct instances. Since a Flavor can inherit from more than one other Flavor, it can inherit from one or more mixins. Note that the original Flavors did not use generic functions.

 

In New Flavors (a successor of Flavors) and [CLOS](./CLOS), methods are organized in "[generic functions](./Generic_function)". These generic functions are functions that are defined in multiple cases (methods) by class dispatch and method combinations.

 

CLOS and Flavors allow mixin methods to add behavior to existing methods: `:before` and `:after` daemons, whoppers and wrappers in Flavors. CLOS added `:around` methods and the ability to call shadowed methods via `CALL-NEXT-METHOD`. So, for example, a stream-lock-mixin can add locking around existing methods of a stream class. In Flavors one would write a wrapper or a whopper and in CLOS one would use an `:around` method. Both CLOS and Flavors allow the computed reuse via method combinations. `:before`, `:after` and `:around` methods are a feature of the standard method combination. Other method combinations are provided.

 

An example is the `+` method combination, where the resulting values of each of the applicable methods of a generic function are arithmetically added to compute the return value. This is used, for example, with the border-mixin for graphical objects. A graphical object may have a generic width function. The border-mixin would add a border around an object and has a method computing its width. A new class `bordered-button` (that is both a graphical object and uses the `border` mixin) would compute its width by calling all applicable width methods—via the `+` method combination. All return values are added and create the combined width of the object.

 

In an OOPSLA 90 paper,[[10]](./Mixin#cite_note-10) Gilad Bracha and William Cook reinterpret different inheritance mechanisms found in Smalltalk, Beta and CLOS as special forms of a mixin inheritance.

 

## Programming languages that use mixins

 

Other than Flavors and CLOS (a part of [Common Lisp](./Common_Lisp)), some languages that use mixins are:

 
- [Ada](./Ada_(programming_language)) (by extending an existing tagged record with arbitrary operations in a generic)
- [C++](./C++) (using abstract classes with [CRTP](./Curiously_recurring_template_pattern))
- [C#](./C_Sharp_(programming_language)) (since C# 8.0, by means of *default methods* of interfaces)[[11]](./Mixin#cite_note-11)
- [Cobra](./Cobra_(programming_language))
- [ColdFusion](./Adobe_ColdFusion) (Class based using includes and Object based by assigning methods from one object to another at runtime)
- [Curl](./Curl_(programming_language)) (with Curl RTE)
- [D](./D_(programming_language)) (called ["template mixins"](https://www.digitalmars.com/d/template-mixin.html); D also includes a ["mixin"](https://dlang.org/mixin.html) statement that compiles strings as code.)
- [Dart](./Dart_(programming_language))
- [Eiffel](./Eiffel_(programming_language)) (called "non-conforming inheritance"; uses normal classes inherited using the "inherit {NONE}" keyword)[[12]](./Mixin#cite_note-12)
- [Factor](./Factor_programming_language)[[13]](./Mixin#cite_note-13)
- [Groovy](./Groovy_(programming_language))
- [Go](./Go_(programming_language)) (by struct embedding)
- [Java](./Java_(programming_language)) (since Java 8, by means of *default methods* of interfaces)
- [JavaScript Delegation - Functions as Roles (Traits and Mixins)](./JavaScript#Delegative)
- [Kotlin](./Kotlin)
- [Less](./Less_(stylesheet_language))
- [Magik](./Magik_(programming_language))
- [MATLAB](./MATLAB)[[14]](./Mixin#cite_note-14)
- [OCaml](./OCaml)[[15]](./Mixin#cite_note-15)
- [ooRexx](./Object_REXX)
- [Perl](./Perl) (through [roles](./Moose_(Perl)#Roles) in the Moose extension of the Perl 5 object system)
- [PHP](./PHP)'s "[traits](./Trait_(computer_programming))"
- [Python](./Python_(programming_language))
- [Racket](./Racket_(programming_language)) ([mixins documentation](https://docs.racket-lang.org/guide/classes.html#(part._.Mixins)))
- [Raku](./Raku_(programming_language))
- [Ruby](./Ruby_(programming_language))
- [Rust](./Rust_(programming_language))
- [Sass](./Sass_(stylesheet_language))
- [Scala](./Scala_(programming_language))[[16]](./Mixin#cite_note-16)
- [Smalltalk](./Smalltalk)
- [Swift](./Swift_(programming_language))
- [SystemVerilog](./SystemVerilog)
- [XOTcl](./XOTcl)/[TclOO](http://wiki.tcl.tk/18152) (object systems builtin to [Tcl](./Tcl_(programming_language)))[[17]](./Mixin#cite_note-17)
- [TypeScript](./TypeScript) ([mixins documentation](https://www.typescriptlang.org/docs/handbook/mixins.html))
- [Vala](./Vala_(programming_language))

 

Some languages do not support mixins on the language level, but can easily mimic them by copying methods from one object to another at runtime, thereby "borrowing" the mixin's methods. This is also possible with [statically typed](./Static_typing) languages, but it requires constructing a new object with the extended set of methods.

 

Other languages that do not support mixins can support them in a round-about way via other language constructs. For example, [Visual Basic .NET](./Visual_Basic_.NET) and C# support the addition of extension methods on interfaces, meaning any class implementing an interface with extension methods defined will have the extension methods available as pseudo-members.

 

## Examples

 

### Common Lisp

 

[Common Lisp](./Common_Lisp) provides mixins in CLOS (Common Lisp Object System) similar to Flavors.

 

`object-width` is a generic function with one argument that uses the `+` method combination. This combination determines that all applicable methods for a generic function will be called and the results will be added.

 
```
(defgeneric object-width (object)
  (:method-combination +))

```
 

`button` is a class with one slot for the button text.

 
```
(defclass button ()
  ((text :initform "click me")))

```
 

There is a method for objects of class button that computes the width based on the length of the button text. `+` is the method qualifier for the method combination of the same name.

 
```
(defmethod object-width + ((object button))
   (* 10 (length (slot-value object 'text))))

```
 

A `border-mixin` class. The naming is just a convention. There are no superclasses, and no slots.

 
```
(defclass border-mixin () ())

```
 

There is a method computing the width of the border. Here it is just 4.

 
```
(defmethod object-width + ((object border-mixin))
  4)

```
 

`bordered-button` is a class inheriting from both `border-mixin` and `button`.

 
```
(defclass bordered-button (border-mixin button) ())

```
 

We can now compute the width of a button. Calling `object-width` computes 80. The result is the result of the single applicable method: the method `object-width` for the class `button`.

 
```
? (object-width (make-instance 'button))
80

```
 

We can also compute the width of a `bordered-button`. Calling `object-width` computes 84. The result is the sum of the results of the two applicable methods: the method `object-width` for the class `button` and the method `object-width` for the class `border-mixin`.

 
```
? (object-width (make-instance 'bordered-button))
84

```
 

### C++

 

#### Mixin with CRTP

 

In [C++](./C++), the traditional way one can implement mixins is using the [curiously recurring template pattern](./Curiously_recurring_template_pattern) (CRTP).

 
```
import std;

using std::string;
using std::three_way_comparable;
using std::tuple;

template <typename Host>
concept HasKey = requires (const Host& x) {
    { x.key() } -> three_way_comparable<bool>;
};

template <HasKey Host>
class CompareByKey {
protected:
    CompareByKey() = default;
    ~CompareByKey() = default;
public:
    // use a deduced type to allow strong_ordering when possible,
    // but keep other orderings if necessary
    [[nodiscard]]
    friend auto operator<=>(const Host& lhs, const Host& rhs) noexcept {
        return lhs.key() <=> rhs.key();
    }

    [[nodiscard]]
    friend bool operator==(const Host& lhs, const Host& rhs) noexcept {
        return lhs.key() == rhs.key();
    }
};

class Person : public CompareByKey<Person> {
private:
    string name;
    int age;
public:
    Person(string name, int age):
        name{std::move(name)}, age{age} {}

    [[nodiscard]]
    tuple<const string&, const int&> key() const noexcept {
        return std::tie(name, age);
    }
};

```
 

#### Mixin with annotations

 

Since [C++26](./C++26), C++ may use [annotations](./Attribute-oriented_programming) for [reflection](./Reflective_programming) to implement mixins.

 
```
import std;

using std::hash;
using std::string;
using std::vector;
using std::meta::info;

template <typename Host>
struct EqualityMixin {
    [[nodiscard]]
    bool operator==(const Host& other) const noexcept {
        const Host& self = static_cast<const Host&>(*this);

        template for (constexpr info m: std::meta::nonstatic_data_members_of(^^Host)) {
            if (!(self.[:m:] == other.[:m:])) {
                return false;
            }
        }
        return true;
    }

    [[nodiscard]]
    bool operator!=(const Host& other) const noexcept {
        return !(*this == other);
    }
};

template <typename Host>
struct HashMixin {
    static constexpr uint32_t FNV_PRIME = 0x9e3779b9;

    [[nodiscard]]
    size_t hash() const noexcept {
        const Host& self = static_cast<const Host&>(*this);
        size_t h = 0;
        template for (constexpr info m: std::meta::nonstatic_data_mebers_of(^^Host)) {
            h ^= hash<[: std:meta::type_of(m) :]>{}(self.[:m:]) + FNV_PRIME + (h << 6) + (h >> 2);
        }
        return h;
    }
};

template <typename Host>
struct ZeroMixin {
    void zero() {
        Host& self = static_cast<Host&>(*this);
        template for (constexpr info m: std::meta::nonstatic_data_mebers_of(^^Host)) {
            self.[:m:] = {};
        }
    }
};

// store the mixin templates as paramters of the annotation tag
// the parameters can be recovered using
// std::meta::template_arguments_of()
template <template <typename> typename... Ms>
struct Mixin {};

struct [[=Mixin<EqualityMixin, HashMixin, ZeroMixin>{}]] Vec2 {
    double x = 0.0; // x-coordinate
    double y = 0.0; // y-coordinate
};

struct [[=Mixin<EqualityMixin, HashMixin, ZeroMixin>{}]] Pixel {
    uint8_t r = 0; // red-value of pixel
    uint8_t g = 0; // green-value of pixel
    uint8_t b = 0; // blue-value of pixel
    uint8_t a = 255; // alpha-value of pixel
};

class [[=Mixin<HashMixin, ZeroMixin>{}]] Person {
private:
    string name;
    int age;
public:
    Person(string name, int age):
        name{std::move(name)}, age{age} {}

    // ...
};

```
 

### D

 

In the [D](./D_(programming_language)) programming language, there are two kinds of mixins: string mixins and template mixins.

 
```
mixin template AddFunction() {
    void addedFunction() {
        import std.stdio;
        writeln("Added function from mixin!");
    }
}

class MyClass {
    mixin AddFunction; // Injects addedFunction() into MyClass
}

void main() {
    // String mixin
    string code = `
        writeln("Hello from a string mixin!");
    `;

    mixin(code); // This injects and runs the writeln code

    // Template mixin
    MyClass obj = new MyClass();
    obj.addedFunction();
}

```
 

 

 

### Java

 

Mixins can be emulated in [Java](./Java_(programming_language)) using default method implementations on interfaces.

 
```
import java.time.Instant;

interface LoggerMixin {
    default void log(String fmt, Object... args) {
        System.out.printf("[LOG]: %s", String.format(fmt, args));
    }
}

interface TimestampMixin {
    default String currentTimestamp() {
        Instant.now().toString();
    }
}

class MyService implements LoggerMixin, TimestampMixin {
    public void doWork() {
        log("Starting work at %s", currentTimestamp());
    }
}

public class Main {
    public static void main(String[] args) {
        MyService service = new MyService();
        service.doWork();
    }
}

```
 

### JavaScript

 

#### The Object-Literal and `extend` Approach

 

It is technically possible to add behavior to an object by binding functions to keys in the object. However, this lack of separation between state and behavior has drawbacks:

 
1. It intermingles properties of the model domain with that of implementation domain.
2. No sharing of common behavior. Metaobjects solve this problem by separating the domain specific properties of objects from their behaviour specific properties.[[18]](./Mixin#cite_note-18)

 

An extend function is used to mix the behavior in the following (with [TypeScript](./TypeScript) type annotations):[[19]](./Mixin#cite_note-19)

 
```
'use strict';

interface NameMixin {
  fullName(): string;
  rename(first: string, last: string): this;
}

class Halfling {
  firstName: string;
  lastName: string;

  constructor(first: string, last: string) {
    this.firstName = first;
    this.lastName = last;
  }
}

const mixin: NameMixin = {
  fullName() {
    return this.firstName + ' ' + this.lastName;
  },
  rename(first: string, last: string) {
    this.firstName = first;
    this.lastName = last;
    return this;
  }
};

// An extend function
function extend<T, U>(obj: T, mixin: U): T & U {
  Object.keys(mixin).forEach(key => {
    (obj as any)[key] = (mixin as any)[key];
  });
  return obj as T & U;
}

// Mixin the other methods
extend(Halfling.prototype, mixin);

// Indicate that Halfling now includes the mixin metohds:
interface Halfling extends NameMixin {}

const sam: Halfling = new Halfling('Sam', 'Loawry');
const frodo: Halfling = new Halfling('Freeda', 'Baggs');

console.log(sam.fullName()); // Sam Loawry
console.log(frodo.fullName()); // Freeda Baggs

sam.rename('Samwise', 'Gamgee');
frodo.rename('Frodo', 'Baggins');

console.log(sam.fullName()); // Samwise Gamgee
console.log(frodo.fullName()); // Frodo Baggins

```
 

#### Mixin with using `Object.assign()`

 
```
'use strict';

interface Person {
  name: string;
  city: string;
  born: string;
}

interface Mix1 {
  toString(): string;
  age(): number;
}

interface Mix2 {
  toString(): string;
}

type PersonWithMixins = Person & Mix1 & Mix2;

// Creating an object
const obj1: Person = {
  name: 'Marcus Aurelius',
  city: 'Rome',
  born: '121-04-26'
};

// Mixin 1
const mix1: Mix1 = {
  toString() {
    return `${this.name} was born in ${this.city} in ${this.born}`;
  },
  age() {
    const year: number = new Date().getFullYear();
    const born: number = new Date(this.born).getFullYear();
    return year - born;
  }
};

// Mixin 2
const mix2: Mix2 = {
  toString() {
    return `${this.name} - ${this.city} - ${this.born}`;
  }
};

// Adding the methods from mixins to the object using Object.assign()
const mixedObj: PersonWithMixins = Object.assign(obj1, mix1, mix2) as PersonWithMixins;

console.log(obj1.toString()); // Marcus Aurelius - Rome - 121-04-26
console.log(`His age is ${obj1.age()} as of today`); // His age is 1897 as of today

```
 

#### The pure function and delegation based Flight-Mixin Approach

 

Even though the firstly described approach is mostly widespread the next one is closer to what JavaScript's language core fundamentally offers - [Delegation](./JavaScript#Delegative).

 

Two [function object](./Function_object) based patterns already do the trick without the need of a third party's implementation of `extend`.

 
```
'use strict';

interface FirstLast<T> {
  first(): T | undefined;
  last(): T | undefined;
}

// Extend the Array type globally
interface Array<T> extends FirstLast<T> {}

// Implementation
const EnumerableFirstLast = (function () {
  const first = function <T>(this: T[]): T | undefined {
    if (this.length === 0) {
      return null;
    }
    return this[0];
  };

  const last = function <T>(this: T[]): T | undefined {
    return this[this.length - 1];
  };

  return function (this: any) {
    this.first = first;
    this.last = last;
  };
}());

// Application - explicit delegation:
// applying [first] and [last] enumerable behavior onto [Array]'s [prototype].
EnumerableFirstLast.call(Array.prototype);

// Now you can do:
const a: number[] & FirstLast<number> = [1, 2, 3];
a.first(); // 1
a.last(); // 3

```
 

### Python

 

In [Python](./Python_(programming_language)), an example of the mixin concept is found in the `socketserver` module,[[20]](./Mixin#cite_note-20) which has both a `UDPServer` class and a `TCPServer` class. They act as servers for [UDP](./User_Datagram_Protocol) and [TCP](./Transmission_Control_Protocol) socket servers, respectively. Additionally, there are two mixin classes: `ForkingMixIn` and `ThreadingMixIn`. Normally, all new connections are handled within the same process. By extending `TCPServer` with the `ThreadingMixIn` as follows:

 
```
from socketserver import TCPServer, ThreadingMixIn

class ThreadingTCPServer(ThreadingMixIn, TCPServer):
    pass

```
 

the `ThreadingMixIn` class adds functionality to the TCP server such that each new connection creates a new [thread](./Thread_(computer_science)). Using the same method, a `ThreadingUDPServer` can be created without having to duplicate the code in `ThreadingMixIn`. Alternatively, using the `ForkingMixIn` would cause the process to be [forked](./Fork_(operating_system)) for each new connection. Clearly, the functionality to create a new thread or fork a process is not terribly useful as a stand-alone class.

 

In this usage example, the mixins provide alternative underlying functionality without affecting the functionality as a socket server.

 

### Ruby

 

Most of the Ruby world is based around mixins via `Modules`. The concept of mixins is implemented in Ruby by the keyword `include` to which we pass the name of the module as [parameter](./Parameter_(computer_programming)).

 

Example:

 
```
class Student
  include Comparable # The class Student inherits the Comparable module using the 'include' keyword
  attr_accessor :name, :score

  def initialize(name, score)
    @name = name
    @score = score
  end

  # Including the Comparable module requires the implementing class to define the <=> comparison operator
  # Here's the comparison operator. We compare 2 student instances based on their scores.

  def <=>(other)
    @score <=> other.score
  end

  # Here's the good bit - I get access to <, <=, >,>= and other methods of the Comparable Interface for free.
end

s1 = Student.new("Peter", 100)
s2 = Student.new("Jason", 90)

s1 > s2 #true
s1 <= s2 #false

```
 

### In other languages

 

In the [Curl](./Curl_(programming_language)) web-content language, multiple inheritance is used as classes with no instances may implement methods. Common mixins include all skinnable `ControlUI`s inheriting from `SkinnableControlUI`, user interface delegate objects that require dropdown menus inheriting from StandardBaseDropdownUI and such explicitly named mixin classes as `FontGraphicMixin`, `FontVisualMixin` and `NumericAxisMixin-of` class. Version 7.0 added library access so that mixins do not need to be in the same package or be public abstract. Curl constructors are factories that facilitates using multiple-inheritance without explicit declaration of either interfaces or mixins.[*[citation needed](./Wikipedia:Citation_needed)*]

 

## Interfaces and traits

 

Java 8 introduces a new feature in the form of default methods for interfaces.[[21]](./Mixin#cite_note-21) Basically it allows a method to be defined in an interface with application in the scenario when a new method is to be added to an interface after the interface class programming setup is done. To add a new function to the interface means to implement the method at every class which uses the interface. Default methods help in this case where they can be introduced to an interface any time and have an implemented structure which is then used by the associated classes. Hence default methods add the ability to applying the mixin concept in Java.

 

Interfaces combined with [aspect-oriented programming](./Aspect-oriented_programming) can also produce full-fledged mixins in languages that support such features, such as C# or Java. Additionally, through the use of the [marker interface pattern](./Marker_interface_pattern), [generic programming](./Generic_programming), and extension methods, C# 3.0 has the ability to mimic mixins. With Dart 2.7 and C# 3.0 came the introduction of extension methods which can be applied, not only to classes, but also to interfaces. Extension Methods provide additional functionality on an existing class without modifying the class. It then becomes possible to create a static helper class for specific functionality that defines the extension methods. Because the classes implement the interface (even if the actual interface doesn’t contain any methods or properties to implement) it will pick up all the extension methods also.[[3]](./Mixin#cite_note-:2-3)[[4]](./Mixin#cite_note-:3-4)[[22]](./Mixin#cite_note-22) C# 8.0 adds the feature of default interface methods.[[23]](./Mixin#cite_note-23)[[24]](./Mixin#cite_note-24)

 

[ECMAScript](./ECMAScript) (in most cases implemented as JavaScript) does not need to mimic [object composition](./Object_composition) by step-wise copying fields from one object to another. It natively[[25]](./Mixin#cite_note-25) supports [Trait](./Trait_(computer_programming)) and mixin[[26]](./Mixin#cite_note-26)[[27]](./Mixin#cite_note-27) based object composition via function objects that implement additional behavior and then are delegated via `call` or `apply` to objects that are in need of such new functionality.

 

### Scala

 

Scala has a rich [type system](./Type_system) and Traits are a part of it which helps implement mixin behaviour. As their name reveals, Traits are usually used to represent a distinct feature or aspect that is normally orthogonal to the responsibility of a concrete type or at least of a certain instance.[[28]](./Mixin#cite_note-28)
For example, the ability to sing is modeled as such an orthogonal feature: it could be applied to Birds, Persons, etc.

 
```
trait Singer{
  def sing { println(" singing … ") }
  //more methods
}

class Bird extends Singer

```
 

Here, Bird has mixed in all methods of the trait into its own definition as if class Bird had defined method sing() on its own.

 

As `extends` is also used to inherit from a super class, in case of a trait `extends` is used if no super class is inherited and only for mixin in the first trait. All following traits are mixed in using keyword `with`.

 
```
class Person
class Actor extends Person with Singer
class Actor extends Singer with Performer

```
 

Scala allows mixing in a trait (creating an [anonymous type](./Anonymous_type)) when creating a new instance of a class. In the case of a Person class instance, not all instances can sing, but we can create a specific Person instance that can sing.

 
```
class Person{
  def tell {  println (" Human ") }
  //more methods
}

val singingPerson = new Person with Singer
singingPerson.sing

```
 

### Rust

 

Rust makes extensive use of mixins via *traits*. Traits, like in Scala, allow users to implement behaviours for a defined type. They are also used for [generics](./Generic_programming) and [dynamic dispatch](./Dynamic_dispatch), allowing types implementing a trait to be used interchangeably statically or dynamically at runtime.[[29]](./Mixin#cite_note-29)

 
```
// Allows for types to "speak"
trait Speak {
	fn speak(&self);

	// Rust allows implementors to define default implementations for functions defined in traits
	fn greet(&self) {
		println!("Hi!")
	}
}

struct Dog {
    name: String,
}

impl Speak for Dog {
	fn speak(&self) {
		println!("{} says, 'Woof woof!'", self.name);
	}
}

struct Robot {
    name: String,
}

impl Speak for Robot {
	fn speak(&self) {
		println!("{} says 'Beep beep boop boop', self.name");
	}

	// Here we override the definition of Speak::greet for Robot
	fn greet(&self) {
		println!("Robot {} says 'Howdy!'", self.name)
	}
}

```
 

### Swift

 

Mixin can be achieved in Swift by using a language feature called Default implementation in Protocol Extension.

 
```
protocol ErrorDisplayable {
    func error(message: String)
}

extension ErrorDisplayable {
    func error(message: String) {
        // Do what it needs to show an error
        //...
        print(message)
    }
}

struct NetworkManager : ErrorDisplayable {
    func onError() {
        error("Please check your internet Connection.")
    }
}

```
 

## See also

 
- [Abstract type](./Abstract_type)
- [Decorator pattern](./Decorator_pattern)
- [Policy-based design](./Policy-based_design)
- [Trait](./Trait_(computer_programming)), a similar structure that does not require linear composition

 

## References

 
1. [1](./Mixin#cite_ref-:0_1-0) [2](./Mixin#cite_ref-:0_1-1) ["Using Mix-ins with Python | Linux Journal"](https://www.linuxjournal.com/article/4540). *www.linuxjournal.com*. Retrieved 2023-05-23.
2. [1](./Mixin#cite_ref-:1_2-0) [2](./Mixin#cite_ref-:1_2-1) AOL.COM, Bapopik at (3 August 2002). ["Mix-Ins (Steve's ice cream, Boston, 1975)"](https://listserv.linguistlist.org/pipermail/ads-l/2002-August/024421.html). Retrieved 2023-05-23.
3. [1](./Mixin#cite_ref-:2_3-0) [2](./Mixin#cite_ref-:2_3-1) ["Implementing Mixins with C# Extension Methods"](https://www.zorched.net/2008/01/03/implementing-mixins-with-c-extension-methods/). *Zorched / One-Line Fix*. Retrieved 2023-05-23.
4. [1](./Mixin#cite_ref-:3_4-0) [2](./Mixin#cite_ref-:3_4-1) ["I know the answer (it's 42) : Mixins and C#"](https://web.archive.org/web/20060904095424/http://blogs.msdn.com/abhinaba/archive/2006/01/06/510034.aspx). 2006-09-04. Archived from [the original](http://blogs.msdn.com/abhinaba/archive/2006/01/06/510034.aspx) on 2006-09-04. Retrieved 2023-05-23.
5. [↑](./Mixin#cite_ref-5) Boyland, John; Giuseppe Castagna (26 June 1996). ["Type-Safe Compilation of Covariant Specialization: A Practical Case"](https://books.google.com/books?id=sGvtaGy8SJ8C&dq=pathologies+of+multiple+inheritance&pg=PA16). In Pierre Cointe (ed.). *ECOOP '96, Object-oriented Programming: 10th European Conference*. Springer. pp. 16–17. [ISBN](./ISBN_(identifier)) [9783540614395](./Special:BookSources/9783540614395). Retrieved 17 January 2014.
6. [↑](./Mixin#cite_ref-6) ["Mix In"](http://wiki.c2.com/?MixIn). *wiki.c2.com*. Retrieved 2023-05-23.
7. [↑](./Mixin#cite_ref-7) ["Working with Mixins in Ruby"](https://culttt.com/2015/07/08/working-with-mixins-in-ruby/). 8 July 2015.
8. [↑](./Mixin#cite_ref-8) ["Re-use in OO: Inheritance, Composition and Mixins"](https://naildrivin5.com/blog/2012/12/19/re-use-in-oo-inheritance.html).
9. [↑](./Mixin#cite_ref-9) ["Moving beyond mixins » Justin Leitgeb"](https://web.archive.org/web/20150925090219/http://justinleitgeb.com/ruby/moving-beyond-mixins/). Archived from [the original](http://justinleitgeb.com/ruby/moving-beyond-mixins/) on 2015-09-25. Retrieved 2015-09-16.
10. [↑](./Mixin#cite_ref-10) ["Mixin-based Inheritance"](http://www.bracha.org/oopsla90.pdf) (PDF).
11. [↑](./Mixin#cite_ref-11) Bill Wagner. ["Create mixin types using default interface methods"](https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/tutorials/mixins-with-default-interface-methods). *docs.microsoft.com*. Retrieved 2022-04-18.
12. [↑](./Mixin#cite_ref-12) ["ET: Inheritance"](https://www.eiffel.org/doc/eiffel/ET-_Inheritance#Non-conforming_inheritance). *www.eiffel.org*. 2024-06-03. Retrieved 2024-11-05.
13. [↑](./Mixin#cite_ref-13) slava (2010-01-25). ["Factor/Features/The language"](https://concatenative.org/wiki/view/Factor/Features/The%20language). concatenative.org. Retrieved 2012-05-15. Factor's main language features: … Object system with Inheritance, Generic functions, Predicate dispatch and *Mixins*
14. [↑](./Mixin#cite_ref-14) ["Classes - MATLAB & Simulink - MathWorks India"](https://in.mathworks.com/help/matlab/mixin-classes.html).
15. [↑](./Mixin#cite_ref-15) Alain Frisch (2013-06-14). ["Mixin objects"](https://www.lexifi.com/blog/ocaml/mixin/). LexiFi. Retrieved 2022-03-29.
16. [↑](./Mixin#cite_ref-16) ["Mixin Class Composition"](https://docs.scala-lang.org/tutorials/tour/mixin-class-composition.html). [École polytechnique fédérale de Lausanne](./École_polytechnique_fédérale_de_Lausanne). Retrieved 16 May 2014.
17. [↑](./Mixin#cite_ref-17) ["XOTcl - Tutorial"](http://media.wu-wien.ac.at/doc/tutorial.html#mixins). *media.wu-wien.ac.at*. Retrieved 2023-05-23.
18. [↑](./Mixin#cite_ref-18) ["Mixins, Forwarding, and Delegation in JavaScript"](https://raganwald.com/2014/04/10/mixins-forwarding-delegation.html).
19. [↑](./Mixin#cite_ref-19) ["DRY JavaScript with mixins"](https://web.archive.org/web/20150921074320/http://bob.yexley.net/dry-javascript-with-mixins/). Archived from [the original](http://bob.yexley.net/dry-javascript-with-mixins/) on 2015-09-21. Retrieved 2015-09-16.
20. [↑](./Mixin#cite_ref-20) ["cpython: 2cb530243943 Lib/socketserver.py"](https://hg.python.org/cpython/file/3.5/Lib/socketserver.py). *hg.python.org*. Retrieved 2023-05-23.
21. [↑](./Mixin#cite_ref-21) ["Default Methods (The Java™ Tutorials > Learning the Java Language > Interfaces and Inheritance)"](https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html).
22. [↑](./Mixin#cite_ref-22) [Mixins, generics and extension methods in C#](http://erwyn.bloggingabout.net/2005/10/20/mixins-generics-and-extension-methods-in-c/)
23. [↑](./Mixin#cite_ref-23) ["Extension methods"](https://web.archive.org/web/20200923021740/https://flutterbyexample.com/lesson/extension-methods/). *flutterbyexample.com*. Archived from the original on September 23, 2020. Retrieved 2023-05-23.
24. [↑](./Mixin#cite_ref-24) ["Create mixin types using default interface methods | Microsoft Docs"](https://web.archive.org/web/20200413082731/https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/mixins-with-default-interface-methods). 2020-04-13. Archived from [the original](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/mixins-with-default-interface-methods) on 2020-04-13. Retrieved 2023-05-23.
25. [↑](./Mixin#cite_ref-25) Seliger, Peter (2014-04-11). ["Drehtür: The-many-Talents-of-JavaScript"](https://peterseliger.blogspot.com/2014/04/the-many-talents-of-javascript.html). *Drehtür*. Retrieved 2023-05-23.
26. [↑](./Mixin#cite_ref-26) Croll, Angus (2011-05-31). ["A fresh look at JavaScript Mixins"](https://javascriptweblog.wordpress.com/2011/05/31/a-fresh-look-at-javascript-mixins/). *JavaScript, JavaScript..*. Retrieved 2023-05-23.
27. [↑](./Mixin#cite_ref-27) ["javascript-code-reuse-patterns/source/components/composition at master · petsel/javascript-code-reuse-patterns"](https://github.com/petsel/javascript-code-reuse-patterns). *GitHub*. Retrieved 2023-05-23.
28. [↑](./Mixin#cite_ref-28) ["Scala in practice: Traits as Mixins – Motivation"](https://gleichmann.wordpress.com/2009/07/19/scala-in-practice-traits-as-mixins-motivation). 19 July 2009.
29. [↑](./Mixin#cite_ref-29) ["Traits: Defining Shared Behavior - the Rust Programming Language"](https://doc.rust-lang.org/book/ch10-02-traits.html).

 

## External links

 
- [MixIn](http://c2.com/cgi/wiki?MixIn) at Portland Pattern Repository
- [Mixins](https://web.archive.org/web/20050308114937/http://www.macromedia.com/support/documentation/en/flex/1/mixin/index.html) in [ActionScript](./ActionScript)
- [The Common Lisp Object System: An Overview](https://www.dreamsongs.com/Files/ECOOP.pdf) by [Richard P. Gabriel](./Richard_P._Gabriel) and Linda DeMichiel provides a good introduction to the motivation for defining classes by means of generic functions.

 Categories