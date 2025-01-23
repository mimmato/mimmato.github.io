---
title: Java Method, Class & Constructor
date: 2025-01-22 00:00:00 +0800
categories: [Learning]
tags: [java, programming, method, class, constructor]     # TAG names should always be lowercase
---

## Java Class 

A class in Java is the fundamental building block of an application. Each class typically resides in its own .java file, and the file name should match the class name.

Classes are organized into packages, which provide a way to group related classes together. Java's package structure mirrors the file system, making it easier to manage large applications.

Below is a representation of how classes are structured in a typical Java project:

#### **Directory Structure Example**

<div style="display: flex; align-items: flex-start;">
  <pre style="margin-right: 20px;">
src/
└── package1/
    ├── Car1.java
    ├── Car2.java
    └── Car3.java
└── package2/
    ├── Dog1.java
    ├── Dog2.java
    └── Dog3.java
└── package3/
    ├── Class1.java
    ├── Class2.java
    └── Class3.java
  </pre>
  <div>
    <strong>Definitions:</strong>
    <ul>
      <li><strong>src/</strong>: The root directory that holds all the packages.</li>
      <li><strong>Packages</strong>: Each package (e.g., package1, package2, etc.) holds related classes.</li>
      <li><strong>Class Files</strong>: Each class file (e.g., Car1.java, Dog1.java, etc.) contains a class definition.</li>
    </ul>
  </div>
</div>

#### Class initialization & syntax

Using `Car1.java` as an example, you will find that the class is defined as so in the beginning of the Car1.java file:

```java
public class Car1 {
    // This is an example of a class in Java
}
```

**Definitions:**


- **`public`**: The access modifier. It makes this class accessible from anywhere.
- **`class`**: The keyword used to declare a class in Java.
- **`Car1`**: The name of the class. It must match the file name (Car1.java).
- **`{ }`**: The braces enclose the body of the class, where fields, methods, constructors, and other members are defined.

Classes can only use one of two modifiers:

- **`public`**: The class is accessible by any other class
- **`default`**: The class is only accessible by classes in the same package. This is used when you **don't** specify a modifier. 



## Java Method

A Method or Function is a piece of code defined in a program. It contains a set of instructions used to complete a task and is executed when called upon. A good example is the main method. It is the starting point for any Java program or class. 

The following image illustrates the anatomy of a Java Class and the contained Java Main method followed by a statement:

![Image](assets/img/classAnatomy.jpg)

image source: 
*Kathy Sierra and Bert Bates. 2005. Head First Java, 2nd Edition. O'Reilly & Associates, Inc., USA.*

#### Main Method initialization & syntax:

Continuing with the `Car1.java` file example, you will find that within the class defined as Car1, we now have our `Main` method initialized, followed by a statement:

```java
public class Car1 {
    public static void main(String[] args) {
        System.out.println("This is the main method of the Car1 class.");
    }
}
```

**Definitions:**

- **`public`**: This is an **access modifier**, indicating that the method can be accessed from outside the class (i.e., it is publicly accessible).

- **`static`**: This keyword means that the method belongs to the class itself rather than instances of the class. It can be called without creating an object of the class.

- **`void`**: This is the **return type** of the method. `void` means the method doesn't return any value.

- **`main`**: This is the **name** of the method. In this case, it's the entry point of a Java application, meaning this method is executed first when the program runs.

- **`(String[] args)`**: These are the **parameters** of the method. Here, `String[]` defines an array of `String` objects that can be passed to the method. `args` is the name of this array, and it allows command-line arguments to be passed to the program.

Other parameters and examples





Method overloading 
