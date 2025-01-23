---
title: Java Method, Class & Constructor
date: 2025-01-22 00:00:00 +0800
categories: [Learning]
tags: [java, programming, method, class, constructor]     # TAG names should always be lowercase
---

## Java Class and java file

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

#### Class declaration, signature & syntax:

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

A Method or Function is a piece of code defined in a program. It contains a set of instructions used to complete a task and is executed <u>when called upon</u>. A good example is the main method. It is the starting point for any Java program or class. 

The following image illustrates the anatomy of a Java Class and the contained Java Main method followed by a statement:

![Image](assets/img/classAnatomy.jpg)

image source: 
*Kathy Sierra and Bert Bates. 2005. Head First Java, 2nd Edition. O'Reilly & Associates, Inc., USA.*

#### Main Method declaration, signature & syntax:

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

**NOTE** that the main method of a Java program can only return `void`. To specify a different return type, you have to add it as a separte method called within `main`.

- **`main`**: This is the **name** of the method. In this case, it's the entry point of a Java application, meaning this method is executed first when the program runs.

- **`(String[] args)`**: These are the **parameters** of the method. Here, `String[]` defines an array of `String` objects that can be passed to the method. `args` is the name of this array, and it allows command-line arguments to be passed to the program.

The following is meant to illustrate other parts of the Method signature and the elements that can be included:

**`Access modifier`**: controls the level of access of the set method. It can be specified as `public`, `private` and `protected`:

```java
    public static void main ( String[] args) {}
    private static void main ( String[] args) {}
    protected static void main ( String[] args) {}
```

**`Return type`** : Other than `void`, the return type can be specified as of a specific <u>primitive</u> data type (int, char, short etc.) or <u>non-primitive</u>  (String, ArrayList, HashMap etc.).
The following example illustrates how a new method named `carSpeed();` is initialized within the main method. `carSpeed();` can now have its return type specified as `String`:

```java
public class Car1 {
public static void main(String[] args) {
        System.out.println("This is the main method of the Car1 class. The return type if always void");
        String message = carSpeed();
        System.out.println(message);
    }
public static String carSpeed() {
        System.out.println("This is the carSpeed method initialized in the main method.");
        return "The return type of this method is String."; // Return a string value
    }
}
```

**`return` keyword**: following the declaration of a return type different from `void`,  the `return` keyword is used within the body of a new method to return its value or result. You can refer to the previous example. 

**`Method name`** : written in camel case when using multiple words, method names are specified after the return type and before the parameters list:

```java
    public static void main ( String[] args) {}
    private static void methodName1 ( String[] args) {}
    protected static void methodName2 ( String[] args) {}
```

**`Parameter list`** : a list of input parameters, placed within the brackets `()` of the method signature:

```java
    public static void main(/*Parameters list i.e */
                                                String[] args
                                                int[] numbers
                                                String text
                                                int a, int b
                                                HashSet<String> hashSetList) {
    }
```

**`Exception throw`** : methods can throw exceptions to indicate that an error or unexpected condition has occurred. This is done using the `throws` keyword in the method signature followed by the Exception name:

```java
public class Car1 {

    public static void main(String[] args) throws Exception  {
        // throws is specified within the signature 

        System.out.println("This is the main method of the Car1 class.");

        // The key word `throw` is specified within the method body.
        throw new Exception ("Car won't start");
    }
}
```
Java uses built-in Exceptions and user-defined Exceptions. The above example illustrates the usage of a built-in Exception named **Exception** within the main method.

**`throw` keyword** : the keyword is needed within the body method and when an exception is specified within its signature in order for the instructions to be completed. 


**`Method body`** : enclosed in curly braces `{}`. This is where all statements of the set method goes:


```java
public class Car1 {
    public static void main(String[] args) {
       // Code or statements between the braces is part of the Method body.
       System.out.println("This statement is part of the method body.");
    }
}
```
// test deploy 

#### Method overloading 

## Java object

## Java Constructor

In Java, a **constructor** is a special type of method that is called when an object of the class is created. Its purpose is to initialize the object's state.

Example with Car1 `class` and `main` method, followed by the Car1 `constructor`:


```java
public class Car1 {
    public static void main(String[] args) {

        // Create a Car1 object using the constructor
        Car1 myCar = new Car1("Toyota");
        System.out.println("Car model: " + myCar.model);
    }

    private String model;

    // Constructor
    public Car1(String model) {
        this.model = model;
    }
}
```

**Definitions:**

- **`public`**: This is the **access modifier**, indicating that the constructor can be accessed from outside the class.

- **`Car1`**: This is the **name of the constructor**, which must match the class name.

- **`(String model)`**: These are the **parameters** of the constructor, allowing the model to be passed during object creation.

- **`this.model = model;`**: This line initializes the object's model using the constructor's parameter.

- **`main Method`**: The entry point of the program, which creates an object and prints its model.

**`this` keyword**:




 
