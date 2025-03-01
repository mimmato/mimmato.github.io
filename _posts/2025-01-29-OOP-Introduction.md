---
title: Introduction to Object Oriented Programming, Inheritance and Polymorphism
date: 2025-01-29 00:00:00 +0800
categories: [Learning]
tags: [java, programming, oop, inheritance, polymorphism]     # TAG names should always be lowercase
---
**1. What is Object-Oriented Programming?**

### 1.1 Definition of Object-Oriented Programming
Object-Oriented Programming (OOP) is a programming paradigm that is based on the concept of "objects." These objects contain both data (attributes) and behavior (methods). OOP allows for better code organization, reuse, and scalability. It is widely used in modern programming languages like Java, C++, and Python.

### 1.2 Real-Life Example of OOP Using Cars
Consider a car as an object in OOP. A car has:
- **Attributes (data):** brand, model, color, speed
- **Methods (behavior):** accelerate(), brake(), honk()

Each car object can have different values for its attributes but shares common methods, demonstrating how OOP models real-world entities.

---

**2. Basic Principles of Object-Oriented Programming**

### 2.1 Encapsulation
**Definition:** Encapsulation is the practice of restricting direct access to some data within a class and providing controlled access through methods. This protects the integrity of the object's data.

**Example (Using Cars):**
```java
class Car {
    private String brand;
    
    public Car(String brand) {
        this.brand = brand;
    }
    
    public String getBrand() {
        return brand;
    }
}
```
Here, the `brand` attribute is private and can only be accessed through the `getBrand()` method.

### 2.2 Abstraction
**Definition:** Abstraction is the process of hiding complex implementation details and exposing only the necessary features of an object.

**Example (Using Cars):**
```java
abstract class Car {
    abstract void drive();
}
class Tesla extends Car {
    void drive() {
        System.out.println("The Tesla is driving automatically.");
    }
}
```
Users of the `Car` class do not need to know the details of how `drive()` is implemented.

### 2.3 Inheritance
**Definition:** Inheritance allows one class (child) to inherit properties and behaviors from another class (parent), promoting code reuse.

**Example (Using Cars):**
```java
class Vehicle {
    String type = "Car";
}
class Sedan extends Vehicle {
    String model = "Toyota";
}
```
Here, `Sedan` inherits the `type` attribute from `Vehicle`.

### 2.4 Polymorphism
**Definition:** Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables a single interface to be used for different underlying forms.

**Example (Using Cars):**
```java
class Car {
    void start() {
        System.out.println("Car is starting");
    }
}
class Tesla extends Car {
    void start() {
        System.out.println("Tesla is starting silently");
    }
}
```
A `Tesla` object can be treated as a `Car` object while having its own unique behavior.

---

**Focusing on Inheritance and Polymorphism**
In the next sections, we will explore **Inheritance** and **Polymorphism** in greater depth, as they are fundamental in building scalable and reusable applications.

---

**3. Inheritance in More Detail**

### 3.1 Keyword `super`
**Definition:** The `super` keyword is used to refer to the parent class's attributes or methods.

**Example (Using Cars):**
```java
class Vehicle {
    String brand = "Generic";
}
class Car extends Vehicle {
    void displayBrand() {
        System.out.println(super.brand);
    }
}
```

### 3.2 `extends`
**Definition:** The `extends` keyword is used to establish inheritance between classes.

**Example:**
```java
class Vehicle {}
class Truck extends Vehicle {}
```
Here, `Truck` inherits all properties of `Vehicle`.

---

**4. Polymorphism in More Detail**

### 4.1 Method Overriding
**Definition:** Method overriding occurs when a subclass provides a specific implementation of a method that is already defined in its superclass.

**Example (Using Cars):**
```java
class Car {
    void drive() {
        System.out.println("Car is driving");
    }
}
class Tesla extends Car {
    void drive() {
        System.out.println("Tesla is driving autonomously");
    }
}
```

### 4.2 Method Overloading
**Definition:** Method overloading allows multiple methods in the same class to have the same name but different parameters.

**Example (Using Cars):**
```java
class Car {
    void start() {
        System.out.println("Car is starting");
    }
    void start(String mode) {
        System.out.println("Car is starting in " + mode + " mode");
    }
}
```
Here, both `start()` methods exist in the same class but accept different arguments.

---

**5. Relationship Between Inheritance and Polymorphism**

Inheritance and Polymorphism are closely linked:

```
Class Hierarchy:
    Vehicle
       |
   ---------
   |       |
  Car    Truck
   |
Tesla (Polymorphic)
```

- **Inheritance** allows a subclass to acquire attributes and behaviors from its parent.
- **Polymorphism** allows methods to be overridden in subclasses to provide specific implementations while maintaining a common interface.

By using these two principles together, developers can create flexible and scalable programs that model real-world behaviors effectively.

