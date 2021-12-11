# Java and Object Oriented Approach

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

## Autoboxing and Unboxing
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