---
source: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
fetched: 2026-06-19
---

Degree to which elements within a module belong together 

In [computer programming](./Computer_programming), **cohesion** refers to the *degree to which the elements inside a [module](./Module_(programming)) belong together*.[[1]](./Cohesion_(computer_science)#cite_note-Yourdon_1979-1) In one sense, it is a measure of the strength of relationship between the [methods](./Method_(computer_programming)) and data of a [class](./Class_(programming)) and some unifying purpose or concept served by that class. In another sense, it is a measure of the strength of relationship between the class's methods and data.

 

Cohesion is an [ordinal](./Level_of_measurement#Ordinal_scale) type of measurement and is usually described as “high cohesion” or “low cohesion”. Modules with high cohesion tend to be preferable, because high cohesion is associated with several desirable software traits including [robustness](./Robustness_(computer_science)), reliability, [reusability](./Reusability), and understandability. In contrast, low cohesion is associated with undesirable traits such as being difficult to maintain, test, reuse, or understand.

 

Cohesion is often contrasted with [coupling](./Coupling_(computer_science)). High cohesion often correlates with [loose coupling](./Loose_coupling), and vice versa.[[2]](./Cohesion_(computer_science)#cite_note-Ingeno_2018-2) The [software metrics](./Software_metric) of coupling and cohesion were invented by [Larry Constantine](./Larry_Constantine) in the late 1960s as part of [Structured Design](./Structured_Design), based on characteristics of “good” programming practices that reduced maintenance and modification costs. Structured Design, cohesion and coupling were published in the article *Stevens, Myers & Constantine* (1974)[[3]](./Cohesion_(computer_science)#cite_note-Stevens_1974-3) and the book *Yourdon & Constantine* (1979).[[1]](./Cohesion_(computer_science)#cite_note-Yourdon_1979-1) The latter two subsequently became standard terms in [software engineering](./Software_engineering).

 

## High cohesion

 
|  | This sectionneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sourcesin this section. Unsourced material may be challenged and removed.(May 2023)(Learn how and when to remove this message) |
| --- | --- |

 

In [object-oriented programming](./Object-oriented_programming), a class is said to have high cohesion if the methods that serve the class are similar in many aspects.[[4]](./Cohesion_(computer_science)#cite_note-Marsic_2012-4) In a highly cohesive system, code readability and [reusability](./Reusability) is increased, while complexity is kept manageable.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/09/CouplingVsCohesion.svg/250px-CouplingVsCohesion.svg.png)](./File:CouplingVsCohesion.svg)Cohesion 

Cohesion is increased if:

 
- The functionalities embedded in a class, accessed through its methods, have much in common.
- Methods carry out a small number of related activities, by *avoiding* [coarsely grained](./Granularity#Data_granularity) or unrelated sets of data.
- Related methods are in the same source file or otherwise grouped together; for example, in separate files but in the same sub-directory/folder.

 

Advantages of high cohesion (or "strong cohesion") are:

 
- Reduced module complexity, with fewer operations.
- Increased system [maintainability](./Maintainability), because logical changes in the domain affect fewer modules, and changes in one module require fewer changes in other modules.
- Increased module reusability, because application developers will find the [component](./Software_component) they need more easily among the cohesive set of operations provided by the module.

 

While in principle a module can have perfect cohesion by only consisting of a single, atomic element – having a single function, for example – in practice complex tasks are not expressible by a single, simple element. Thus a single-element module has an element that is either too complicated to accomplish a task, or too narrow and thus tightly [coupled](./Coupling_(computer_programming)) to other modules. Thus cohesion is balanced with both unit complexity and coupling.

 

## Types of cohesion

 

Cohesion is a qualitative measure, meaning that the source code is examined using a [rubric](./Rubric_(academic)) to determine a classification. Cohesion types, from the worst to the best, are as follows:

 Coincidental cohesion (worst)Coincidental cohesion is when parts of a module are grouped arbitrarily. The only relationship between the parts is that they have been grouped together (e.g., a “Utilities” class). Example:

```
/*
Groups: The function definitions
Parts: The terms on each function
*/
Module A {
  /*
  Implementation of r(x) = 5x + 3
  There is no particular reason to group functions in this way,
  so the module is said to have Coincidental Cohesion.
  */ 
  r(x) = a(x) + b(x) 
  a(x) = 2x + 1
  b(x) = 3x + 2
}

```
 Logical cohesionLogical cohesion is when parts of a module are grouped because they are logically categorized to do the same thing even though they are different by nature (e.g., grouping all mouse and keyboard input handling routines or bundling all models, views, and controllers in separate folders in an [MVC pattern](./Model–view–controller)). Temporal cohesionTemporal cohesion is when parts of a module are grouped according to the time in which they are processed. The parts are processed at a particular time in program execution (e.g., a function that is called after catching an exception that closes open files, creates an error log, and notifies the user). Procedural cohesionProcedural cohesion is when parts of a module are grouped because they always follow a certain sequence of execution (e.g., a function that checks file permissions and then opens the file). Communicational/informational cohesionCommunicational cohesion is when parts of a module are grouped because they operate on the same data (e.g., a module that operates on the same record of information). Sequential cohesionSequential cohesion is when parts of a module are grouped because the output from one part is the input to another part like an assembly line (e.g., a function that reads data from a file and processes the data). Functional cohesion (best)Functional cohesion is when parts of a module are grouped because they all contribute to a single well-defined task of the module (e.g., [Lexical analysis](./Lexical_analysis) of an XML string). Example:

```
/*
Groups: The function definitions
Parts: The terms on each function
*/
Module A {
  /*
  Implementation of arithmetic operations
  This module is said to have functional cohesion because 
  there is an intention to group simple arithmetic operations
  on it. 
  */
  a(x, y) = x + y
  b(x, y) = x * y
}

Module B {
  /*
  Module B: Implements r(x) = 5x + 3
  This module can be said to have atomic cohesion. The whole
  system (with Modules A and B as parts) can also be said to have functional
  cohesion, because its parts both have specific separate purposes. 
  */
  r(x) = [Module A].a([Module A].b(5, x), 3)
}

```
 Perfect cohesion (atomic)Example.

```
/*
Groups: The function definitions
Parts: The terms on each function
*/
Module A {
  /* 
  Implementation of r(x) = 2x + 1 + 3x + 2
  It's said to have perfect cohesion because it cannot be reduced any more than that.
  */
  r(x) = 2x + 1 + 3x + 2
}

```
 

Although cohesion is a ranking type of scale, the ranks do not indicate a steady progression of improved cohesion. Studies by [Larry Constantine](./Larry_Constantine), [Edward Yourdon](./Edward_Yourdon), and [Steve McConnell](./Steve_McConnell)[[5]](./Cohesion_(computer_science)#cite_note-McConnell-5) indicate that the first two types of cohesion are inferior, communicational and sequential cohesion are very good, and functional cohesion is superior.

 

## See also

 
- [Coupling (computer science)](./Coupling_(computer_science))
- [List of object-oriented programming terms](./List_of_object-oriented_programming_terms)
- [Static code analysis](./Static_code_analysis)

 

## References

 
1. [1](./Cohesion_(computer_science)#cite_ref-Yourdon_1979_1-0) [2](./Cohesion_(computer_science)#cite_ref-Yourdon_1979_1-1) [Yourdon, Edward](./Edward_Yourdon); [Constantine, Larry LeRoy](./Larry_LeRoy_Constantine) (1979) [1975]. *Structured Design: Fundamentals of a Discipline of Computer Program and Systems Design*. Yourdon Press. [Bibcode](./Bibcode_(identifier)):[1979sdfd.book.....Y](https://ui.adsabs.harvard.edu/abs/1979sdfd.book.....Y). [ISBN](./ISBN_(identifier)) [978-0-13-854471-3](./Special:BookSources/978-0-13-854471-3).
2. [↑](./Cohesion_(computer_science)#cite_ref-Ingeno_2018_2-0) Ingeno, Joseph (2018). *Software Architect's Handbook*. [Packt Publishing](./Packt_Publishing). p. 175. [ISBN](./ISBN_(identifier)) [978-178862406-0](./Special:BookSources/978-178862406-0).
3. [↑](./Cohesion_(computer_science)#cite_ref-Stevens_1974_3-0) [Stevens, Wayne P.](./Wayne_Stevens_(software_engineer)); [Myers, Glenford J.](./Glenford_J._Myers); [Constantine, Larry LeRoy](./Larry_LeRoy_Constantine) (June 1974). "Structured design". *[IBM Systems Journal](./IBM_Systems_Journal)*. **13** (2): 115–139. [doi](./Doi_(identifier)):[10.1147/sj.132.0115](https://doi.org/10.1147%2Fsj.132.0115).
4. [↑](./Cohesion_(computer_science)#cite_ref-Marsic_2012_4-0) Marsic, Ivan (2012). *Software Engineering*. [Rutgers University](./Rutgers_University).
5. [↑](./Cohesion_(computer_science)#cite_ref-McConnell_5-0) [McConnell, Steve](./Steve_McConnell) (June 2004) [1993]. [*Code Complete*](./Code_Complete) (2 ed.). Pearson Education. pp. [168-171](https://archive.org/details/codecomplete0000mcco/page/168). [ISBN](./ISBN_(identifier)) [978-0-7356-1967-8](./Special:BookSources/978-0-7356-1967-8).

 

## External links

 
- [Definitions of Cohesion metrics](http://www.ndepend.com/Metrics.aspx#RelationalCohesion)
- [Cohesion metrics](http://www.aivosto.com/project/help/pm-oo-cohesion.html)
- [Measuring Cohesion in Python](https://github.com/mschwager/cohesion)