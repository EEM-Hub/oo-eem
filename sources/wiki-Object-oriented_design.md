---
source: https://en.wikipedia.org/wiki/Object-oriented_design
fetched: 2026-06-19
---

Software development methodology 
|  | This article has multiple issues.Please helpimprove itor discuss these issues on thetalk page.(Learn how and when to remove these messages)This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Object-oriented analysis and design"–news·newspapers·books·scholar·JSTOR(November 2019)(Learn how and when to remove this message)Parts of this article (those related to article) need to beupdated.Please help update this article to reflect recent events or newly available information.(July 2023)(Learn how and when to remove this message) |  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Object-oriented analysis and design"–news·newspapers·books·scholar·JSTOR(November 2019)(Learn how and when to remove this message) |  | Parts of this article (those related to article) need to beupdated.Please help update this article to reflect recent events or newly available information.(July 2023) |
| --- | --- | --- | --- | --- | --- |
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Object-oriented analysis and design"–news·newspapers·books·scholar·JSTOR(November 2019)(Learn how and when to remove this message) |
|  | Parts of this article (those related to article) need to beupdated.Please help update this article to reflect recent events or newly available information.(July 2023) |

 
| Part of a series on |
| --- |
| Software development |
| Core activitiesData modelingProcessesRequirementsDesignConstructionEngineeringTestingDebuggingDeploymentMaintenance |
| Paradigms, modelsAgileCleanroomIncrementalPrototypingSpiralV modelWaterfall |
| Methodologies, frameworksASDDADDevOpsDSDMFDDIIDKanbanLean SDLeSSMDEMSFPSPRADRUPSAFeScrumSEMATTDDTSPUPXP |
| Supporting disciplinesConfiguration managementDeployment managementDocumentationProject managementQuality assuranceUser experience |
| PracticesATDDBDDCCOCDCIDDDPPSBEStand-upTDDXP |
| ToolsBuild automationCompilerDebuggerGUI builderIDEInfrastructure as codeProfilerRelease automationUML modeling |
| Standards, bodies of knowledgeCMMIIEEE standardsIREBISO 9001ISO/IEC standardsITILOMGPMBOKSWEBOK |
| GlossariesArtificial intelligenceComputer scienceElectrical and electronics engineering |
| OutlinesSoftware developmentComputer programmingProgramming languagesCC++C#JavaJavaScriptPerlPythonRust |
| vte |

 

**Object-oriented analysis and design** (**OOAD**) is an approach to [ analyzing](./Requirements_analysis) and [ designing](./Design) a [computer](./Computer)-based system by applying an [object](./Object_(computer_science))-oriented mindset and using [visual modeling](./Visual_modeling) throughout the [software development process](./Software_development_process). It consists of object-oriented analysis (OOA) and object-oriented design (OOD) – each producing a model of the system via [object-oriented modeling](./Object-oriented_modeling) (OOM). Proponents contend that the models should be continuously refined and evolved, in an iterative process, driven by key factors like risk and business value.

 

OOAD is a method of analysis and design that leverages object-oriented principals of decomposition and of notations for depicting logical, physical, state-based and dynamic models of a system. As part of the [software development life cycle](./Software_development_life_cycle) OOAD pertains to two early stages: often called requirement analysis and design.[[1]](./Object-oriented_analysis_and_design#cite_note-Jacobsen_1992_https://archive.org/details/objectorientedso00jaco/page/15_15,199-1)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Waterfall_model_revised.svg/500px-Waterfall_model_revised.svg.png)](./File:Waterfall_model_revised.svg)The [Waterfall Model](./Waterfall_Model). [![](//upload.wikimedia.org/wikipedia/commons/1/19/Development-iterative.png)](./File:Development-iterative.png)OOAD is conducted in an iterative and incremental manner, as formulated by the [Unified Process](./Unified_Process). 

Although OOAD could be employed in a [ waterfall methodology](./Waterfall_model) where the life cycle stages as sequential with rigid boundaries between them, OOAD often involves more iterative approaches. Iterative methodologies were devised to add flexibility to the development process. Instead of working on each life cycle stage at a time, with an iterative approach, work can progress on analysis, design and coding at the same time. And unlike a waterfall mentality that a change to an earlier life cycle stage is a failure, an iterative approach admits that such changes are normal in the course of a knowledge-intensive process – that things like analysis can't really be completely understood without understanding design issues, that coding issues can affect design, that testing can yield information about how the code or even the design should be modified, etc.[[2]](./Object-oriented_analysis_and_design#cite_note-2) Although it is possible to do object-oriented development in a waterfall methodology, most OOAD follows an iterative approach.

 

The object-oriented paradigm emphasizes modularity and re-usability. The goal of an object-oriented approach is to satisfy the ["open–closed principle"](./Open_Closed_Principle).  A module is open if it supports extension, or if the module provides standardized ways to add new behaviors or describe new states. In the object-oriented paradigm this is often accomplished by creating a new subclass of an existing class. A module is closed if it has a well defined stable interface that all other modules must use and that limits the interaction and potential errors that can be introduced into one module by changes in another. In the object-oriented paradigm this is accomplished by defining methods that invoke services on objects. Methods can be either public or private, i.e., certain behaviors that are unique to the object are not exposed to other objects. This reduces a source of many common errors in computer programming.[[3]](./Object-oriented_analysis_and_design#cite_note-3)

 

## Object-oriented analysis

 

Common models used in OOA are the use case and the [object model](./Object_model). A [use case](./Use_case) describes a scenario for standard domain functions that the system must accomplish. An object model describes the names, class relations, operations, and properties of the main objects. User-interface mockups or prototypes can also be created to help understanding.[[4]](./Object-oriented_analysis_and_design#cite_note-4)

 

Unlike with OOA that organizes requirements around objects that integrate processes and data, with other analysis methods, processes and data are considered separately. For example, data may be modeled by [entity–relationship diagrams](./Entity–relationship_model), and behaviors by [flowcharts](./Flowchart) or [structure charts](./Structure_chart).

 

### Artifacts

 

Outputs of OOA are inputs to OOD. In an iterative approach, and an output artifact does not need to be completely developed to serve as input to OOD. Both OOA and OOD can be performed incrementally, and the artifacts can be continuously grown instead of completely developed in one shot. OOA artifacts include:

 Conceptual modelA [conceptual model](./Conceptual_model_(computer_science)) captures concepts in the [problem domain](./Domain_(software_engineering)). The conceptual model is explicitly chosen to be independent of implementation details, such as [concurrency](./Concurrency_(computer_science)) or data storage. Use caseA [use case](./Use_case) is a description of sequences of events that lead to a system doing something useful. Each use case provides one or more [scenarios](./Scenario_(computing)) that convey how the system should interact with the users called actors to achieve a specific business goal or function. Use case actors may be end users or other systems. In many circumstances use cases are further elaborated into [use case diagrams](./Use_case_diagram). Use case diagrams are used to identify the actor (users or other systems) and the processes they perform. System sequence diagramA [system sequence diagram](./System_sequence_diagram) (SSD) is a picture that shows, for a particular scenario of a use case, the events that external actors generate, their order, and possible inter-system events. User interface documentationOptional documentation that shows and describes the [look and feel](./Look_and_feel) of the [user interface](./User_interface). Relational data modelIf an [object database](./Object_database) is not used, a [relational data model](./Relational_data_model) should usually be created before the design since the strategy chosen for [object–relational mapping](./Object–relational_mapping) is an output of the OO design process. However, it is possible to develop the relational data model and the OOD artifacts in parallel, and the growth of an artifact can stimulate the refinement of other artifacts. 

## Object-oriented design

 

OOD, a form of [software design](./Software_design), is the process of planning a system of interacting objects to solve a software problem. A designer applies implementation constraints to the conceptual model produced in OOA. Such constraints could include the [hardware](./Computer_hardware) and [software](./Software) platforms, the performance requirements, persistent storage and transaction, usability of the system, and limitations imposed by budgets and time. Concepts in the analysis model which is technology independent, are mapped onto implementing classes and interfaces resulting in a model of the solution domain, i.e., a detailed description of *how* the system is to be built on concrete technologies.[[5]](./Object-oriented_analysis_and_design#cite_note-5)

 

OOD activities include:

 
- Defining objects and their [attributes](./Attribute_(computing))
- Creating [class diagrams](./Class_diagram) from [conceptual models](./Conceptual_model_(computer_science))
- Using [design patterns](./Design_pattern)[[6]](./Object-oriented_analysis_and_design#cite_note-gof-6)
- Defining [application frameworks](./Application_framework)
- Identifying persistent objects/data
- Designing the object relation mapping if a [relational database](./Relational_database) is used
- Identifying remote objects

 

OOD principles and strategies include:

 Dependency injection[Dependency injection](./Dependency_injection) means if an object depends upon having an instance of some other object, then the needed object is "injected" into the dependent object (for example, being passed a database connection as an argument to the [constructor](./Constructor_(object-oriented_programming)) instead of creating one internally). Acyclic dependencies principleThe [acyclic dependencies principle](./Acyclic_dependencies_principle) is that dependency graph of packages or components (the granularity depends on the scope of work for one developer) should have no cycles. This is also referred to as having a [directed acyclic graph](./Directed_acyclic_graph).[[7]](./Object-oriented_analysis_and_design#cite_note-objectMentor-7) For example, package C depends on package B, which depends on package A. If package A depended on package C, you would have a cycle. Composite reuse principleThe [composite reuse principle](./Composite_reuse_principle) is to favor [polymorphic](./Polymorphism_(computer_science)) [composition](./Object_composition) of objects over inheritance.[[6]](./Object-oriented_analysis_and_design#cite_note-gof-6) 

### Artifacts

 Sequence diagramExtend the [sequence diagram](./Sequence_diagram) to add specific objects that handle the system events. A sequence diagram shows, as parallel vertical lines, different processes or objects that live simultaneously, and, as horizontal arrows, the messages exchanged between them, in the order in which they occur. Class diagramA [class diagram](./Class_diagram) is a type of static structure [UML](./Unified_Modeling_Language) diagram that describes the structure of a system by showing the system's classes, its attributes, and the relationships between the classes. The messages and classes identified through the development of the sequence diagrams can serve as input to the automatic generation of the global class diagram of the system. 

## See also

  
- [ATLAS Transformation Language](./ATLAS_Transformation_Language)
- [Class-responsibility-collaboration card](./Class-responsibility-collaboration_card)
- [Domain specific language](./Domain_specific_language)
- [Domain-driven design](./Domain-driven_design)
- [Domain-specific modelling](./Domain-specific_modelling)
- [GRASP (object-oriented design)](./GRASP_(object-oriented_design))
- [IDEF4](./IDEF4)
- [Meta-Object Facility](./Meta-Object_Facility)
- [Metamodeling](./Metamodeling)
- [Model-driven engineering](./Model-driven_engineering)
- [Model-based testing](./Model-based_testing)
- [Object-oriented modeling](./Object-oriented_modeling)
- [Object-oriented user interface](./Object-oriented_user_interface)
- [QVT](./QVT)
- [Shlaer–Mellor method](./Shlaer–Mellor_method)
- [Software analysis pattern](./Software_analysis_pattern)
- [SOLID](./SOLID)
- [Story-driven modeling](./Story-driven_modeling)
- [Unified Process](./Unified_Process)

  

## References

  
1. [↑](./Object-oriented_analysis_and_design#cite_ref-Jacobsen_1992_https://archive.org/details/objectorientedso00jaco/page/15_15,199_1-0) Jacobsen, Ivar; Magnus Christerson; Patrik Jonsson; Gunnar Overgaard (1992). [*Object Oriented Software Engineering*](https://archive.org/details/objectorientedso00jaco/page/15). Addison-Wesley ACM Press. pp. [15, 199](https://archive.org/details/objectorientedso00jaco/page/15). [ISBN](./ISBN_(identifier)) [0-201-54435-0](./Special:BookSources/0-201-54435-0).
2. [↑](./Object-oriented_analysis_and_design#cite_ref-2) Boehm B, ["A Spiral Model of Software Development and Enhancement](http://csse.usc.edu/csse/TECHRPTS/1988/usccse88-500/usccse88-500.pdf) [Archived](https://web.archive.org/web/20150528141610/http://csse.usc.edu/csse/TECHRPTS/1988/usccse88-500/usccse88-500.pdf) 2015-05-28 at the [Wayback Machine](./Wayback_Machine)", IEEE Computer, IEEE, 21(5):61-72, May 1988
3. [↑](./Object-oriented_analysis_and_design#cite_ref-3) Meyer, Bertrand (1988). *Object-Oriented Software Construction*. Cambridge: Prentise Hall International Series in Computer Science. p. 23. [ISBN](./ISBN_(identifier)) [0-13-629049-3](./Special:BookSources/0-13-629049-3).
4. [↑](./Object-oriented_analysis_and_design#cite_ref-4) Jacobsen, Ivar; Magnus Christerson; Patrik Jonsson; Gunnar Overgaard (1992). [*Object Oriented Software Engineering*](https://archive.org/details/objectorientedso00jaco/page/77). Addison-Wesley ACM Press. pp. [77–79](https://archive.org/details/objectorientedso00jaco/page/77). [ISBN](./ISBN_(identifier)) [0-201-54435-0](./Special:BookSources/0-201-54435-0).
5. [↑](./Object-oriented_analysis_and_design#cite_ref-5) Conallen, Jim (2000). [*Building Web Applications with UML*](https://archive.org/details/buildingwebappli00cona/page/147). Addison Wesley. p. [147](https://archive.org/details/buildingwebappli00cona/page/147). [ISBN](./ISBN_(identifier)) [0201615770](./Special:BookSources/0201615770).
6. [1](./Object-oriented_analysis_and_design#cite_ref-gof_6-0) [2](./Object-oriented_analysis_and_design#cite_ref-gof_6-1) [Erich Gamma](./Erich_Gamma); [Richard Helm](./Richard_Helm); [Ralph Johnson](./Ralph_Johnson_(computer_scientist)); [John Vlissides](./John_Vlissides) (January 2, 1995). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://dl.acm.org/doi/10.5555/186897). [Addison-Wesley](./Addison-Wesley). [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0). 
7. [↑](./Object-oriented_analysis_and_design#cite_ref-objectMentor_7-0) ["What Is Object-Oriented Design?"](https://web.archive.org/web/20070630045531/http://www.objectmentor.com/omSolutions/oops_what.html). Object Mentor. Archived from [the original](http://www.objectmentor.com/omSolutions/oops_what.html) on 2007-06-30. Retrieved 2007-07-03.

 

## Further reading

 
- [Grady Booch](./Grady_Booch). "Object-oriented Analysis and Design with Applications, 3rd edition":[http://www.informit.com/store/product.aspx?isbn=020189551X](http://www.informit.com/store/product.aspx?isbn=020189551X) Addison-Wesley 2007.
- [Rebecca Wirfs-Brock](./Rebecca_Wirfs-Brock), Brian Wilkerson, Lauren Wiener. *Designing Object Oriented Software*. Prentice Hall, 1990. [*A down-to-earth introduction to the object-oriented programming and design.*]
- [A Theory of Object-Oriented Design](https://web.archive.org/web/20070928035622/http://www.eden-study.org/articles/2002/isf4(4).pdf): The building-blocks of OOD and notations for representing them (with focus on design patterns.)
- [Martin Fowler](./Martin_Fowler_(software_engineer)). *Analysis Patterns: Reusable Object Models*. Addison-Wesley, 1997. [*An introduction to object-oriented analysis with conceptual models*]
- [Bertrand Meyer](./Bertrand_Meyer). *Object-oriented software construction*. Prentice Hall, 1997
- [Craig Larman](./Craig_Larman). *Applying UML and Patterns – Introduction to OOA/D & Iterative Development*. Prentice Hall PTR, 3rd ed. 2005.
- Setrag Khoshafian. *Object Orientation*.
- Ulrich Norbisrath, Albert Zündorf, Ruben Jubeh. *Story Driven Modeling*. Amazon Createspace. p. 333, 2013. [ISBN](./ISBN_(identifier)) [9781483949253](./Special:BookSources/9781483949253).

 

## External links

   [![Wikiversity logo](//upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Wikiversity_logo_2017.svg/40px-Wikiversity_logo_2017.svg.png)](./File:Wikiversity_logo_2017.svg) Wikiversity has learning resources about ***[Object Oriented Software Design](https://en.wikiversity.org/wiki/Object%20Oriented%20Software%20Design)***  
- Article [Object-Oriented Analysis and Design with UML and RUP](https://www.beroux.com/english/articles/oop_uml_and_rup.php) an overview (also about CRC cards).
- Applying UML – [Object Oriented Analysis & Design](http://www.parlezuml.com/e-books/umlformanagers/umlformanagers_ch3.pdf) [Archived](https://web.archive.org/web/20090915034105/http://www.parlezuml.com/e-books/umlformanagers/umlformanagers_ch3.pdf) 2009-09-15 at the [Wayback Machine](./Wayback_Machine) tutorial
- OOAD & UML Resource website and Forums – [Object Oriented Analysis & Design with UML](https://www.ooaduml.com)
- [Software Requirement Analysis using UML](https://www.slideshare.net/dhirajmusings/software-requirement-analysis-using-uml) article by Dhiraj Shetty
- Article [Object-Oriented Analysis in the Real World](http://www.methodsandtools.com/archive/archive.php?id=77)
- [*Object-Oriented Analysis & Design*](https://www.parlezuml.com/e-books/umlformanagers/umlformanagers_ch3.pdf) [Archived](https://web.archive.org/web/20090915034105/http://www.parlezuml.com/e-books/umlformanagers/umlformanagers_ch3.pdf) 2009-09-15 at the [Wayback Machine](./Wayback_Machine) – overview using UML
- [Larman, Craig. *Applying UML and Patterns – Third Edition*](https://authors.phptr.com/larman/uml_ooad/index.html) [Archived](https://web.archive.org/web/20161025182528/http://authors.phptr.com/larman/uml_ooad/index.html) 2016-10-25 at the [Wayback Machine](./Wayback_Machine)
- [*Object-Oriented Analysis and Design*](https://www.informit.com/articles/article.aspx?p=360440&seqNum=8)
- [LePUS3 and Class-Z](http://www.lepus.org.uk): formal modelling languages for object-oriented design
- [*The Hierarchy of Objects*](https://docs.google.com/document/d/1IbzL1xyPzpOD_3Tfk4CEgFJbEddT639M1C0WOkMBlTc/edit?usp=sharing)

 
| vteUnified Modeling Language |
| --- |
| Actors | OrganizationsObject Management GroupUML PartnersPersonsGrady BoochIvar JacobsonJames Rumbaugh |  |
| Concepts | Object orientedObject-oriented programmingObject-oriented analysis and designObject-oriented modelingStructureActorAttributeArtifactClassComponentInterfaceObjectPackageProfile diagramBehaviorActivityEventMessageMethodStateUse caseRelationshipsAssociationCompositionDependencyGeneralization(orInheritance)ExtensibilityProfileStereotypeOtherMultiplicity | Object oriented | Object-oriented programmingObject-oriented analysis and designObject-oriented modeling | Structure | ActorAttributeArtifactClassComponentInterfaceObjectPackageProfile diagram | Behavior | ActivityEventMessageMethodStateUse case | Relationships | AssociationCompositionDependencyGeneralization(orInheritance) | Extensibility | ProfileStereotype | Other | Multiplicity |
| Object oriented | Object-oriented programmingObject-oriented analysis and designObject-oriented modeling |
| Structure | ActorAttributeArtifactClassComponentInterfaceObjectPackageProfile diagram |
| Behavior | ActivityEventMessageMethodStateUse case |
| Relationships | AssociationCompositionDependencyGeneralization(orInheritance) |
| Extensibility | ProfileStereotype |
| Other | Multiplicity |
| Diagrams | StructureClassComponentComposite structureDeploymentObjectPackageBehaviourActivityState MachineUse caseInteractionCommunicationsSequenceInteraction overviewTiming | Structure | ClassComponentComposite structureDeploymentObjectPackage | Behaviour | ActivityState MachineUse case | Interaction | CommunicationsSequenceInteraction overviewTiming |
| Structure | ClassComponentComposite structureDeploymentObjectPackage |
| Behaviour | ActivityState MachineUse case |
| Interaction | CommunicationsSequenceInteraction overviewTiming |
| Derived languages | Systems Modeling Language (SysML)UML eXchange Format (UXF)XML Metadata Interchange (XMI)Executable UML (xUML) |
| Other topics | Glossary of UML termsRational Unified ProcessList of Unified Modeling Language toolsObject Modeling in Color |