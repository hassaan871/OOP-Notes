# 🏗️ Constructors in Java

## 🤔 Why Do We Need Constructors?

* When we create objects, properties start with default values (zero/null)
* In real-world objects (cars, TVs), properties have initial values when created
* We want to initialize object properties at creation time
* Example: A rectangle should have length and width set when created, not zero values by default

## 📝 What is a Constructor?

* A method of a class that is **automatically called** whenever an object is created
* Has the **same name as the class**
* Does **not** have a return type (not even void)
* Usually declared as **public** (can be private in special cases)
* Used to initialize object properties

## 🔄 Default Constructor

* Every class in Java has a default constructor provided by the compiler
* If you define your own constructor, the default constructor is removed
* The default constructor takes no parameters

## 💻 Constructor Example

```java
public class Rectangle {
    private double length;
    private double breadth;
    
    // Non-parameterized constructor
    public Rectangle() {
        length = 1;
        breadth = 1;
    }
    
    // Parameterized constructor
    public Rectangle(double l, double b) {
        length = l;
        breadth = b;
    }
    
    // Method to calculate area
    public double area() {
        return length * breadth;
    }
}
```

## 🔢 Types of Constructors

1. **Non-parameterized Constructor**
   * Takes no arguments
   * Replacement for default constructor
   * Example: `public Rectangle()`

2. **Parameterized Constructor**
   * Takes arguments to initialize properties
   * Example: `public Rectangle(double l, double b)`

## 📌 Key Points

* Constructors can be overloaded (multiple constructors with different parameters)
* Constructor overloading follows the same rules as method overloading
* Constructor name must be exactly the same as the class name
* No return type specified for constructors

## 🧩 Using Constructors

```java
// Using non-parameterized constructor
Rectangle r1 = new Rectangle();  // Creates rectangle with length=1, breadth=1
System.out.println(r1.area());   // Output: 1

// Using parameterized constructor
Rectangle r2 = new Rectangle(10, 5);  // Creates rectangle with length=10, breadth=5
System.out.println(r2.area());        // Output: 50
```