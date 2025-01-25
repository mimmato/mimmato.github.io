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

A Method or Function is a piece of code defined in a program. It contains a set of instructions used to complete a task and is executed <u>when called upon</u>. 

The following image illustrates the anatomy of a Java Class and the contained Java Main method followed by a statement:

![Image](assets/img/classAnatomy.jpg)

image source: 
*Kathy Sierra and Bert Bates. 2005. Head First Java, 2nd Edition. O'Reilly & Associates, Inc., USA.*

#### Main Method declaration, signature & syntax:

An example of a method is the main method. It is the special type of method used as a starting point for any Java program or class. Continuing with the `Car1.java` file example, you will find that within the class defined as Car1, we now have our `Main` method initialized, followed by a statement:

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

**NOTE** The signature of the Main method is not a subject to change. For example, the main method of a Java program can only return `void`. To specify a different return type, you have to add it as a separte method called within the `main` method.

The following is meant to illustrate other parts of a Method signature and the elements that can be included:

**`Access modifier`**: controls the level of access of the set method. It can be specified as `public`, `private` and `protected`:

```java
    public static void regularMethod ( String[] args) {}
    private static void regularMethod ( String[] args) {}
    protected static void regularMethod ( String[] args) {}
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
#### Method overloading 
Method overloading is used when you want to bring more functionality out of the same method. It is important to note that to overload a method, you must:
- preserve the method name throughout your declarations
- ensure that the method parameters differ each time the method is declared

Let's take the `carSpeed();` method we declared previously as an example and overload it:

```java
public class Car1 {
public static void main(String[] args) {
        String message = carSpeed();
        System.out.println(message);
        System.out.println("-------------------------");

        String message2 = carSpeed(120);
        System.out.println(message2);
        System.out.println("-------------------------");

        String message3 = carSpeed(120, "Toyota");
        System.out.println(message3);

    }
public static String carSpeed() {
        System.out.println("First declaration of carSpeed(); without arguments in the parameters list.");
        return "This will not return anything as there are no method parameters specified."; 
    }

public static String carSpeed(int speed) {
        System.out.println("Second declaration of carSpeed(); with a parameter 'int speed'.");
        return "This returns speed - " + speed + " km/h"; 
    }

public static String carSpeed(int speed, String model) {
        System.out.println("Third declaration of carSpeed(); with parameters 'int speed' and 'String model'.");
        return "This returns speed - " + speed + " km/h and model - " + model;
    }    
}
```

example output:

```
First declaration of carSpeed(); without arguments in the parameters list.
This will not return anything as there are no method parameters specified.
-------------------------
Second declaration of carSpeed(); with a parameter 'int speed'.
This returns speed - 120 km/h
-------------------------
Third declaration of carSpeed(); with parameters 'int speed' and 'String model'.
This returns speed - 120 km/h and model - Toyota
```

In the above example, we duplicated the same method named `carSpeed();` 3 times, but passed different parameters in the parentheses to expand the method's functionality. We also added arguments or values, so we can visualize and make sense of the methods' parameters when printing.

## Java object

So far, we have created **classes** and **methods**. We discussed their structure and some of their characteristics. In other words, we have set up a blueprint (classes) to create an object and we have also added some action (methods) for our object, but we are yet to create the actual object:

```java
public class Car1 {
    private String model;

    public static void main(String[] args) {
        // Create a Car1 object
        Car1 myCar = new Car1();

        // Set the car model
        myCar.model = "Toyota";

        // Print the car model
        System.out.println("Car model: " + myCar.model);
    }
}
```
example output:

```
Car model: Toyota
```

Expanding on our previous example, we have now initialized our first object named `myCar`. We use the keyword **new** to create it and point it to our class **Car1**.
Next, we define a new variable within our Car1 class named `model` and assign it to our new object (myCar) just so we have something to print out in the example other than null. The actual value in this case is `"Toyota"`.

The following analogy might help to better understand the relationship between the 3 components:

```java
Class: Car1
  ↳ Blueprint (defines attributes and behavior)

Object: myCar
  ↳ Created from the Class (Car1)
  ↳ Contains specific data (e.g., myCar.model = "Toyota";)

Method: main(String[] args)
  ↳ Action the object can perform (creates the myCar object, sets the model to "Toyota") 
  ```

#### Java attribute

In our previous example, we created an object named `myCar` in our `Car1` class and had the main method print a variable - **Toyota**. That variable we printed was actually an attribute that we assigned to our object named `myCar.model`:

```
myCar.model = "Toyota";
```
What we have here is the object **myCar** with an assigned attribute named **model** which holds the **"Toyota"** variable. We can now expand our object with different attributes like **color**, **engine**, **year** etc.

## Java Constructor

In Java, a **constructor** is a special type of method that is called when an object of the class is created. Its purpose is to initialize the object's state.

Example with **Car1** `class` and `main` method, followed by the **Car1** `constructor`:

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

- **`Car1`**: This is the **name of the constructor**, <u>which must match the class name!</u>

- **`(String model)`**: These are the **parameters** of the constructor, allowing the model to be passed during object creation.

- **`this.model = model;`**: This line initializes the object's model using the constructor's parameter.

**NOTE** Constructors do not have a return type.

Using a constructor, we now have a special type of method where we can set up our object's attributes:

```java
public Car1(String model) {
        this.model = model;
    }
```   

We no longer need to hardcode the value of our attribute when defining it, but can reference it in the object itself:

```java
        Car1 myCar = new Car1("Toyota");
        System.out.println("Car model: " + myCar.model);
```

**`this` keyword**: In the context of what we know so far (i.e. classes, methods, objects, constructors), we will use the **`this`** keyword when defining attributes within constructors to later refer to the object's variables. Using this keyword would also to avoid mistakes when calling out instance and local variables that share the same name. 

```java
public class Car1 {
    private String model;

    public static void main(String[] args) {
        // Create a Car1 object using the constructor
        Car1 myCar = new Car1("Honda");
        System.out.println("Car model: " + myCar.model);
    }

    // Constructor
    public Car1(String model) {
        // Using 'this' to refer to the instance variable when parameter has the same name
        this.model = model;  // 'this.model' refers to the instance variable, 'model' is the parameter
    }
}
```

example output:

```
Car model: Honda
```

If `this.model = model;` is not defined then our expected output would be **null** because the instance variable (**private String model;**) by that same name holds no value.

##  &nbsp;
#### Summary
##  &nbsp;

So far, we have went over **classes**, **objects**, **methods** & **constructors**. We have now defined the structure of applications using classes (blueprints) to create objects (instances), and define methods (actions) for the objects to perform; while **constructors** help us initialize objects efficiently, and manage underlying class attributes.

