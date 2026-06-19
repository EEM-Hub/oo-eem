---
source: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
fetched: 2026-06-19
---

Software design pattern [![](//upload.wikimedia.org/wikipedia/commons/thumb/a/a0/MVC-Process.svg/250px-MVC-Process.svg.png)](./File:MVC-Process.svg)Diagram of interactions in MVC's Smalltalk-80 interpretation[*[contradictory](./Category:All_self-contradictory_articles)*] 

**Model–view–controller** (**MVC**) is a software [architectural pattern](./Architectural_pattern)[[1]](./Model–view–controller#cite_note-1) commonly used for developing [user interfaces](./User_interface) that divides the related program logic into three interconnected elements. These elements are:

 
- the **[model](./Model)**, the internal representations of information
- the **view**, the interface that presents information to and accepts it from the user[*[contradictory](./Category:All_self-contradictory_articles)*]
- the **controller**, the software linking the two.[[2]](./Model–view–controller#cite_note-Reenskaug_and_Coplien,_Artima,_2009-2)[[3]](./Model–view–controller#cite_note-3)

 

Traditionally used for desktop [graphical user interfaces](./Graphical_user_interface) (GUIs), this pattern became popular for designing [web applications](./Web_application).[[4]](./Model–view–controller#cite_note-4) Popular programming languages have MVC frameworks that facilitate the implementation of the pattern.

 

 

 

## History

 

One of the seminal insights in the early development of graphical user interfaces, MVC became one of the first approaches to describe and implement software constructs in terms of their [responsibilities](./Single_responsibility_principle).[[5]](./Model–view–controller#cite_note-5)

 

[Trygve Reenskaug](./Trygve_Reenskaug) created MVC while working on [Smalltalk](./Smalltalk)-79 as a visiting scientist at the Xerox [Palo Alto Research Center](./PARC_(company)) (PARC) in the late 1970s.[[6]](./Model–view–controller#cite_note-page_trygver-6)[[7]](./Model–view–controller#cite_note-notes1-7)[[8]](./Model–view–controller#cite_note-FowlerPoEAA-8): 330  He wanted a pattern that could be used to structure any program where users interact with a large, convoluted [data set](./Data_set). His design initially had four parts: [Model](./Model), view, thing, and editor. After discussing it with the other Smalltalk [developers](./Software_development), he and the rest of the group settled on model, view, and controller instead.[[6]](./Model–view–controller#cite_note-page_trygver-6)

 

In their final design, a model represents some part of the program purely and intuitively. A view is a visual representation of a model, retrieving data from the model to display to the user and passing requests back and forth between the user and the model. A controller is an organizational part of the user interface that lays out and coordinates multiple Views on the screen, and which receives user input and sends the appropriate messages to its underlying Views. This design also includes an Editor as a specialized kind of controller used to modify a particular view, and which is created through that view.[[6]](./Model–view–controller#cite_note-page_trygver-6)

 

Smalltalk-80 supports a version of MVC that evolved from this one.[[6]](./Model–view–controller#cite_note-page_trygver-6) It provides abstract `view` and `controller` [classes](./Class_(programming)) as well as various concrete subclasses of each that represent different generic [widgets](./Software_widget). In this scheme, a `View` represents some way of displaying information to the user, and a `controller` represents some way for the user to interact with a `view`. A `view` is also coupled to a model object, but the structure of that object is left up to the application [programmer](./Programmer). The Smalltalk-80 environment also includes an "MVC Inspector", a development tool for viewing the structure of a given model, view, and controller side-by-side.[[9]](./Model–view–controller#cite_note-smalltalk_redbook-9)

 

In 1988, an article in *[The Journal of Object Technology](./The_Journal_of_Object_Technology)* (JOT) by two ex-PARC employees presented MVC as a general "[programming paradigm](./Programming_paradigm) and methodology" for Smalltalk-80 developers. However, their scheme differed from both Reenskaug et al.'s and that presented by the Smalltalk-80 reference books. They defined a view as covering any graphical concern, with a controller being a more abstract, generally invisible object that receives user input and interacts with one or many views and only one model.[[10]](./Model–view–controller#cite_note-art1-10)

 

The MVC pattern subsequently evolved,[[11]](./Model–view–controller#cite_note-Fowler-11) giving rise to variants such as [hierarchical model–view–controller](./Hierarchical_model–view–controller) (HMVC), [model–view–adapter](./Model–view–adapter) (MVA), [model–view–presenter](./Model–view–presenter) (MVP), [model–view–viewmodel](./Model–view–viewmodel) (MVVM), and others that adapted MVC to different contexts.

 

The use of the MVC pattern in [web applications](./Web_application) grew after the introduction of [NeXT](./NeXT)'s [WebObjects](./WebObjects) in 1996, which was originally written in [Objective-C](./Objective-C) (that borrowed heavily from Smalltalk) and helped enforce MVC principles. Later, the MVC pattern became popular with Java developers when WebObjects was ported to [Java](./Java_(programming_language)). Later frameworks for Java, such as [Spring](./Spring_Framework) (released in October 2002), continued the strong bond between Java and MVC.

 

In 2003, [Martin Fowler](./Martin_Fowler_(software_engineer)) published *Patterns of Enterprise Application Architecture*, which presented MVC as a pattern where an "input controller" receives a request, sends the appropriate messages to a model object, takes a response from the model object, and passes the response to the appropriate view for display.[[8]](./Model–view–controller#cite_note-FowlerPoEAA-8): 56  This is close to the approach taken by the [Ruby on Rails](./Ruby_on_Rails) web application framework (August 2004), which has the client send requests to the server via an in-[browser](./Web_browser) view, these requests are handled by a controller on the server, and the controller communicates with the appropriate model objects.[[12]](./Model–view–controller#cite_note-12) The [Django](./Django_(web_framework)) framework (July 2005, for [Python](./Python_(programming_language))) put forward a similar "model-template-view" (MTV) take on the pattern, in which a view retrieves data from models and passes it to templates for display.[[13]](./Model–view–controller#cite_note-13) Both Rails and Django debuted with a strong emphasis on rapid deployment, which increased MVC's popularity outside the traditional enterprise environment in which it has long been popular.

 

## Components

 

### Model

 See also: [Data model](./Data_model) 

The central component of the pattern. It is the application's dynamic [data structure](./Data_structure), independent of the user interface.[[14]](./Model–view–controller#cite_note-14) It directly manages the data, logic and rules of the application. In Smalltalk-80, the design of a model type is left entirely to the programmer.[[15]](./Model–view–controller#cite_note-15) With WebObjects, Rails, and Django, a model type typically [represents](./Object–relational_mapping) a table in the application's [database](./Database).[[16]](./Model–view–controller#cite_note-16)[[17]](./Model–view–controller#cite_note-17)[[18]](./Model–view–controller#cite_note-18) The model is essential for keeping the data organized and consistent. It ensures that the application's data behaves according to the defined rules and logic.

 

### View

 

Any representation of information such as a [chart](./Chart), diagram or table. Multiple views of the same information are possible, such as a bar chart for management and a tabular view for [accountants](./Accountant).

 

In Smalltalk-80, a view is just a visual representation of a model, and does not handle user input.[[19]](./Model–view–controller#cite_note-19) With WebObjects, a view represents a complete user interface element such as a menu or button, and does receive input from the user.[[20]](./Model–view–controller#cite_note-20) In both Smalltalk-80 and WebObjects, however, views are meant to be general-purpose and [composable](./Composability).[[21]](./Model–view–controller#cite_note-21)[[22]](./Model–view–controller#cite_note-22)

 

With Rails and Django, the role of the view is played by [HTML](./HTML) templates, so in their scheme a view specifies an in-browser user interface rather than representing a user interface widget directly.[[23]](./Model–view–controller#cite_note-23)[[24]](./Model–view–controller#cite_note-24) (Django opts to call this kind of object a "template" in light of this.[[25]](./Model–view–controller#cite_note-25)) This approach puts relatively less emphasis on small, composable views; a typical Rails view has a [one-to-one relationship](./Cardinality_(data_modeling)) with a controller action.[[26]](./Model–view–controller#cite_note-26)

 

Smalltalk-80 views communicate with both a model and a controller,[[27]](./Model–view–controller#cite_note-27) whereas with WebObjects, a view talks only to a controller, which then talks to a model.[[28]](./Model–view–controller#cite_note-28) With Rails and Django, a view/template is used by a controller/view when preparing a response to the client.[[29]](./Model–view–controller#cite_note-29)[[30]](./Model–view–controller#cite_note-djangoviewtemplfaq-30)

 

### Controller

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/UML_class_diagram_MVC_controller.svg/250px-UML_class_diagram_MVC_controller.svg.png)](./File:UML_class_diagram_MVC_controller.svg)UML class diagram of an example controller in MVC architecture 

Accepts input and converts it to commands for the model or view.[[31]](./Model–view–controller#cite_note-31)

 

A Smalltalk-80 controller handles user input events, such as button presses or mouse movement.[[32]](./Model–view–controller#cite_note-32) At any given time, each controller has one associated view and model, although one model object may hear from many different controllers. Only one controller, the "active" controller, receives user input at any given time; a global [window manager](./Window_manager) object is responsible for setting the current active controller. If user input prompts a change in a model, the controller will signal the model to change, but the model is then responsible for telling its views to update.[[33]](./Model–view–controller#cite_note-33)

 

In WebObjects, the views handle user input, and the controller mediates between the views and the models. There may be only one controller per application, or one controller per window. Much of the application-specific logic is found in the controller.[[34]](./Model–view–controller#cite_note-34)

 

In Rails, requests arriving at the on-server application from the client are sent to a "router", which maps the request to a specific method of a specific controller. Within that method, the controller interacts with the request data and any relevant model objects and prepares a response using a view. Conventionally, each view has an associated controller; for example, if the application had a `client` view, it would typically have an associated `Clients` controller as well. However, developers are free to make other kinds of controllers if they wish.[[35]](./Model–view–controller#cite_note-35)

 

Django calls the object playing this role a "view" instead of a controller.[[30]](./Model–view–controller#cite_note-djangoviewtemplfaq-30) A Django view is a function that receives a web request and returns a web response. It may use templates to create the response.[[36]](./Model–view–controller#cite_note-36)

 

## Interactions

 

In addition to dividing the application into a model, a view and a controller component, the MVC [design pattern](./Software_design_pattern) defines the interactions between these three components :[[37]](./Model–view–controller#cite_note-posa-37)

 
- The model is responsible for managing the data of the application. It receives user input from the controller.
- The view renders presentation of the model in a particular format.
- The controller responds to the user input and performs interactions on the data model objects. The controller receives the input, optionally validates it and then passes the input to the model.

 

As with other software patterns, MVC expresses the "core of the solution" to a problem while allowing it to be adapted for each system.[[38]](./Model–view–controller#cite_note-gof-38) Particular MVC designs can vary significantly from the traditional description here.[[39]](./Model–view–controller#cite_note-39)

 

## Motivation

 

As [Alan Kay](./Alan_Kay) wrote in 2003, the original motivation behind the MVC was to allow creation of a graphical interface for any object.[[40]](./Model–view–controller#cite_note-:0-40) That was outlined in detail in Richard Pawson's book *[Naked Objects](./Naked_objects)*.[[40]](./Model–view–controller#cite_note-:0-40)

 

Trygve Reenskaug, originator of MVC at PARC, has written that "MVC was conceived as a general solution to the problem of users controlling a large and complex data set."[[6]](./Model–view–controller#cite_note-page_trygver-6)

 

In their 1991 guide *Inside Smalltalk*, [Carleton University](./Carleton_University) computer science professors Wilf LaLonde and John Pugh described the advantages of Smalltalk-80-style MVC as:

 
- independence of presentation and data, e.g. multiple views on one model simultaneously,
- composable presentation widgets, e.g. one view used as a subview of another,
- switchable input modes, by swapping one controller out for another during [runtime](./Software_execution), and
- independence of input and output processing, via the [separate responsibilities](./Separation_of_concerns) of controllers and views.[[41]](./Model–view–controller#cite_note-41)

 

## Use in web applications

 

Although originally developed for [desktop computing](./Desktop_computer), MVC has been widely adopted as a design for [World Wide Web](./World_Wide_Web) applications in major [programming languages](./Programming_language). Several [web frameworks](./Web_framework) have been created that enforce the pattern. These [software frameworks](./Software_framework) vary in their interpretations, mainly in the way that the MVC responsibilities are divided between the [client and server](./Client–server_model).[[42]](./Model–view–controller#cite_note-leff-42) Early MVC frameworks took a [thin client](./Thin_client) approach that placed almost the entire model, view and controller logic on the server. In this approach, the client sends [hyperlink](./Hyperlink) requests or [form](./Form_(web)) submissions to the controller and then receives a complete and updated [web page](./Web_page) (or other document) from the view; the model exists entirely on the server.[[42]](./Model–view–controller#cite_note-leff-42) Later frameworks have allowed the MVC components to execute partly on the client, using [Ajax](./Ajax_(programming)) to synchronize data.

 

## See also

  
- [Action–domain–responder](./Action–domain–responder)
- [Bistro Framework](./Bistro_Framework)
- [Entity–control–boundary pattern](./Entity–control–boundary)
- [Hierarchical model–view–controller](./Hierarchical_model–view–controller)
- [Model–view–adapter](./Model–view–adapter)
- [Model–view–presenter](./Model–view–presenter)
- [Model–view–viewmodel](./Model–view–viewmodel)
- [Multitier architecture](./Multitier_architecture)
- [Observer pattern](./Observer_pattern)
- [Presentation–abstraction–control](./Presentation–abstraction–control)
- [Separation of concerns](./Separation_of_concerns)
- [Strategy pattern](./Strategy_pattern)

 

## References

  
1. [↑](./Model–view–controller#cite_ref-1) ["The Principles of Clean Architecture by Uncle Bob Martin"](https://www.youtube.com/watch?v=o_TH-Y78tt4&t=1667). *[YouTube](./YouTube)*. 15 December 2015.
2. [↑](./Model–view–controller#cite_ref-Reenskaug_and_Coplien,_Artima,_2009_2-0) Reenskaug, Trygve; Coplien, James O. (20 March 2009). ["The DCI Architecture: A New Vision of Object-Oriented Programming"](https://web.archive.org/web/20090323032904/https://www.artima.com/articles/dci_vision.html). *Artima Developer*. Archived from [the original](https://www.artima.com/articles/dci_vision.html) on 23 March 2009. Retrieved 3 August 2019. More deeply, the framework exists to separate the representation of information from user interaction.
3. [↑](./Model–view–controller#cite_ref-3) Burbeck (1992): "... the user input, the modeling of the external world, and the visual feedback to the user are explicitly separated and handled by three types of object."
4. [↑](./Model–view–controller#cite_ref-4) Davis, Ian. ["What Are The Benefits of MVC?"](http://blog.iandavis.com/2008/12/what-are-the-benefits-of-mvc/). *Internet Alchemy*. Retrieved 2016-11-29.
5. [↑](./Model–view–controller#cite_ref-5) [Model–View–Controller History](http://c2.com/cgi/wiki?ModelViewControllerHistory). C2.com (2012-05-11). Retrieved on 2013-12-09.
6. [1](./Model–view–controller#cite_ref-page_trygver_6-0) [2](./Model–view–controller#cite_ref-page_trygver_6-1) [3](./Model–view–controller#cite_ref-page_trygver_6-2) [4](./Model–view–controller#cite_ref-page_trygver_6-3) [5](./Model–view–controller#cite_ref-page_trygver_6-4) [Notes and Historical documents](http://heim.ifi.uio.no/~trygver/themes/mvc/mvc-index.html) from Trygve Reenskaug, inventor of MVC.
7. [↑](./Model–view–controller#cite_ref-notes1_7-0) "A note on DynaBook requirements", Trygve Reenskaug, 22 March 1979, [SysReq.pdf](https://wayback.archive-it.org/10370/20180425072145/http://folk.uio.no/trygver/1979/sysreq/SysReq.pdf).
8. [1](./Model–view–controller#cite_ref-FowlerPoEAA_8-0) [2](./Model–view–controller#cite_ref-FowlerPoEAA_8-1) [Fowler, Martin](./Martin_Fowler_(software_engineer)) (2003). *Patterns of Enterprise Application Architecture*. Pearson Education, Inc. [ISBN](./ISBN_(identifier)) [0-321-12742-0](./Special:BookSources/0-321-12742-0).
9. [↑](./Model–view–controller#cite_ref-smalltalk_redbook_9-0) [Goldberg, Adele](./Adele_Goldberg_(computer_scientist)) (1984). *Smalltalk-80: The Interactive Programming Environment*. Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-11372-4](./Special:BookSources/0-201-11372-4).
10. [↑](./Model–view–controller#cite_ref-art1_10-0) Krasner, Glenn E.; Pope, Stephen T. (Aug–Sep 1988). ["A cookbook for using the model–view controller user interface paradigm in Smalltalk-80"](http://dl.acm.org/citation.cfm?id=50757.50759). *[The Journal of Object Technology](./The_Journal_of_Object_Technology)*. **1** (3). SIGS Publications: 26–49. Also published as "[A Description of the Model–View–Controller User Interface Paradigm in the Smalltalk-80 System](https://web.archive.org/web/20100921030808/http://www.itu.dk/courses/VOP/E2005/VOP2005E/8_mvc_krasner_and_pope.pdf)" (Report), ParcPlace Systems; Retrieved 2012-06-05.
11. [↑](./Model–view–controller#cite_ref-Fowler_11-0) [The evolution of MVC and other UI architectures](http://martinfowler.com/eaaDev/uiArchs.html) from Martin Fowler.
12. [↑](./Model–view–controller#cite_ref-12) ["Ruby on Rails Guides"](https://guides.rubyonrails.org/). Retrieved March 19, 2022.
13. [↑](./Model–view–controller#cite_ref-13) ["Django FAQ: Django appears to be a MVC framework, but you call the Controller the "view", and the View the "template". How come you don't use the standard names?"](https://docs.djangoproject.com/en/4.0/faq/general/#django-appears-to-be-a-mvc-framework-but-you-call-the-controller-the-view-and-the-view-the-template-how-come-you-don-t-use-the-standard-names). Retrieved March 19, 2022.
14. [↑](./Model–view–controller#cite_ref-14) Burbeck, Steve (1992) [Applications Programming in Smalltalk-80:How to use Model–View–Controller (MVC)](https://web.archive.org/web/20120729161926/http://st-www.cs.illinois.edu/users/smarch/st-docs/mvc.html)
15. [↑](./Model–view–controller#cite_ref-15) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). U.S.A.: Prentice-Hall Inc. p. 8. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3). The model can be any object without restriction.
16. [↑](./Model–view–controller#cite_ref-16) [*WebObjects System Overview*](https://developer.apple.com/library/archive/documentation/LegacyTechnologies/WebObjects/WebObjects_5/WebObjectsOverview/WebObjectsOverview.pdf) (PDF). Cupertino, CA: Apple Computer, Inc. May 2001. p. 28. In WebObjects, a model establishes and maintains a correspondence between an enterprise object class and data stored in a relational database.
17. [↑](./Model–view–controller#cite_ref-17) ["Active Record Basics"](https://guides.rubyonrails.org/active_record_basics.html). *Rails Guides*. Retrieved October 27, 2022. This will create a `Product` model, mapped to a products table at the database.
18. [↑](./Model–view–controller#cite_ref-18) ["Models"](https://docs.djangoproject.com/en/4.1/topics/db/models/). *Django Documentation*. Retrieved October 27, 2022. Generally, each model maps to a single database table.
19. [↑](./Model–view–controller#cite_ref-19) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). U.S.A.: Prentice-Hall Inc. p. 8. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3). The view is responsible for providing a visual representation of the object.
20. [↑](./Model–view–controller#cite_ref-20) [*WebObjects System Overview*](https://developer.apple.com/library/archive/documentation/LegacyTechnologies/WebObjects/WebObjects_5/WebObjectsOverview/WebObjectsOverview.pdf) (PDF). Cupertino, CA: Apple Computer, Inc. May 2001. p. 28. View objects represent things visible on the user interface (windows, for example, or buttons).
21. [↑](./Model–view–controller#cite_ref-21) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). U.S.A.: Prentice-Hall Inc. p. 8. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3). [MVC] permits views to be used as parts for assembly into larger units; new kinds of views can be constructed using existing views as subviews.
22. [↑](./Model–view–controller#cite_ref-22) [*WebObjects System Overview*](https://developer.apple.com/library/archive/documentation/LegacyTechnologies/WebObjects/WebObjects_5/WebObjectsOverview/WebObjectsOverview.pdf) (PDF). Cupertino, CA: Apple Computer, Inc. May 2001. p. 28. View objects tend to be very reusable and so provide consistency between applications.
23. [↑](./Model–view–controller#cite_ref-23) ["Action View Overview"](https://guides.rubyonrails.org/action_view_overview.html). *Rails Guides*. Retrieved October 27, 2022. Action View templates are written using embedded Ruby in tags mingled with HTML.
24. [↑](./Model–view–controller#cite_ref-24) ["Templates"](https://docs.djangoproject.com/en/4.1/topics/templates/). *Django Documentation*. Retrieved October 27, 2022. A template contains the static parts of the desired HTML output as well as some special syntax describing how dynamic content will be inserted.
25. [↑](./Model–view–controller#cite_ref-25) ["Django FAQ: Django appears to be a MVC framework, but you call the Controller the "view", and the View the "template". How come you don't use the standard names?"](https://docs.djangoproject.com/en/4.0/faq/general/#django-appears-to-be-a-mvc-framework-but-you-call-the-controller-the-view-and-the-view-the-template-how-come-you-don-t-use-the-standard-names). Retrieved October 27, 2022.
26. [↑](./Model–view–controller#cite_ref-26) ["Action View Overview"](https://guides.rubyonrails.org/action_view_overview.html). *Rails Guides*. Retrieved October 27, 2022. Typically, the views share their name with the associated controller action...
27. [↑](./Model–view–controller#cite_ref-27) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). U.S.A.: Prentice-Hall Inc. p. 9. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3). ...the view knows explicitly about the model and the controller.
28. [↑](./Model–view–controller#cite_ref-28) [*WebObjects System Overview*](https://developer.apple.com/library/archive/documentation/LegacyTechnologies/WebObjects/WebObjects_5/WebObjectsOverview/WebObjectsOverview.pdf) (PDF). Cupertino, CA: Apple Computer, Inc. May 2001. p. 28. Acting as a mediator between Model objects and View objects in an application is a Controller object.
29. [↑](./Model–view–controller#cite_ref-29) ["Action View Overview"](https://guides.rubyonrails.org/action_view_overview.html). *Rails Guides*. Retrieved October 27, 2022. In Rails, web requests are handled by action controller and action view. Typically, action controller is concerned with communicating with the database and performing CRUD actions where necessary. Action View is then responsible for compiling the response.
30. [1](./Model–view–controller#cite_ref-djangoviewtemplfaq_30-0) [2](./Model–view–controller#cite_ref-djangoviewtemplfaq_30-1) ["Django FAQ: Django appears to be a MVC framework, but you call the Controller the "view", and the View the "template". How come you don't use the standard names?"](https://docs.djangoproject.com/en/4.0/faq/general/#django-appears-to-be-a-mvc-framework-but-you-call-the-controller-the-view-and-the-view-the-template-how-come-you-don-t-use-the-standard-names). Retrieved October 27, 2022. In Django, a 'view' describes which data is presented, but a view normally delegates to a template, which describes how the data is presented.
31. [↑](./Model–view–controller#cite_ref-31) [Simple Example of MVC (Model–View–Controller) Architectural Pattern for Abstraction](http://www.codeproject.com/Articles/25057/Simple-Example-of-MVC-Model-View-Controller-Design)
32. [↑](./Model–view–controller#cite_ref-32) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). U.S.A.: Prentice-Hall Inc. p. 8. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3). The controller is responsible for interfacing between the user and the model/view. It interprets keyboard characters along with mouse movements and clicking.
33. [↑](./Model–view–controller#cite_ref-33) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). U.S.A.: Prentice-Hall Inc. p. 11. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3).
34. [↑](./Model–view–controller#cite_ref-34) [*WebObjects System Overview*](https://developer.apple.com/library/archive/documentation/LegacyTechnologies/WebObjects/WebObjects_5/WebObjectsOverview/WebObjectsOverview.pdf) (PDF). Cupertino, CA: Apple Computer, Inc. May 2001. p. 28.
35. [↑](./Model–view–controller#cite_ref-35) ["Action View Overview"](https://guides.rubyonrails.org/action_view_overview.html). *Rails Guides*. Retrieved October 27, 2022. Typically, the views share their name with the associated controller action...
36. [↑](./Model–view–controller#cite_ref-36) ["Writing views"](https://docs.djangoproject.com/en/4.1/topics/http/views/). *Django Documentation*. Retrieved October 27, 2022.
37. [↑](./Model–view–controller#cite_ref-posa_37-0) Buschmann, Frank (1996) *Pattern-Oriented Software Architecture*.
38. [↑](./Model–view–controller#cite_ref-gof_38-0) Gamma, Erich et al. (1994) *Design Patterns*
39. [↑](./Model–view–controller#cite_ref-39) Moore, Dana et al. (2007) *Professional Rich Internet Applications: Ajax and Beyond*: "Since the origin of MVC, there have been many interpretations of the pattern. The concept has been adapted and applied in very different ways to a wide variety of systems and architectures."
40. [1](./Model–view–controller#cite_ref-:0_40-0) [2](./Model–view–controller#cite_ref-:0_40-1) Alan Kay (23 May 2003). ["is squeak really object oriented ?"](http://lists.squeakfoundation.org/pipermail/squeak-dev/2003-May/058824.html). *Squeak Foundation mailing list*. Retrieved 26 October 2021.
41. [↑](./Model–view–controller#cite_ref-41) LaLonde, Wilf R.; Pugh, John R. (1991). [*Inside Smalltalk*](https://books.google.com/books?id=RRkiAQAAIAAJ). Vol. 2. U.S.A.: Prentice-Hall Inc. pp. 8–9. [ISBN](./ISBN_(identifier)) [0-13-467309-3](./Special:BookSources/0-13-467309-3).
42. [1](./Model–view–controller#cite_ref-leff_42-0) [2](./Model–view–controller#cite_ref-leff_42-1) Leff, Avraham; Rayfield, James T. (September 2001). *Web-Application Development Using the Model/View/Controller Design Pattern*. IEEE Enterprise Distributed Object Computing Conference. pp. 118–127.

 

## Bibliography

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) Wikibooks has a book on the topic of: ***[Computer Science Design Patterns/Model–view–controller](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Model–view–controller)***  
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

 
| vteSmalltalkprogramming language |
| --- |
| Software | ImplementationsMajorAmber°Dolphin Smalltalk°GemStone/SGNU Smalltalk°Smalltalk/XSqueak°Pharo°VisualAgeSmalltalkVisualWorksDialectsF-Script°Little Smalltalk°Newspeak°OMeta/Squeak°Pocket Smalltalk°Self°StepTalk°Strongtalk°Virtual realityplatformsCroquet Project° →Open Cobalt°Graphical user interfacesModel–view–controllerMorphicAIDA/Web°GemStone/SMoose°Seaside° | Implementations | MajorAmber°Dolphin Smalltalk°GemStone/SGNU Smalltalk°Smalltalk/XSqueak°Pharo°VisualAgeSmalltalkVisualWorksDialectsF-Script°Little Smalltalk°Newspeak°OMeta/Squeak°Pocket Smalltalk°Self°StepTalk°Strongtalk° | Major | Amber°Dolphin Smalltalk°GemStone/SGNU Smalltalk°Smalltalk/XSqueak°Pharo°VisualAgeSmalltalkVisualWorks | Dialects | F-Script°Little Smalltalk°Newspeak°OMeta/Squeak°Pocket Smalltalk°Self°StepTalk°Strongtalk° | Virtual realityplatforms | Croquet Project° →Open Cobalt° | Graphical user interfaces | Model–view–controllerMorphic |
| Implementations | MajorAmber°Dolphin Smalltalk°GemStone/SGNU Smalltalk°Smalltalk/XSqueak°Pharo°VisualAgeSmalltalkVisualWorksDialectsF-Script°Little Smalltalk°Newspeak°OMeta/Squeak°Pocket Smalltalk°Self°StepTalk°Strongtalk° | Major | Amber°Dolphin Smalltalk°GemStone/SGNU Smalltalk°Smalltalk/XSqueak°Pharo°VisualAgeSmalltalkVisualWorks | Dialects | F-Script°Little Smalltalk°Newspeak°OMeta/Squeak°Pocket Smalltalk°Self°StepTalk°Strongtalk° |
| Major | Amber°Dolphin Smalltalk°GemStone/SGNU Smalltalk°Smalltalk/XSqueak°Pharo°VisualAgeSmalltalkVisualWorks |
| Dialects | F-Script°Little Smalltalk°Newspeak°OMeta/Squeak°Pocket Smalltalk°Self°StepTalk°Strongtalk° |
| Virtual realityplatforms | Croquet Project° →Open Cobalt° |
| Graphical user interfaces | Model–view–controllerMorphic |
| Workstation | Xerox Alto |
| Community | BusinessCincom SystemsGemstoneIBMObject ArtsXerox PARCPeopleDesignersL. Peter DeutschAdele GoldbergDan IngallsTed KaehlerAlan KayDiana MerryDavid UngarScott WallaceLars BakGilad BrachaUrs HölzleJulian LombardiMark P. McCahillAndreas RaabDavid P. ReedTrygve ReenskaugDavid SmithLarry Tesler | Business | Cincom SystemsGemstoneIBMObject ArtsXerox PARC | People | DesignersL. Peter DeutschAdele GoldbergDan IngallsTed KaehlerAlan KayDiana MerryDavid UngarScott WallaceLars BakGilad BrachaUrs HölzleJulian LombardiMark P. McCahillAndreas RaabDavid P. ReedTrygve ReenskaugDavid SmithLarry Tesler | Designers | L. Peter DeutschAdele GoldbergDan IngallsTed KaehlerAlan KayDiana MerryDavid UngarScott Wallace |
| Business | Cincom SystemsGemstoneIBMObject ArtsXerox PARC |
| People | DesignersL. Peter DeutschAdele GoldbergDan IngallsTed KaehlerAlan KayDiana MerryDavid UngarScott WallaceLars BakGilad BrachaUrs HölzleJulian LombardiMark P. McCahillAndreas RaabDavid P. ReedTrygve ReenskaugDavid SmithLarry Tesler | Designers | L. Peter DeutschAdele GoldbergDan IngallsTed KaehlerAlan KayDiana MerryDavid UngarScott Wallace |
| Designers | L. Peter DeutschAdele GoldbergDan IngallsTed KaehlerAlan KayDiana MerryDavid UngarScott Wallace |
| Italics= discontinued° =Open-source softwareBookCategory |