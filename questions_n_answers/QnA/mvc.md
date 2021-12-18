# Model View Controller

## What is Model-View-Controller?
MVC is a software architecture pattern for developing web applications. It is handled by three objects, Model, View, and Controller.

## What does Model-View-Controller represent in an MVC application?
In an MVC model:
- __Model__: It represents the application data domain. In other words, an application’s business logic is contained within the model and is responsible for maintaining data.
- __View__: It represents the user interface with which end-users communicate. In short, all the user interface logic is contained within View.
- __Controller__: It is the controller that answers the user’s actions. Based on the user actions, the respective controller responds within the model and chooses a view to render that displays the user interface. The user input logic is contained within the controller.

## What are the advantages of MVC?
- MVC segregates your project into a different segment, and it becomes easy for developers to work on
- It is easy to edit or change some part of your project that benefits in less development and maintenance cost of the project
- MVC makes your project more systematic
- It represents a clear separation between business logic and presentation logic
- Each MVC object has different responsibilities
- The development progresses in parallel
- Easy to manage and maintain
- All classes and objects are independent of each other

## What are the steps for the execution of an MVC project?

The steps for the execution of an MVC project includes:
- Receive the first request for the application
- Perform routing
- Create an MVC request handler
- Create Controller
- Execute Controller
- Invoke action
- Execute Result

## What are the features of MVC?
Here are the features of MVC:
- Easy and frictionless testability. Highly testable, extensible, and pluggable framework.
- Offers full control over your HTML as well as your URLs
- Leverages existing features provided by ASP.NET, JSP, Django, etc.
- Clear separation of logic: Model, View, Controller. Separation of application tasks via business logic, Ul logic, and input logic.
- URL Routing for SEO Friendly URLs. Powerful URL- mapping for comprehensible and searchable URLs.
- Support for Test Driven Development (TDD).

## What is the difference between MVVM and MVC?
Here are the important differences between MVVM and MVC:

|MVC|MVVM|
|--- |--- |
|A Controller is the entry point to the Application.|The View is the entry point to the Application.|
|One to many relationships between Controller & View.|One to many relationships between View & View Model.|
|View does not have reference to the Controller|View have references to the View-Model.|
|MVC is Old Model|MVVM is a relatively New Model.|
|Difficult to read, change, to unit test, and reuse this Model|The debugging process will be complicated when we have complex data bindings.|
|MVC Model component can be tested separately from the user|Easy for separate unit testing and code is event-driven.|

## What is MVC in AngularJS?
- The __Controller__ represents the layer that has the business logic. User events trigger the functions which are stored inside your controller. The user events are part of the controller.
- __Views__ are used to represent the presentation layer which is provided to the end-users.
- __Models__ are used to represent your data. The data in your model can be as simple as just having primitive declarations. For example, if you are maintaining a student application, your data model could just have a student id and a name. Or it can also be complex by having a structured data model. If you are maintaining a car ownership application, you can have structures to define the vehicle itself in terms of its engine capacity, seating capacity, etc.
