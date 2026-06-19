---
source: https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming)
fetched: 2026-06-19
---

Evaluation and comparison of objects For other uses, see [Delegation (computing)](./Delegation_(computing)). Not to be confused with [Forwarding (object-oriented programming)](./Forwarding_(object-oriented_programming)). 

In [object-oriented programming](./Object-oriented_programming), **delegation** refers to evaluating a member ([property](./Property_(programming)) or [method](./Method_(computer_programming))) of one [object](./Object_(computer_science)) (the receiver) in the context of another original object (the sender). Delegation can be done explicitly, by passing the responsibilities of the sending object to the receiving object, which can be done in any [object-oriented language](./Object-oriented_language); or implicitly, by the member lookup rules of the language, which requires language support for the feature. Implicit delegation is the fundamental method for behavior reuse in [prototype-based programming](./Prototype-based_programming), corresponding to [inheritance](./Inheritance_(object-oriented_programming)) in [class-based programming](./Class-based_programming). The best-known languages that support delegation at the language level are [Self](./Self_(programming_language)), which incorporates the notion of delegation through its notion of [mutable](./Mutable) parent [slots](./Slot_(computer_architecture)) that are used upon method lookup on self calls, and [JavaScript](./JavaScript); see [JavaScript delegation](./JavaScript#Delegative).

 

The term *delegation* is also used loosely for various other relationships between objects; see [delegation (programming)](./Delegation_(programming)) for more. Frequently confused concepts are simply using another object, more precisely referred to as *consultation* or *[aggregation](./Object_aggregation)*; and evaluating a member on one object by evaluating the corresponding member on another object, notably in the context of the receiving object, which is more precisely referred to as *[forwarding](./Forwarding_(object-oriented_programming))* (when a wrapper object doesn't pass itself to the wrapped object).[[1]](./Delegation_(object-oriented_programming)#cite_note-FOOTNOTEGammaHelmJohnsonVlissides1995"Delegation",_pp._20–21-1)[[2]](./Delegation_(object-oriented_programming)#cite_note-FOOTNOTEBeck1997"Delegation",_pp._64–69-2)[[a]](./Delegation_(object-oriented_programming)#cite_note-3) The [delegation pattern](./Delegation_pattern) is a [software design pattern](./Software_design_pattern) for implementing delegation, though this term is also used loosely for consultation or forwarding.

 

## Overview

 

This sense of *delegation* as programming language feature making use of the method lookup rules for dispatching so-called [self-calls](./Self-call?action=edit&redlink=1) was defined by [Lieberman](./Henry_Lieberman) in his 1986 paper "Using Prototypical Objects to Implement Shared Behavior in Object-Oriented Systems".

 

Delegation is dependent upon [dynamic binding](./Dynamic_binding_(computer_science)), as it requires that a given method call can invoke different segments of code at runtime[*[citation needed](./Wikipedia:Citation_needed)*]. It is used throughout [macOS](./MacOS) (and its predecessor [NeXTStep](./NeXTStep)) as a means of customizing the behavior of program components.[[3]](./Delegation_(object-oriented_programming)#cite_note-4) It enables implementations such as making use of a single OS-provided class to manage windows, because the class takes a delegate that is program-specific and can override default behavior as needed. For instance, when the user clicks the close box, the window manager sends the delegate a windowShouldClose: call, and the delegate can delay the closing of the window, if there is unsaved data represented by the window's contents.

 

Delegation can be characterized (and distinguished from [forwarding](./Forwarding_(object-oriented_programming))) as *late binding of self*:[[4]](./Delegation_(object-oriented_programming)#cite_note-5)

 

... messages sent to the `self` (or `this`) variable in the parent will "come back" to the object that originally received the message.

 

That is, the `self` in a method definition in the receiving object is *not* statically bound to that object at definition time (such as compile time or when the function is attached to an object), but rather at *evaluation* time, it is bound to the *original* object.

 

It has been argued that delegation may in some cases be preferred to [inheritance](./Inheritance_(object-oriented_programming)) to make program code more readable and understandable.[[5]](./Delegation_(object-oriented_programming)#cite_note-6) Despite explicit delegation being fairly widespread, relatively few major programming languages implement delegation as an alternative model to inheritance. The precise relationship between delegation and inheritance is complicated; some authors consider them equivalent, or one a special case of the other.[[6]](./Delegation_(object-oriented_programming)#cite_note-7)

 

## Language support for delegation

 

In languages that support delegation via method lookup rules, method dispatching is defined the way it is defined for virtual methods in inheritance: It is always the most specific method that is chosen during method lookup. Hence it is the *original* receiver entity that is the start of method lookup even though it has passed on control to some other object (through a delegation link, not an object reference).

 

Delegation has the advantage that it can take place at run time and affect only a subset of entities of some type and can even be removed at run time. Inheritance, by contrast, typically targets the type rather than the instances, and is restricted to compile time. On the other hand, inheritance can be statically type-checked, while delegation generally cannot without generics (although a restricted version of delegation can be statically typesafe[[7]](./Delegation_(object-oriented_programming)#cite_note-8)). Delegation can be termed "run-time inheritance for specific objects."

 

Here is a [pseudocode](./Pseudocode) example in a [C#](./C_Sharp_(programming_language))/[Java](./Java_(programming_language)) like language:

 
```
class A {
    void foo() {
        // "this" also known under the names "current", "me" and "self" in other languages
        this.bar();
    }

    void bar() {
        print("a.bar");
    }
}

class B {
    private delegate A a; // delegation link

    public B(A a) {
        this.a = a;
    }

    void foo() {
        a.foo(); // call foo() on the a-instance
    }

    void bar() {
        print("b.bar");
    }
}

a = new A();
b = new B(a); // establish delegation between two objects

```
 

Calling `b.foo()` will result in **b.bar** being printed, since `this` refers to the *original* sending object, `b`, within the context of `a`. The resulting ambiguity of `this` is referred to as [object schizophrenia](./Object_schizophrenia).

 

Translating the implicit `this` into an explicit parameter, the call (in `B`, with `a` a delegate) `a.foo()` translates to `A.foo(b)`, using the type of `a` for method resolution, but the delegating object `b` for the `this` argument.

 

Using inheritance, the analogous code (using capital letters to emphasize that resolution is based on classes, not objects) is:

 
```
class A {
    void foo() {
        this.bar();
    }

    void bar() {
        print("A.bar");
    }
}

class B extends A {
    public B() {}

    void foo() {
        super.foo(); // call foo() of the superclass (A)
    }

    void bar() {
        print("B.bar");
    }
}

b = new B();

```
 

Calling `b.foo()` will result in **B.bar**. In this case, `this` is unambiguous: there is a single object, `b`, and `this.bar()` resolves to the method on the subclass.

 

Programming languages in general do not support this unusual form of delegation as a language concept, but there are a few exceptions[*[citation needed](./Wikipedia:Citation_needed)*].

 

### Dual inheritance

 

If the language supports both delegation and inheritance one can do **dual inheritance** by utilizing both mechanisms at the same time as in

 
```
class C extends A {
    delegationlink D d;
}

```
 

This calls for additional rules for method lookup, as there are now potentially two methods that can be denoted as the most specific (due to the two lookup paths).

 

### Related areas

 

Delegation can be described as a low level mechanism for sharing code and data between entities. Thus it builds the foundation for other language constructs. Notably [role-oriented programming](./Role-oriented_programming) languages have been utilizing delegation, but especially the older ones factually used [aggregation](./Aggregation_(object-oriented_programming)) while claiming to use delegation. This should not be considered cheating, merely the plural definitions of what delegation means (as described above).

 

More recently work has also been done on distributing delegation, so e.g. clients of a search engine (finding cheap hotel rooms) can use a shared entity using delegation to share best hits and general re-usable functionality.

 

Delegation has also been suggested for advice resolution in [aspect-oriented programming](./Aspect-oriented_programming) by Ernst and Lorenz in 2003.

 

## See also

 
- [Delegation pattern](./Delegation_pattern)
- [Adapter pattern](./Adapter_pattern)
- [Hooking](./Hooking)
- [Continuation](./Continuation)
- [Implementation inheritance](./Implementation_inheritance)
- [Inheritance semantics](./Inheritance_semantics)
- [Schizophrenia (object-oriented programming)](./Schizophrenia_(object-oriented_programming))
- [Virtual inheritance](./Virtual_inheritance)
- [Wrapper function](./Wrapper_function)

 

Distinguish:

 
- [Delegate (CLI)](./Delegate_(CLI))
- [Delegation (programming)](./Delegation_(programming))
- [Object aggregation](./Object_aggregation)
- [Forwarding (object-oriented programming)](./Forwarding_(object-oriented_programming))

 

## Notes

  
1. [↑](./Delegation_(object-oriented_programming)#cite_ref-3) Beck 1997 uses the terms "simple delegation" for when the receiving object does not have access to the sending object, and "self delegation" for when the receiving object does have access to the sending object; in modern language these are "forwarding" and "delegation", as used in this article.

 

## References

 
1. [↑](./Delegation_(object-oriented_programming)#cite_ref-FOOTNOTEGammaHelmJohnsonVlissides1995"Delegation",_pp._20–21_1-0) [Gamma et al. 1995](./Delegation_(object-oriented_programming)#CITEREFGammaHelmJohnsonVlissides1995), "Delegation", pp. 20–21.
2. [↑](./Delegation_(object-oriented_programming)#cite_ref-FOOTNOTEBeck1997"Delegation",_pp._64–69_2-0) [Beck 1997](./Delegation_(object-oriented_programming)#CITEREFBeck1997), "Delegation", pp. 64–69.
3. [↑](./Delegation_(object-oriented_programming)#cite_ref-4) Apple (2009-08-20). ["Cocoa Fundamentals Guide: Delegates and Data Sources"](https://developer.apple.com/mac/library/documentation/Cocoa/Conceptual/CocoaFundamentals/CommunicatingWithObjects/CommunicateWithObjects.html). *Apple Developer Connection*. Retrieved 2009-09-11.
4. [↑](./Delegation_(object-oriented_programming)#cite_ref-5)  "Intersecting Classes and Prototypes". *Perspectives of Systems Informatics: 5th International Andrei Ershov Memorial Conference, PSI 2003, Akademgorodok, Novosibirsk, Russia, July 9-12, 2003, Revised Papers*. p. [38](https://books.google.com/books?id=lqL4wL5aSkkC&pg=PA38&dq=delegation).
5. [↑](./Delegation_(object-oriented_programming)#cite_ref-6) [](http://heim.ifi.uio.no/~trygver/2007/readability.pdf)[Trygve Reenskaug](./Trygve_Reenskaug), Dept. of Informatics, University of Oslo, "The Case for Readable Code" (2007)
6. [↑](./Delegation_(object-oriented_programming)#cite_ref-7) Stein, Lynn Andrea. *Delegation is Inheritance*. OOPSLA '87 Conference proceedings on Object-oriented programming systems, languages and applications. pp. 138–146. [doi](./Doi_(identifier)):[10.1145/38807.38820](https://doi.org/10.1145%2F38807.38820).
7. [↑](./Delegation_(object-oriented_programming)#cite_ref-8) Günter Kniesel (1999-11-19). ["Type-Safe Delegation for Run-Time Component Adaptation"](https://web.archive.org/web/20150304020026/http://link.springer.com/). *ECOOP' 99 — Object-Oriented Programming*. Lecture Notes in Computer Science. Vol. 1628. Springer. pp. 351–366. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.33.7584](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.33.7584). [doi](./Doi_(identifier)):[10.1007/3-540-48743-3_16](https://doi.org/10.1007%2F3-540-48743-3_16). [ISBN](./ISBN_(identifier)) [978-3-540-66156-6](./Special:BookSources/978-3-540-66156-6). Archived from the original on 2015-03-04. Retrieved 2015-03-04. This paper proposes object-based inheritance (also known as delegation) as a complement to purely forwarding-based object composition. It presents a typesafe integration of delegation into a class-based object model and shows how it overcomes the problems faced by forwarding-based component interaction, how it supports independent extensibility of components and unanticipated, dynamic component adaptation.`{{cite book}}`:  CS1 maint: bot: original URL status unknown ([link](./Category:CS1_maint:_bot:_original_URL_status_unknown))

  
- [Lieberman, Henry](./Henry_Lieberman) (1986). ["Using prototypical objects to implement shared behavior in object-oriented systems"](http://web.media.mit.edu/~lieber/Lieberary/OOP/Delegation/Delegation.html). *Conference proceedings on Object-oriented programming systems, languages and applications*. Vol. 21. Portland. pp. 214–223. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.48.69](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.48.69). [doi](./Doi_(identifier)):[10.1145/960112.28718](https://doi.org/10.1145%2F960112.28718). `{{cite book}}`: `|journal=` ignored ([help](./Help:CS1_errors#periodical_ignored))CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
- Lynn Andrea Stein, Henry Liberman, David Ungar: *A shared view of sharing: The Treaty of Orlando*. In: Won Kim, Frederick H. Lochovsky (Eds.): *Object-Oriented Concepts, Databases, and Applications* ACM Press, New York 1989, ch. 3, pp. 31–48 [ISBN](./ISBN_(identifier)) [0-201-14410-7](./Special:BookSources/0-201-14410-7) (online at [Citeseer](http://citeseer.ist.psu.edu/stein89shared.html))
- [Gamma, Erich](./Erich_Gamma); [Helm, Richard](./Richard_Helm); [Johnson, Ralph](./Ralph_Johnson_(computer_scientist)); [Vlissides, John](./John_Vlissides) (1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](./Design_Patterns_(book)). [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0).
- Malenfant, J.: On the Semantic Diversity of Delegation-Based Programming Languages, *Proceedings of the OOPSLA95,* New York: ACM 1995, pp. 215–230.
- [Beck, Kent](./Kent_Beck) (1997). *Smalltalk Best Practice Patterns*. Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0134769042](./Special:BookSources/978-0134769042).
- Kasper Bilsted Graversen: *The nature of roles---A taxonomic analysis of roles as a language construct.* Ph.D. Thesis 2006, (Online at [IT University of Copenhagen](https://web.archive.org/web/20120329110415/http://www.it-c.dk/people/kbilsted/graversen06thesis.pdf))

  

## External links

 
- [A new way to implement Delegate in C++](https://web.archive.org/web/20070916214628/http://www.codeproject.com/cpp/CppDelegateImplementation.asp)
- [Fast delegates in C++](https://web.archive.org/web/20070701084227/http://www.codeproject.com/cpp/FastDelegate.asp)
- [PerfectJPattern Open Source Project](https://perfectjpattern.sourceforge.net/delegates.html), Provides a reusable implementation of Delegates in Java

 Categories