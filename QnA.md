# Questions and Answers take from the world

https://career.guru99.com/technical-interview-questions/

## Algorithms
### Explain what is Quick Sort algorithm?
Quick Sort algorithm has the ability to sort list or queries quickly. It is based on the principle of partition exchange sort or Divide and conquer. This type of algorithm occupies less space, and it segregates the list into three main parts.

- Elements less than the Pivot element
- Pivot element
- Elements greater than the Pivot element

### Explain what is time complexity of Algorithm?
Time complexity of an algorithm indicates the total time needed by the program to run to completion. It is usually expressed by using the big O notation.

### Explain how binary search works?
In binary search, we compare the key with the item in the middle position of the array. If the key is less than the item searched then it must lie in the lower half of the array, if the key is greater than the item searched than it should be in upper half of the array.

### Explain whether it is possible to use binary search for linked liss?

Since random access is not acceptable in linked list, it is impossible to reach the middle element of O(1) time. Thus, binary search is not possible for linked list.

### Explain what is heap sort?
Heap-sort can be defined as a comparison based sorting algorithm. It divides its input into the unsorted and sorted region, until it shrinks the unsorted region by eliminating the smallest element and moving that to the sorted region.

### Explain what is the difference between best case scenario and worst case scenario of an algorithm?
__Best case scenario__: Best case scenario for an algorithm is explained as the arrangement of data for which the algorithm performs best. For example, we take a binary search, for which the best case scenario would be if the target value is at the very center of the data you are searching. The best case time complexity would be O(1).

__Worst case scenario__: It is referred for the worst set of input for a given algorithm. For example quicksort, which can perform worst if you select the largest or smallest element of a sublist for the pivot value. It will cause quicksort to degenerate to O(n<sup>2</sup>).

### Explain what is a recursive algorithm?
Recursive algorithm is a method of solving a complicated problem by breaking a problem down into smaller and smaller sub-problems until you get the problem small enough that it can be solved easily. Usually, it involves a function calling itself.

### Mention what are the three laws of recursion algorithm?
All recursive algorithm must follow three laws:
- It should have a base case
- A recursive algorithm must call itself
- A recursive algorithm must change its state and move towards the base case

### Explain what is bubble sort algorithm?
Bubble sort algorithm is also referred as sinking sort. In this type of sorting, the list to be sorted out compares the pair of adjacent items. If they are organized in the wrong order, it will swap the values and arrange them in the correct order.

## MySQL
### Differentiate between FLOAT and DOUBLE? 
Following are differences for `FLOAT` and `DOUBLE`:
- Floating point numbers are stored in `FLOAT` with eight place accuracy and it has four bytes.
- Floating point numbers are stored in `DOUBLE` with accuracy of 18 places and it has eight bytes.

### Differentiate CHAR_LENGTH and LENGTH?
`CHAR_LENGTH` is character count whereas the `LENGTH` is byte count. The numbers are same for Latin characters but they are different for Unicode and other encodings.

### Difference between CHAR and VARCHAR? 
Following are the differences between `CHAR` and `VARCHAR`:
- `CHAR` and `VARCHAR` types differ in storage and retrieval.
- `CHAR` column length is fixed to the length that is declared while creating table. The length value ranges from 1 and 255.
- When `CHAR` values are stored then they are right padded using spaces to specific length. Trailing spaces are removed when `CHAR` values are retrieved.

### What is the difference between primary key and candidate key?

Every row of a table is identified uniquely by __primary key__. There is only one __primary key__ for a table.

__Primary Key is also a candidate key__. By common convention, candidate key can be designated as primary and which can be used for any foreign key references.

### What is the difference between mysql_fetch_array and mysql_fetch_object?

Following are the differences between `mysql_fetch_array` and `mysql_fetch_object`:

- `mysql_fetch_array`: Returns a result row as an associated array or a regular array from database.

- `mysql_fetch_object`:  Returns a result row as object from database.

## DBMS
### Enlist the various relationships of database
The various relationships of database are:

- __One-to-one__: Single table having drawn relationship with another table having similar kind of columns.
- __One-to-many__: Two tables having primary and foreign key relation.
- __Many-to-many__: Junction table having many tables related to many tables.

### Define Normalization
Organized data void of inconsistent dependency and redundancy within a database is called normalization.

### Enlist the advantages of normalizing database.
Advantages of normalizing database are:

- No duplicate entries
- Saves storage space
- Boasts the query performances.

### Define Denormalization
Boosting up database performance, adding of redundant data which in turn helps rid of complex data is called denormalization.

### Define DDL and DML
- Managing properties and attributes of database is called __Data Definition Language (DDL)__.
- Manipulating data in a database such as inserting, updating, deleting is defined as __Data Manipulation Language (DML)__.

## Model View Controller

### What is Model-View-Controller?
MVC is a software architecture pattern for developing web applications. It is handled by three objects, Model, View, and Controller.

### What does Model-View-Controller represent in an MVC application?
In an MVC model:
- __Model__: It represents the application data domain. In other words, an application’s business logic is contained within the model and is responsible for maintaining data.
- __View__: It represents the user interface with which end-users communicate. In short, all the user interface logic is contained within View.
- __Controller__: It is the controller that answers the user’s actions. Based on the user actions, the respective controller responds within the model and chooses a view to render that displays the user interface. The user input logic is contained within the controller.

### What are the advantages of MVC?
- MVC segregates your project into a different segment, and it becomes easy for developers to work on
- It is easy to edit or change some part of your project that benefits in less development and maintenance cost of the project
- MVC makes your project more systematic
- It represents a clear separation between business logic and presentation logic
- Each MVC object has different responsibilities
- The development progresses in parallel
- Easy to manage and maintain
- All classes and objects are independent of each other

### What are the steps for the execution of an MVC project?

The steps for the execution of an MVC project includes:
- Receive the first request for the application
- Perform routing
- Create an MVC request handler
- Create Controller
- Execute Controller
- Invoke action
- Execute Result

### What are the features of MVC?
Here are the features of MVC:
- Easy and frictionless testability. Highly testable, extensible, and pluggable framework.
- Offers full control over your HTML as well as your URLs
- Leverages existing features provided by ASP.NET, JSP, Django, etc.
- Clear separation of logic: Model, View, Controller. Separation of application tasks via business logic, Ul logic, and input logic.
- URL Routing for SEO Friendly URLs. Powerful URL- mapping for comprehensible and searchable URLs.
- Support for Test Driven Development (TDD).

### What is the difference between MVVM and MVC?
Here are the important differences between MVVM and MVC:

|MVC|MVVM|
|--- |--- |
|A Controller is the entry point to the Application.|The View is the entry point to the Application.|
|One to many relationships between Controller & View.|One to many relationships between View & View Model.|
|View does not have reference to the Controller|View have references to the View-Model.|
|MVC is Old Model|MVVM is a relatively New Model.|
|Difficult to read, change, to unit test, and reuse this Model|The debugging process will be complicated when we have complex data bindings.|
|MVC Model component can be tested separately from the user|Easy for separate unit testing and code is event-driven.|

### What is MVC in AngularJS?
- The __Controller__ represents the layer that has the business logic. User events trigger the functions which are stored inside your controller. The user events are part of the controller.
- __Views__ are used to represent the presentation layer which is provided to the end-users.
- __Models__ are used to represent your data. The data in your model can be as simple as just having primitive declarations. For example, if you are maintaining a student application, your data model could just have a student id and a name. Or it can also be complex by having a structured data model. If you are maintaining a car ownership application, you can have structures to define the vehicle itself in terms of its engine capacity, seating capacity, etc.

## Web Development

### Explain what is CORS? How does it work?
(CORS) Cross-Origin Resource Sharing is a mechanism that enables many resources (e.g., JavaScript, fonts etc.) on a web page to be requested from another domain outside the domain from which the resource originated.  It is a mechanism supported in HTML5 that manages XMLHttpRequest access to a domain different.

### List out the advantage of HTTP/2 as compared with HTTP 1.1?
The advantage of HTTP/2 compared to HTTP/1.1 is:
- HTTP headers data compression
- Server push technologies
- Over a single TCP connection parallel loading of page elements
- Prioritization of request

### Mention some tips you can use to reduce the load time of a web application that you have written?
To decrease the load time of a web application you have to follow the following tips

- Optimize images to no longer than screen resolution and save it as a compressed file
- Eliminate all JavaScript files to reduce the amount of transferable data
- Combine & Mininify all CSS and JS and call them in footer
- Defer or Asynch JS Files
- Caching

### Mention what is the correct way to include JavaScript into your HTML?
The correct way to include JavaScript into your HTML is by using inline event handlers or inline code.

### Explain what is the difference between cookies and local storage?
||||
|--- |--- |--- |
||Cookies|Local Storage|
|Client Side/ Server Side|Data accessible both at client side and server side. The data is sent to the serverside with every cookie request.|Only at the local browser side data is accessible. Server cannot use local storage until deliberately sent a request to the server via POST or GET|
|Size|Storage capacity of cookies is 4095 bytes/cookie|Storage capacity of local storage is 5MB per domain|
|Expiration|Cookies have expiration and cookie data gets deleted after some time|There is no expiration and has to remove manually|

### Explain how can you refer to CSS file in the web page?
You can refer to the `.css` file in the webpage by using the `<link>` tag. It should be kept between `<head></head>` tags. For example `<link href=”/css/mystyle.css” type=”text/css” rel=”stylesheet”/>`.

## OOP
### Write basic concepts of OOPS?
Following are the concepts of OOPS:
- Abstraction
- Encapsulation
- Inheritance
- Polymorphism

### What is a class?
A class is simply a representation of a type of object. It is the blueprint/plan/template that describes the details of an object.

### What is an Object?
An object is an instance of a class. It has its own state, behavior, and identity.

### What is the main difference between a class and an object?
An object is an instance of a class. Objects hold multiple information, but classes don’t have any information. Definition of properties and functions can be done in class and can be used by the object.

A class can have sub-classes, while an object doesn’t have sub-objects.

### What is Encapsulation?
Encapsulation is an attribute of an object, and it contains all data which is hidden. That hidden data can be restricted to the members of that class.

Levels are `public`, `protected`, `private`, `internal`, and `protected internal`.

### What is Polymorphism?
Polymorphism is nothing but assigning behavior or value in a subclass to something that was already declared in the main class. Simply, polymorphism takes more than one form.

### What is Inheritance?
Inheritance is a concept where one class shares the structure and behavior defined in another class. If Inheritance applied to one class is called Single Inheritance, and if it depends on multiple classes, then it is called multiple Inheritance.

### What are manipulators?
Manipulators are the functions which can be used in conjunction with the insertion (<<) and extraction (>>) operators on an object. Examples are endl and setw.

### Explain the term constructor
A constructor is a method used to initialize the state of an object, and it gets invoked at the time of object creation. Rules for constructor are:

Constructor Name should be the same as a class name.
A constructor must have no return type.

### What is an Inline function?
An inline function is a technique used by the compilers and instructs to insert complete body of the function wherever that function is used in the program source code.

### What is function overloading?
Function overloading is a regular function, but it is assigned with multiple parameters. It allows the creation of several methods with the same name which differ from each other by the type of input and output of the function.

Example:
```java
void add(int& a, int& b);

void add(double& a, double& b);

void add(struct bob& a, struct bob& b);
```

### What is method overriding?
Method overriding is a feature that allows a subclass to provide the implementation of a method that overrides in the main class. It will override the implementation in the superclass by providing the same method name, same parameter, and same return type.

### What is the main difference between overloading and overriding?
__Overloading__ is static Binding, whereas Overriding is dynamic Binding. Overloading is nothing but the same method with different arguments, and it may or may not return the equal value in the same class itself.

__Overriding__ is the same method names with the same arguments and return types associated with the class and its child class.

### What is an abstract class?
An abstract class is a class which cannot be instantiated. Creation of an object is not possible with an abstract class, but it can be inherited. An abstract class can contain only an Abstract method. Java allows only abstract method in abstract class while other languages allow non-abstract method as well.

### What are the different types of arguments?
A parameter is a variable used during the declaration of the function or subroutine, and arguments are passed to the function body, and it should match with the parameter defined. There are two types of Arguments.

- __Call by Value__: Value passed will get modified only inside the function, and it returns the same value whatever it is passed into the function.
- __Call by Reference__: Value passed will get modified in both inside and outside the functions and it returns the same or different value.

### What is the super keyword?
The `super` keyword is used to invoke the overridden method, which overrides one of its superclass methods. This keyword allows to access overridden methods and also to access hidden members of the superclass.

It also forwards a call from a constructor, to a constructor in the superclass.

### What is an interface?
An interface is a collection of an abstract method. If the class implements an interface, it thereby inherits all the abstract methods of an interface.

Java uses Interface to implement multiple inheritances.

### What is an abstraction?
Abstraction is a useful feature of OOPS, and it shows only the necessary details to the client of an object. Meaning, it shows only required details for an object, not the inner constructors, of an object. Example – When you want to switch on the television, it is not necessary to know the inner circuitry/mechanism needed to switch on the TV. Whatever is required to switch on TV will be shown by using an abstract class.

### How can we call the base method without creating an instance?
Yes, it is possible to call the base method without creating an instance. And that method should be “Static method.”

### What is early and late Binding?
Early binding refers to the assignment of values to variables during design time, whereas late Binding refers to the assignment of values to variables during run time.

### What is ‘this’ pointer?
THIS pointer refers to the current object of a class. THIS keyword is used as a pointer which differentiates between the current object with the global object. It refers to the current object.

### What is dynamic or run time polymorphism?
Dynamic or Run time polymorphism is also known as method overriding in which call to an overridden function is resolved during run time, not at the compile time. It means having two or more methods with the same name, same signature but with different implementation.

### Whether static method can use nonstatic members?
False.

### What are a base class, subclass, and superclass?
- The base class is the most generalized class, and it is said to be a root class.
- A Subclass is a class that inherits from one or more base classes.
- The superclass is the parent class from which another class inherits.

### Which OOPS concept exposes only the necessary information to the calling functions?
Encapsulation

## Data Structure
### What is data structure?
Data structure refers to the way data is organized and manipulated. It seeks to find ways to make data access more efficient. When dealing with the data structure, we not only focus on one piece of data but the different set of data and how they can relate to one another in an organized manner.

### When is a binary search best applied?
A binary search is an algorithm that is best applied to search a list when the elements are already in order or sorted. The list is searched starting in the middle, such that if that middle value is not the target search key, it will check to see if it will continue the search on the lower half of the list or the higher half. The split and search will then continue in the same manner.

### What is a linked list?
A linked list is a sequence of nodes in which each node is connected to the node following it. This forms a chain-like link for data storage.

### What is LIFO?
LIFO is a short form of Last In First Out. It refers how data is accessed, stored and retrieved. Using this scheme, data that was stored last should be the one to be extracted first. This also means that in order to gain access to the first data, all the other data that was stored before this first data must first be retrieved and extracted.

### What is a queue?
A queue is a data structure that can simulate a list or stream of data. In this structure, new elements are inserted at one end, and existing elements are removed from the other end.

### What are binary trees?
A binary tree is one type of data structure that has two nodes, a left node, and a right node. In programming, binary trees are an extension of the linked list structures.

### Which data structures are applied when dealing with a recursive function?
Recursion, is a function that calls itself based on a terminating condition, makes use of the stack. Using LIFO, a call to a recursive function saves the return address so that it knows how to return to the calling function after the call terminates.

### What is a stack?
A stack is a data structure in which only the top element can be accessed. As data is stored in the stack, each data is pushed downward, leaving the most recently added data on top.

###  Explain Binary Search Tree
A binary search tree stores data in such a way that they can be retrieved very efficiently. The left subtree contains nodes whose keys are less than the node’s key value, while the right subtree contains nodes whose keys are greater than or equal to the node’s key value. Moreover, both subtrees are also binary search trees.

### Are linked lists considered linear or non-linear data structures?
It depends on where you intend to apply linked lists. If you based it on storage, a linked list is considered non-linear. On the other hand, if you based it on access strategies, then a linked list is considered linear.

### What is FIFO?
FIFO stands for First-in, First-out, and is used to represent how data is accessed in a queue. Data has been inserted into the queue list the longest is the one that is removed first.

### What is an ordered list?
An ordered list is a list in which each node’s position in the list is determined by the value of its key component, so that the key values form an increasing sequence, as the list is traversed.

### What is merge sort?
Merge sort, is a  divide-and-conquer approach for sorting the data. In a sequence of data, adjacent ones are merged and sorted to create bigger sorted lists. These sorted lists are then merged again to form an even bigger sorted list, which continues until you have one single sorted list.

### Differentiate NULL and VOID
Null is a value, whereas Void is a data type identifier. A variable that is given a Null value indicates an empty value. The void is used to identify pointers as having no initial size.

### What is the primary advantage of a linked list?
A linked list is an ideal data structure because it can be modified easily. This means that editing a linked list works regardless of how many elements are in the list.

### What is the difference between a PUSH and a POP?
Pushing and popping applies to the way data is stored and retrieved in a stack. A push denotes data being added to it, meaning data is being “pushed” into the stack. On the other hand, a pop denotes data retrieval, and in particular, refers to the topmost data being accessed.

### What is a linear search?
A linear search refers to the way a target key is being searched in a sequential data structure. In this method, each element in the list is checked and compared against the target key. The process is repeated until found or if the end of the file has been reached.

### How does variable declaration affect memory allocation?
The amount of memory to be allocated or reserved would depend on the data type of the variable being declared. For example, if a variable is declared to be of integer type, then 32 bits of memory storage will be reserved for that variable.

### What is the advantage of the heap over a stack?
The heap is more flexible than the stack. That’s because memory space for the heap can be dynamically allocated and de-allocated as needed. However, the memory of the heap can at times be slower when compared to that stack.

### What is Data abstraction?
Data abstraction is a powerful tool for breaking down complex data problems into manageable chunks. This is applied by initially specifying the data objects involved and the operations to be performed on these data objects without being overly concerned with how the data objects will be represented and stored in memory.

### How do you insert a new item in a binary search tree?
Assuming that the data to be inserted is a unique value (that is, not an existing entry in the tree), check first if the tree is empty. If it’s empty, just insert the new item in the root node. If it’s not empty, refer to the new item’s key. If it’s smaller than the root’s key, insert it into the root’s left subtree, otherwise, insert it into the root’s right subtree.

### How does a selection sort work for an array?
The selection sort is a fairly intuitive sorting algorithm, though not necessarily efficient. In this process, the smallest element is first located and switched with the element at subscript zero, thereby placing the smallest element in the first position.

The smallest element remaining in the subarray is then located next to subscripts 1 through n-1 and switched with the element at subscript 1, thereby placing the second smallest element in the second position. The steps are repeated in the same manner till the last element.

### How do signed and unsigned numbers affect memory?
In the case of signed numbers, the first bit is used to indicate whether positive or negative, which leaves you with one bit short. With unsigned numbers, you have all bits available for that number. The effect is best seen in the number range (an unsigned 8-bit number has a range 0-255, while the 8-bit signed number has a range -128 to +127.

### What is the minimum number of nodes that a binary tree can have?
A binary tree can have a minimum of zero nodes, which occurs when the nodes have NULL values. Furthermore, a binary tree can also have 1 or 2 nodes.

### Which sorting algorithm is considered the fastest?
There are many types of sorting algorithms: quick sort, bubble sort, balloon sort, radix sort, merge sort, etc. Not one can be considered the fastest because each algorithm is designed for a particular data structure and data set. It would depend on the data set that you would want to sort.

### What is a bubble sort and how do you perform it?
A bubble sort is one sorting technique that can be applied to data structures such as an array. It works by comparing adjacent elements and exchanges their values if they are out of order. This method lets the smaller values “bubble” to the top of the list, while the larger value sinks to the bottom.

### How does selection sort work?
Selection sort works by picking the smallest number from the list and placing it at the front. This process is repeated for the second position towards the end of the list. It is the simplest sort algorithm.

### What is a graph?
A graph is one type of data structure that contains a set of ordered pairs. These ordered pairs are also referred to as edges or arcs and are used to connect nodes where data can be stored and retrieved.

### Briefly explain recursive algorithm.
Recursive algorithm targets a problem by dividing it into smaller, manageable sub-problems. The output of one recursion after processing one sub-problem becomes the input to the next recursive process.

### How do you search for a target key in a linked list?
To find the target key in a linked list, you have to apply sequential search. Each node is traversed and compared with the target key, and if it is different, then it follows the link to the next node. This traversal continues until either the target key is found or if the last node is reached.