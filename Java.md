# Java

- [Java](#java)
  * [Java Scope](#java-scope)
    + [Method Scope](#method-scope)
    + [Block Scope](#block-scope)
    + [Variable Kind](#variable-kind)
  * [Java Modifiers](#java-modifiers)
    + [Access Modifiers](#access-modifiers)
    + [Non-Access Modifiers](#non-access-modifiers)
  * [Wrapper Classes](#wrapper-classes)
  * [Autoboxing and Unboxing](#autoboxing-and-unboxing)
    + [Equality between wrapper classes](#equality-between-wrapper-classes)
  * [Overload](#overload)
  * [Override](#override)
  * [VarArgs](#varargs)
  * [Static Methods and Instance (Non static) Methods](#static-methods-and-instance--non-static--methods)
  * [Array](#array)
  * [String](#string)
  * [Enum](#enum)
  * [Multithreading](#multithreading)
    + [Creating a Thread](#creating-a-thread)
      - [Extend Syntax](#extend-syntax)
      - [Implement Syntaxt](#implement-syntaxt)
  * [Collection Interface and List Interface](#collection-interface-and-list-interface)
  * [:: Keyword](#---keyword)
  * [Lambda Expression](#lambda-expression)
  * [Recursion](#recursion)
    + [Recursion Example](#recursion-example)
      - [Example](#example)
      - [Example Explained](#example-explained)
    + [How is recursion implemented in Java?](#how-is-recursion-implemented-in-java-)
  * [Abstract Class](#abstract-class)
    + [Abstract Class vs Interface](#abstract-class-vs-interface)
  * [Generic Type](#generic-type)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


## Java Scope
In Java, variables are only accessible inside the region they are created. This is called scope.

### Method Scope
Variables declared directly inside a method are available anywhere in the method following the line of code in which they were declared:

```java
public class Main {
  public static void main(String[] args) {

    // Code here CANNOT use x

    int x = 100;

    // Code here can use x
    System.out.println(x);
  }
}
```

### Block Scope
A block of code refers to all of the code between curly braces `{}`. Variables declared inside blocks of code are only accessible by the code between the curly braces, which follows the line in which the variable was declared:
```java
public class Main {
  public static void main(String[] args) {

    // Code here CANNOT use x

    { // This is a block

      // Code here CANNOT use x

      int x = 100;

      // Code here CAN use x
      System.out.println(x);

   } // The block ends here

  // Code here CANNOT use x

  }
}
```
### Variable Kind
There are tree kinds of variable:
- Local Variable: internal to the method
- Instance Variable: internal to the class
- Class Variable (Static)

## Java Modifiers
### Access Modifiers
For __classes__, you can use either `public` or `default`:
| Modifier | Description |
| - | - |
| `public` | The class is accessible by any other class |
| `default` | The class is only accessible by classes in the same package. This is used when you don't specify a modifier. |

For __attributes__, __methods__ and __constructors__, you can use the one of the following:
| Modifier | Description |
| - | - |
| `public` | The code is accessible for all classes. |
| `private` | The code is only accessible within the declared class. |
| `default` | The code is only accessible in the same package. This is used when you don't specify a modifier. |
| `protected` |	The code is accessible in the same package and subclasses. |

### Non-Access Modifiers
For __classes__, you can use either `final` or `abstract`:
| Modifier | Description |
| - | - |
| `final` |	The class cannot be inherited by other classes.	|
| `abstract` |	The class cannot be used to create objects (To access an abstract class, it must be inherited from another class. |

For __attributes__ and __methods__, you can use the one of the following:
| Modifier | Description |
| - | - |
| `final` |	Attributes and methods cannot be overridden/modified. |
| `static` |	Attributes and methods belongs to the class, rather than an object. |
| `abstract` |	Can only be used in an abstract class, and can only be used on methods. The method does not have a body, for example abstract void run();. The body is provided by the subclass (inherited from). You will learn more about inheritance and abstraction in the Inheritance and Abstraction chapters. |
| `transient` |	Attributes and methods are skipped when serializing the object containing them. |
| `synchronized` |	Methods can only be accessed by one thread at a time. |
| `volatile` |	The value of an attribute is not cached thread-locally, and is always read from the "main memory". |

A variable can be `static final` and it's called _CONSTANT_.

## Wrapper Classes
Wrapper classes provide a way to use primitive data types (`int`, `boolean`, etc..) as objects.

Sometimes you must use wrapper classes, for example when working with Collection objects, such as `ArrayList`, where primitive types cannot be used (the list can only store objects).

### Autoboxing and Unboxing
Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes. For example, converting an `int` to an `Integer`, a `double` to a `Double`, and so on. If the conversion goes the other way, this is called unboxing.

Here there are simple examples:
```java
Integer x = 10; // autoboxing

Integer x = new Integer(10); // boxing

int y = x.absoluteValue(x) // unboxing

```

```java
public static int absoluteValue(int i) {
  return (i < 0) ? -i : i;
}
```

### Equality between wrapper classes
Particular attention should be paid to the use of the equality operator (`==`) between wrapper classes since the comparison would be done by reference and the result could be false (unboxing is not done).

```java
Integer x = new Integer(10);
Integer y = new Integer(10);
System.out.println(x == y); // false!

Integer x = 10;
Integer y = 10;
System.out.println(x == y); // true!
```

## Overload
With __method overloading__, multiple methods can have the same name with different parameters. A typical example is a constructor that have different parameters:
```java
class Foo {
  public Foo() { }
  public Foo(String a) { }
  public Foo(String a, int b) { }
}
```

## Override
// TODO

## VarArgs
Varargs provide a short-hand for methods that support an arbitrary number of parameters of one type.

```java
public String formatWithVarArgs(String... values) {
    // ...
}

formatWithVarArgs();

formatWithVarArgs("a", "b", "c", "d");
```

## Static Methods and Instance (Non static) Methods
An example to demonstrate the differences between `static` and `public` methods:
```java
public class Main {
  // Static method
  static void myStaticMethod() {
    System.out.println("Static methods can be called without creating objects");
  }

  // Public method
  public void myPublicMethod() {
    System.out.println("Public methods must be called by creating objects");
  }

  // Main method
  public static void main(String[] args) {
    Main.myStaticMethod(); // Call the static method
    // myPublicMethod(); This would compile an error

    Main myObj = new Main(); // Create an object of Main
    myObj.myPublicMethod(); // Call the public method on the object
  }
}
```

## Array
A simple array of `n` elements can be specified in those ways:

```java
String[n] cars; // or String cars[n];

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

int[] myNum = {10, 20, 30, 40};
```

## String
Strings are used for storing text and they are __immutable__. Infact, if we apply the `replace` method to a string it does not change, but the new returned value that can be assigned to the old reference. Rather the classes `StringBuffer` or `StringBuilder` can be used.

```java
String a = "Ciao Mondo";

a.replace("Mondo", "Bella");

System.out.println(a); // Ciao Mondo

a = a.replace("Mondo", "Bella");

System.out.println(a); // Ciao Bella
```

## Enum
An `enum` is a special "class" that represents a group of constants (unchangeable variables, like final variables). With `enum`, we "force" a variable to have a value predefined by the programmer.

The `enum` class extends `java.lang.Enum` class.

## Multithreading
Threads allows a program to operate more efficiently by doing multiple things at the same time.

Threads can be used to perform complicated tasks in the background without interrupting the main program.

### Creating a Thread
There are two ways to create a thread.

#### Extend Syntax
It can be created by extending the `Thread` class and overriding its `run()` method:
```java
public class Main extends Thread {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```
#### Implement Syntaxt
Another way to create a thread is to implement the `Runnable` interface:
```java
public class Main implements Runnable {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```

> Differences between "extending" and "implementing" Threads
> 
> The major difference is that when a class extends the Thread class, you cannot extend any other class, but by implementing the Runnable interface, it is possible to extend from another class as well, like: class MyClass extends OtherClass implements Runnable.

## Collection Interface and List Interface
The `java.util.Collection` interface describes the abstract collection type via methods of which the most frequently used ones are:

```java
boolean add(E e)
boolean remove(Object o)
boolean contains(Object o)
boolean isEmpty()
void clear()
int size()
Iterator<E> iterator()
```

`java.util.Collection` is extended by `java.util.List<E>` and `java.util.Queue<E>` to realize list and queue types. A list keeps its elements respecting the insertion order, each element in list has an index with starting value 0. The `List` interface adds methods for indexing the elements:
```java
add(int index, E element)
E get(int index)
int indexOf(Object o)
E remove(int index)
```

The most used classes that implement `List` are `java.util.Vector`, `java.util.Stack` and `java.util.ArrayList`. `Vector` provides a synchronized implementation of `List` methods resulting in Thread Safe. `ArrayList` is identical to `Vector` but with unsynchronized methods.

## :: Keyword
Usually, one would call the reduce method using `Math.max(int, int)` as follows:

```java
reduce(new IntBinaryOperator() {
    int applyAsInt(int left, int right) {
        return Math.max(left, right);
    }
});
```

That requires a lot of syntax for just calling Math.max. That's where lambda expressions come into play. Since Java 8 it is allowed to do the same thing in a much shorter way:
```java
reduce((int left, int right) -> Math.max(left, right));
```

But as `Math.max(int, int)` itself fulfills the formal requirements of `IntBinaryOperator`, it can be used directly. Because Java 7 does not have any syntax that allows a method itself to be passed as an argument (you can only pass method results, but never method references), the `::` syntax was introduced in Java 8 to reference methods:
```java
reduce(Math::max);
```

> Note that this will be interpreted by the compiler, not by the JVM at runtime.

## Lambda Expression
A lambda expression is a short block of code which takes in parameters and returns a value. Lambda expressions are similar to methods, but they do not need a name and they can be implemented right in the body of a method.

The simplest lambda expression contains a single parameter and an expression:

```java
parameter -> expression
```

To use more than one parameter, wrap them in parentheses:
```java
(parameter1, parameter2) -> expression
```

Expressions are limited. They have to immediately return a value, and they cannot contain variables, assignments or statements such as if or for. In order to do more complex operations, a code block can be used with curly braces. If the lambda expression needs to return a value, then the code block should have a return statement.
```java
(parameter1, parameter2) -> { code block }
```

## Recursion
Recursion is the technique of making a function call itself. This technique provides a way to break complicated problems down into simple problems which are easier to solve.

Recursion may be a bit difficult to understand. The best way to figure out how it works is to experiment with it.

### Recursion Example
Adding two numbers together is easy to do, but adding a range of numbers is more complicated. In the following example, recursion is used to add a range of numbers together by breaking it down into the simple task of adding two numbers:

#### Example
Use recursion to add all of the numbers up to 10.

```java
public class Main {
  public static void main(String[] args) {
    int result = sum(10);
    System.out.println(result);
  }
  public static int sum(int k) {
    if (k > 0) {
      return k + sum(k - 1);
    } else {
      return 0;
    }
  }
}
```

#### Example Explained
When the `sum()` function is called, it adds parameter `k` to the sum of all numbers smaller than `k` and returns the result. When `k` becomes 0, the function just returns 0. When running, the program follows these steps:

```
10 + sum(9)
10 + ( 9 + sum(8) )
10 + ( 9 + ( 8 + sum(7) ) )
...
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + sum(0)
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + 0
```

Since the function does not call itself when `k` is 0, the program stops there and returns the result.

### How is recursion implemented in Java?
To understand what’s happening, we must look at how Java handles method calls. When a method is called, Java suspends what it is currently doing and pushes the environment on the stack to make place for the called method execution. When this method returns, Java pops the stack to restore the environment and resume program execution. If we call one method after the other, the stack will always hold at least one of these methods call environment.

But methods are not only composed by calling them one after the other. Methods call methods. If `method1` calls `method2` as part of its implementation, Java again suspends `method1` execution, pushes the current environment on the stack, and starts executing `method2`. When `method2` returns, Java pops the last pushed environment from the stack and resume execution (of `method1` in our case). When `method1` completes, Java pops again from the stack and resume what it was doing before calling this method.

Of course, method calls may be deeply nested. Is there a limit to method nesting depth? Yes. The limit is the size of the stack. In current situations, the limit is somewhere around a few thousands of levels, although it is possible to increase this limit by configuring the stack size. However, the same stack size is used for all threads, so increasig the stack size for a single computation will generally waste space. Default stack size varies between 320k and 1024k depending on the version of Java and the system used. For a 64 bits Java 8 program with minimal stack usage, the maximum number of nested method calls is about 7 000. Generally, we don’t need more, excepted in very specific cases. One such case is recursive method calls.

Tail Call Elimination (TCE)Pushing the environment on the stack seems necessary in order to allow resuming computation after the called method returns. But not always. When the call to a method is the last thing to do in the calling method, there is nothing to resume when it returns, so it should be OK to resume directly with the caller of the current method instead of the current method itself. A method call occurring in last position, meaning as the last thing to do before returning, is called a tail call. Avoiding pushing the environment to the stack to resume method processing after a tail call is an optimization technique known as Tail Call Elimination (TCE). Unfortunately, Java does not implement TCE.

Tail Call Elimination is sometimes called Tail Call Optimization (TCO). TCE is generally an optimization, and we may live without it. However, when it comes to recursive function calls, TCE is no longer an optimization. It is a mandatory feature. That’s why TCE is a better term than TCO when it comes to handling recursion.

## Abstract Class
An abstract class is a class that cannot be instantiated.

### Abstract Class vs Interface
- An __Abstract Class__ is used to share code among several classes, if several classes have methods in common.
- An __Interface__ is used if several unrelated classes share the same interface.

## Generic Type
With __generic types__ you can specify the type of data on which a class operates by passing the required type as a parameter (`<T>`).
```java
package it.html.java.generics;
public class Bottiglia<T> {
	private T contenuto;
	public Bottiglia(T t){
		contenuto=t;
	}
	public T getContenuto() {
		return contenuto;
	}
}
```