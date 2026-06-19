---
source: sources/wiki-ModelE28093viewE28093controller.md
source_url: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
---

## Model–View–Controller (MVC) Architectural Pattern

MVC is a software architectural pattern that divides application logic into three interconnected components — Model, View, and Controller — to separate internal data representation from user interface and input handling. Originally created for desktop GUIs in Smalltalk-79, it became the dominant pattern for web application frameworks including Rails, Django, and Spring.

## Key Concepts

- **Model**: The central component managing the application's data structure, logic, and rules, independent of the UI. In web frameworks, typically maps to a database table via ORM.
- **View**: Any visual representation of information (charts, tables, HTML templates). Multiple views of the same model data are possible. In web frameworks, views are typically HTML templates rather than composable widget objects.
- **Controller**: Accepts user input, converts it to commands for the model or view. In web frameworks, receives HTTP requests, interacts with models, and selects views for the response.
- **Separation of concerns**: Each component has a distinct responsibility — data management, presentation, and input handling are decoupled.
- **Observer relationship**: When a model changes, it notifies its views to update (in the original Smalltalk-80 design).
- **Framework interpretation varies**: Smalltalk-80, WebObjects, Rails, and Django each interpret MVC differently, especially regarding where input handling lives and how views communicate.
- **Django's MTV variant**: Django renames the components — "view" means controller, "template" means view — but follows the same separation principle.

## Commands and Syntax

No CLI commands per se, but the pattern manifests in framework conventions:

- **Rails**: Routes map requests to controller actions; controllers call models and render views. Convention: `ClientsController` pairs with `clients/` view templates.
- **Django**: URL conf routes to view functions; views query models and render templates. A "view" is a Python function receiving a request and returning a response.
- **Smalltalk-80**: Abstract `View` and `Controller` classes are subclassed; an "MVC Inspector" tool displays model/view/controller structure side-by-side.

## Relationships

- **Observer Pattern**: MVC relies on observer for model-to-view notification (model changes trigger view updates).
- **Strategy Pattern**: Controllers can be swapped at runtime (switchable input modes), which is an application of Strategy.
- **Separation of Concerns**: MVC is a concrete realization of this principle.
- **Variants and descendants**: HMVC (hierarchical), MVA (model–view–adapter), MVP (model–view–presenter), MVVM (model–view–viewmodel) all evolved from MVC.
- **Action–Domain–Responder (ADR)**: A web-specific refinement of MVC.
- **Multitier Architecture**: MVC maps onto presentation-tier concerns in N-tier systems; the thin-client vs. rich-client split determines where MVC components execute.
- **Composite Pattern**: Views in Smalltalk-80 and WebObjects are composable (subviews within views).
- **Single Responsibility Principle**: MVC was one of the first patterns to describe software constructs in terms of their responsibilities.

## Exam-Relevant Points

- MVC was invented by **Trygve Reenskaug** at **Xerox PARC** in the late 1970s while working on **Smalltalk-79**. His original design had four parts: Model, View, Thing, and Editor.
- The three components: **Model** (data/logic), **View** (presentation), **Controller** (input handling/mediation).
- In **Smalltalk-80**, views communicate with both model and controller; in **WebObjects**, views talk only to the controller.
- In **Rails**, each view typically has a **one-to-one relationship** with a controller action.
- **Django** uses the term "view" for what MVC calls a controller, and "template" for what MVC calls a view (MTV pattern).
- **NeXT's WebObjects** (1996) drove MVC adoption in web development; it was originally written in **Objective-C**.
- Martin Fowler's **Patterns of Enterprise Application Architecture** (2003) defined MVC with an "input controller" that receives requests, messages models, and passes responses to views.
- Early web MVC used a **thin-client** approach (all logic server-side); later frameworks added **Ajax** for client-side MVC execution.
- Key advantages: independence of presentation and data, composable widgets, switchable input modes, and separation of input/output processing.
- MVC defines interactions: model manages data and receives input from controller; view renders model state; controller receives user input and passes it to model.
