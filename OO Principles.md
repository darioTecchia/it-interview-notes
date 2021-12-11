# Object Oriented Principles

Object oriented programming enable to abstract entity of the domain model into 
**objects**.
Objects are composed of two part: the **state** and the **behaviour**. This two
parts are implemented in a **class**. Objects of a specific class are also called
**instance** of the class. The difference between class and object are better explained
in the snippet below:

```java

// This is the Class
public class Person {
	
	// This is the state of the object
	public String name, surname;
	
	// This is the constructor. It create new instance of person class
	public Person(String name, String surname){
		this.name = name;
		this.surname = surname;
	}

	//This is the behaviour
	public String getFullName(){
		return String.format("%s - %s", this.name, this.surname)
	}
}
// End of the class


// These are objects or better instances of Person
Person contributor = new Person("Didacus", "Abella")
Person creator = new Person("Dario", "Tecchia")


```


Object Oriented Programming follow 3 important principles:

1. Encapsulation
2. Inheritance
3. Polymorphism


## Object Oriented Design

Object oriented design require a good knowledge of various techniques and best 
practices. For a developer point of view is a good idea to know the 21 
**Design Patterns** introduced by the Gof (Gang of Four). A pattern is solution to
common problems encountered during development and are categorized into three main
area:

1. __Creational Patterns__: Solve problems regarding object creation.
2. __Structural Patterns__: Solve problems regarding how to organize the interaction
between objects
3. __Behavioural Patterns__: Solve problems regarding runtime behaviour of the objects

