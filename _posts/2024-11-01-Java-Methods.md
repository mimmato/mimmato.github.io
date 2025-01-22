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

Using `Car1.java` as an example, you will find that the class is defined as so in the beginning of the Car1.java file:

```
public class Car1 {

}
```

Testing push to github and actions after building jekyll 

## What is a Java Method?

A Method or Function is a piece of code defined in a program. It contains a set of instructions used to complete a task and is executed when called upon. A good example is the main method. It is the starting point for any Java program or class. 

The following image illustrates the anatomy of a Java Class and the contained Java Main method followed by a statement:

![Image](/github-pages/mimmato.github.io/assets/img/classAnatomy.jpg)

reference: 
*Kathy Sierra and Bert Bates. 2005. Head First Java, 2nd Edition. O'Reilly & Associates, Inc., USA.*

Continuing with the `Car1.java` file example, you will find that within the class defined as Car1, we now have our `Main` method initialized, followed by a statement:

```
public class Car1 {
    public static void main(String[] args) {
        System.out.println("This is the main method of the Car1 class.");
    }
}
```

#### Main Method syntax:

    public static void main(String[] args) {
    }


The benefits of using or defining methods include:

- Code resusability 
- Code
- Code readbility 


Code structure:

Source file (src) -> class file -> method -> statement 


Method overloading 


### Syntax 



## Java Method Syntax




## Printing:

Basic syntax

`System.out.println("Hello world!");`

Common shortcuts used in IDEs like IntelliJ and NetBeans:

`sout` + `TAB`

## Reading input:

#### Scanner tool:

`import java.util.Scanner;`

##### Scanner tool method:

`scanner.nextLine()`

## Concatenation:

## Strings:

String literal
String variable

## Reading Strings:

## Variable types in Java:

String
double
int
boolean



command.valueOf

Integer.valueOf
Boolean.valueOf
Double.valueOf

converting strings 


 if the program handles both the sum of the numbers and their total count as integers, one (or both) of the variables should be casted to a floating-point number by multiplying it by 1.0 before the division.


## Conditional statements and conditional operation


Strings equals

The equals command is written after a string by attaching it to the string to be compared with a dot. The command is given a parameter, which is the string that the variable will be compared against. If the string variable is being directly compared with a string, then the string can be placed inside the parentheses of the equals-command within quotation marks. Otherwise, the name of the string variable that holds the string to be compared is placed inside the parentheses.


    > greater than
    >= greater than or equal to
    < less than
    <= less than or equal to
    == equal to
    != not equal to



Logical Operators




## Loops



## Primitive types (variables)