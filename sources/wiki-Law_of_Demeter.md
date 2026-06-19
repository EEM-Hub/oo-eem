---
source: https://en.wikipedia.org/wiki/Law_of_Demeter
fetched: 2026-06-19
---

Design guideline for software development 

The **Law of Demeter** (**LoD**) or **principle of least knowledge** is a design guideline for developing [software](./Software), particularly [object-oriented programs](./Object-oriented_programming). In its general form, the LoD is a specific case of [loose coupling](./Loose_coupling). The guideline was proposed by Ian Holland at [Northeastern University](./Northeastern_University) towards the end of 1987,[[1]](./Law_of_Demeter#cite_note-1) and the following three recommendations serve as a succinct summary:[[2]](./Law_of_Demeter#cite_note-2)

 
1. Each unit should have only limited knowledge about other units: only units "closely" related to the current unit.
2. Each unit should only talk to its friends; don't talk to strangers.
3. Only talk to your immediate friends.

 

The fundamental notion is that a given object should assume as little as possible about the structure or properties of anything else (including its subcomponents), in accordance with the principle of "[information hiding](./Information_hiding)". It may be viewed as a corollary to the [principle of least privilege](./Principle_of_least_privilege), which dictates that a module possess only the information and resources necessary for its legitimate purpose.

 

It is so named for its origin in the [Demeter Project](./Demeter_Project?action=edit&redlink=1), an [adaptive programming](./Adaptive_programming?action=edit&redlink=1) and [aspect-oriented programming](./Aspect-oriented_programming) effort. The project was named in honor of [Demeter](./Demeter), "distribution-mother" and the Greek [goddess](./Goddess) of [agriculture](./Agriculture), to signify a [bottom-up](./Top-down_and_bottom-up_design) philosophy of programming which is also embodied in the law itself.[[3]](./Law_of_Demeter#cite_note-3)[*[non-primary source needed](./Wikipedia:No_original_research#Primary,_secondary_and_tertiary_sources)*]

 

## History

 

The law of Demeter dates back to 1987 when it was first proposed by Ian Holland, who was working on the Demeter Project. This project was the birthplace of a lot of [aspect-oriented programming](./Aspect-oriented_programming) (AOP) principles.

 

A quote in one of the remainders of the project seems to clarify the origins of the name:[[4]](./Law_of_Demeter#cite_note-4)

 

**Demeter**

 

*The Greek goddess of Agriculture.*

 

 The Demeter project was named after Demeter because we were working
  on a hardware description language Zeus and we were looking for a tool
  to simplify the implementation of Zeus. We were looking for a tool name
  related to Zeus and we chose a sister of Zeus: Demeter.

 

 We later promoted the idea that Demeter-style software development is
  about growing software as opposed to building software.
  We introduced the concept of a growth plan which is basically
  a sequence of more and more complex UML class diagrams.
 

 Growth plans are useful for building systems incrementally.

 

## In object-oriented programming

 

An object `a` can request a service (call a method) of an object instance `b`, but object `a` should not "reach through" object `b` to access yet another object, `c`, to request its services. Doing so would mean that object `a` implicitly requires greater knowledge of object `b`'s internal structure.

 

Instead, `b`'s interface should be modified if necessary so it can directly serve object `a`'s request, propagating it to any relevant subcomponents. Alternatively, `a` might have a direct reference to object `c` and make the request directly to that. If the law is followed, only object `b` knows its own internal structure.

 

More formally, the Law of Demeter for functions requires that a method `m` of an object `a` may only invoke the methods of the following kinds of objects:[[5]](./Law_of_Demeter#cite_note-5)

 
- `a` itself;
- `m`'s parameters;
- any objects instantiated within `m`;
- `a`'s attributes;
- global variables accessible by `a` in the scope of `m`.

 

In particular, an object should avoid invoking methods of an object returned by another method. For many modern object-oriented languages that use a dot as field identifier, the law can be stated simply as "use only one dot".[[6]](./Law_of_Demeter#cite_note-6) That is, the code `a.m().n()` breaks the law where `a.m()` does not. As an [analogy](./Analogy), when one wants a dog to walk, one does not command the dog's legs to walk directly; instead, one commands the dog which then commands its own legs.

 

## Advantages

 

The advantage of following the Law of Demeter is that the resulting software tends to be more [maintainable](./Maintainability) and [adaptable](./Adaptive_reuse). Since objects are [less dependent](./Coupling_(computer_programming)) on the internal structure of other objects, object implementation can be [changed](./Software_configuration_management) without reworking their callers.

 

Basili et al.[[7]](./Law_of_Demeter#cite_note-Basili-7) published experimental results in 1996 suggesting that a lower *Response For a Class* (RFC, the number of methods potentially invoked in response to calling a method of that class) can reduce the probability of [software bugs](./Software_bug). Following the Law of Demeter can result in a lower RFC. However, the results also suggest that an increase in *Weighted Methods per Class*[[8]](./Law_of_Demeter#cite_note-8) (WMC, the number of methods defined in each class) can increase the probability of software bugs. Following the Law of Demeter can also result in a higher WMC.

 

A [multilayered architecture](./Multilayered_architecture) can be considered to be a systematic mechanism for implementing the Law of Demeter in a software system.
In a layered architecture, code within each [layer](./Layer_(object-oriented_design)) can only make calls to code within the layer and code within the next layer down.
"Layer skipping" would violate the layered architecture.

 

## Disadvantages

 

Although the LoD increases the adaptiveness of a software system, it may result in having to write many [wrapper methods](./Wrapper_method) to propagate calls to components; in some cases, this can add noticeable time and space overhead.[[7]](./Law_of_Demeter#cite_note-Basili-7)[[9]](./Law_of_Demeter#cite_note-BradApp-9)[[10]](./Law_of_Demeter#cite_note-Pragmatic-10)

 

At the method level, the LoD leads to narrow interfaces, giving access to only as much information as it needs to do its job, as each method needs to know about a small set of methods of closely related objects.[[11]](./Law_of_Demeter#cite_note-11) On the other hand, at the class level, if the LoD is not used correctly, wide (i.e., enlarged) interfaces may be developed that require introducing many auxiliary methods.[[9]](./Law_of_Demeter#cite_note-BradApp-9)[[10]](./Law_of_Demeter#cite_note-Pragmatic-10) This is due to poor design rather than a consequence of the LoD per se. If a wrapper method is being used, it means that the object being called through the wrapper should have been a dependency in the calling class.

 

One proposed solution to the problem of enlarged class interfaces is the [aspect-oriented](./Aspect-oriented_programming) approach,[[12]](./Law_of_Demeter#cite_note-AOP-Programming-12) where the behavior of the method is specified as an aspect at a high level of abstraction. The wide interfaces are managed through a language that specifies implementations. Both the traversal strategy and the adaptive visitor use only a minimal set of classes that participate in the operation, and the information about the connections between these classes is abstracted out.

 

## See also

 
- [Facade pattern](./Facade_pattern)
- [Principle of least astonishment](./Principle_of_least_astonishment)
- [Single-responsibility principle](./Single-responsibility_principle)

 

## References

 
1. [↑](./Law_of_Demeter#cite_ref-1) [Lieberherr, K.J.](./Karl_Lieberherr); Holland, I.M. (September 1989). ["Assuring good style for object-oriented programs"](https://dx.doi.org/10.1109/52.35588). *IEEE Software*. **6** (5): 38–48. [doi](./Doi_(identifier)):[10.1109/52.35588](https://doi.org/10.1109%2F52.35588). [ISSN](./ISSN_(identifier)) [0740-7459](https://search.worldcat.org/issn/0740-7459). [S2CID](./S2CID_(identifier)) [12651917](https://api.semanticscholar.org/CorpusID:12651917).
2. [↑](./Law_of_Demeter#cite_ref-2) Macedo, Emerson. ["README.markdown: Demeter"](https://github.com/emerleite/demeter). GitHub. Retrieved 2012-07-05.
3. [↑](./Law_of_Demeter#cite_ref-3) ["Law of Demeter: Principle of Least Knowledge"](https://www.khoury.northeastern.edu/home/lieber/LoD.html). *www.khoury.northeastern.edu*. Retrieved 2024-11-07.
4. [↑](./Law_of_Demeter#cite_ref-4) ["The Demeter Project - What is Demeter?"](http://ccs.neu.edu/home/lieber/what-is-demeter.html).
5. [↑](./Law_of_Demeter#cite_ref-5) Bock, David. ["The Paperboy, The Wallet, and The Law Of Demeter"](http://www.ccs.neu.edu/research/demeter/demeter-method/LawOfDemeter/paper-boy/demeter.pdf) (PDF). College of Computer and Information Science, Northeastern University. p. 5. Retrieved 2012-07-05.
6. [↑](./Law_of_Demeter#cite_ref-6) Metz, Sandi (2019). *Practical Object-Ortiented Design: An Agile Primer Using Ruby* (Second ed.). Addison-Wesley. p. 81. [ISBN](./ISBN_(identifier)) [978-0134456478](./Special:BookSources/978-0134456478). [LCCN](./LCCN_(identifier)) [2018939833](https://lccn.loc.gov/2018939833).
7. [1](./Law_of_Demeter#cite_ref-Basili_7-0) [2](./Law_of_Demeter#cite_ref-Basili_7-1) Basili, Victor; Briand, L.; Melo, W. L. (October 1996). ["A Validation of Object-Oriented Design Metrics as Quality Indicators"](http://drum.lib.umd.edu/bitstream/1903/715/2/CS-TR-3443.pdf) (PDF). *IEEE Transactions on Software Engineering*. **22** (10): 751–761. [doi](./Doi_(identifier)):[10.1109/32.544352](https://doi.org/10.1109%2F32.544352). [hdl](./Hdl_(identifier)):[1903/715](https://hdl.handle.net/1903%2F715). As expected, the larger the WMC, the larger the probability of fault detection.
8. [↑](./Law_of_Demeter#cite_ref-8) ["Weighted Methods per Class - Maisqual Wiki"](https://maisqual.squoring.com/wiki/index.php/Weighted_Methods_per_Class). *maisqual.squoring.com*. Retrieved 2018-09-20.
9. [1](./Law_of_Demeter#cite_ref-BradApp_9-0) [2](./Law_of_Demeter#cite_ref-BradApp_9-1) Appleton, Brad. ["Introducing Demeter and its Laws"](http://www.bradapp.com/docs/demeter-intro.html). Retrieved 6 July 2013. A side-effect of this is that if you conform to LoD, while it may quite increase the maintainability and "adaptiveness" of your software system, you also end up having to write lots of little wrapper methods to propagate methods calls to its components (which can add noticeable time and space overhead).
10. [1](./Law_of_Demeter#cite_ref-Pragmatic_10-0) [2](./Law_of_Demeter#cite_ref-Pragmatic_10-1) ["Tell, Don't Ask"](https://web.archive.org/web/20130721012225/http://pragprog.com/articles/tell-dont-ask). The Pragmatic Programmers, LLC. Archived from [the original](http://pragprog.com/articles/tell-dont-ask) on 21 July 2013. Retrieved 6 July 2013. The disadvantage, of course, is that you end up writing many small wrapper methods that do very little but delegate container traversal and such. The cost tradeoff is between that inefficiency and higher class coupling.
11. [↑](./Law_of_Demeter#cite_ref-11) Lieberherr, K.; Holland, I.; Riel, A. (1988). ["Object-Oriented Programming: An Objective Sense of Style"](http://www.ccs.neu.edu/research/demeter/papers/law-of-demeter/oopsla88-law-of-demeter.pdf) (PDF). In Meyrowitz, Norman (ed.). *Conference proceedings on Object-oriented programming systems, languages and applications (OOPSLA '88)*. ACM. pp. 323–334. [doi](./Doi_(identifier)):[10.1145/62083.62113](https://doi.org/10.1145%2F62083.62113). [ISBN](./ISBN_(identifier)) [978-0897912846](./Special:BookSources/978-0897912846). [S2CID](./S2CID_(identifier)) [562521](https://api.semanticscholar.org/CorpusID:562521). Retrieved 2012-07-05. Easier software maintenance, less coupling between your methods, better information hiding, narrower interfaces, methods which are easier to reuse, and easier correct.ness proofs using structural induction.
12. [↑](./Law_of_Demeter#cite_ref-AOP-Programming_12-0) Lieberherr, Karl; Orleans, Doug; Ovlinger, Johan (October 2001). "Aspect-oriented programming with adaptive methods". *Commun. ACM*. **44** (10): 39–40. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.192.6403](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.192.6403). [doi](./Doi_(identifier)):[10.1145/383845.383855](https://doi.org/10.1145%2F383845.383855). [S2CID](./S2CID_(identifier)) [2792493](https://api.semanticscholar.org/CorpusID:2792493). An adaptive method encapsulates the behavior of an operation into one place, thus avoiding the scattering problem, but also abstracts over the class structure, thus avoiding the tangling problem as well.

 

## Further reading

  
- [Lieberherr, Karl](./Karl_Lieberherr); Holland, I. (September 1989). "Assuring good style for object-oriented programs". *IEEE Software*. **6** (5): 38–48. [doi](./Doi_(identifier)):[10.1109/52.35588](https://doi.org/10.1109%2F52.35588). [S2CID](./S2CID_(identifier)) [12651917](https://api.semanticscholar.org/CorpusID:12651917).
- Lieberherr, Karl J. (1995). [*Adaptive Object-Oriented Software: The Demeter Method with Propagation Patterns*](https://archive.org/details/adaptiveobjector0000lieb). PWS Publishing Company. [ISBN](./ISBN_(identifier)) [978-0534946029](./Special:BookSources/978-0534946029).
- Hunt, Andrew; Thomas, David (2002). ["5. Bend, or Break § The Law of Demeter for Functions"](https://books.google.com/books?id=5wBQEp6ruIAC&pg=PA140). *The Pragmatic Programmer: From Journeyman to Master*. Addison-Wesley. pp. 140–1. [ISBN](./ISBN_(identifier)) [978-0-13-211917-7](./Special:BookSources/978-0-13-211917-7).
- [Larman, Craig](./Craig_Larman) (2005). *Applying UML and Patterns* (3rd ed.). Prentice Hall. pp. 430–2. (from this book, "Law of Demeter" is also known as "Don't talk to strangers")
- [McConnell, Steve](./Steve_McConnell) (2004). [*Code Complete*](https://archive.org/details/codecomplete0000mcco) (2nd ed.). Microsoft Press. pp. [150](https://archive.org/details/codecomplete0000mcco/page/150). [ISBN](./ISBN_(identifier)) [9780735619678](./Special:BookSources/9780735619678).
- Palermo, Jeffrey; Scheirman, Ben; Bogard, Jimmy (2009). *ASP.NET MVC in Action*. Manning Publications. p. 14.

  

## External links

 
- [Law of Demeter (LoD)](http://www.ccs.neu.edu/research/demeter/demeter-method/LawOfDemeter/general-formulation.html)
- ["Object-Oriented Programming: An Objective Sense of Style" (OOPSLA '88 Proceedings) (PDF)](http://www.ccs.neu.edu/research/demeter/papers/law-of-demeter/oopsla88-law-of-demeter.pdf)
- [The Paperboy, The Wallet, and The Law Of Demeter (PDF)](http://www.ccs.neu.edu/research/demeter/demeter-method/LawOfDemeter/paper-boy/demeter.pdf)
- [Phil Haack: "The Law of Demeter is not a Dot Counting Exercise"](http://haacked.com/archive/2009/07/14/law-of-demeter-dot-counting.aspx)
- [Lieber: "Law of Demeter: Principle of Least Knowledge"](http://www.ccs.neu.edu/home/lieber/LoD.html)
- ["Adaptive Object-Oriented Software, The Demeter Method"](http://www.ccs.neu.edu/research/demeter/biblio/dem-book.html)
- [The Demeter Project —- What is Demeter?](http://ccs.neu.edu/home/lieber/what-is-demeter.html)