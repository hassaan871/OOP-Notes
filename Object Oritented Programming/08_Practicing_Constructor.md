# 📚 Constructors in Java

## 🔑 Key Points

- A constructor is a special method that gets called when an object is created
- Constructors have the same name as the class
- Constructors don't have a return type
- Constructors can be overloaded (multiple constructors with different parameters)
- Constructors are usually public but can be private too

## 🏗️ Types of Constructors

1. **Non-parameterized constructor** - Takes no arguments, sets default values
2. **Parameterized constructor** - Takes arguments to initialize object properties
3. **Single parameter constructor** - Special case for specific scenarios (like square)

## 💻 Code Example: Rectangle Class

```java
class Rectangle {
    // Properties
    private double length;
    private double breadth;
    
    // Non-parameterized constructor
    public Rectangle() {
        length = 1;
        breadth = 1;
    }
    
    // Parameterized constructor with two parameters
    public Rectangle(double l, double b) {
        setLength(l);
        setBreadth(b);
    }
    
    // Single parameter constructor (for square)
    public Rectangle(double s) {
        length = s;
        breadth = s;
    }
    
    // Getter and Setter methods
    public double getLength() {
        return length;
    }
    
    public void setLength(double l) {
        if (l > 0)
            length = l;
        else
            length = 0;
    }
    
    public double getBreadth() {
        return breadth;
    }
    
    public void setBreadth(double b) {
        if (b > 0)
            breadth = b;
        else
            breadth = 0;
    }
    
    // Utility methods
    public double area() {
        return length * breadth;
    }
    
    public double perimeter() {
        return 2 * (length + breadth);
    }
    
    public boolean isSquare() {
        return length == breadth;
    }
}
```

## 📝 Using Constructors in Main Class

```java
public class TestRectangle {
    public static void main(String[] args) {
        // Using non-parameterized constructor
        Rectangle r1 = new Rectangle();
        
        // Using parameterized constructor (two parameters)
        Rectangle r2 = new Rectangle(10, 5);
        
        // Using parameterized constructor (one parameter - square)
        Rectangle r3 = new Rectangle(10);
        
        // Using parameterized constructor with validation
        Rectangle r4 = new Rectangle(-10, -5); // Will set values to 0
        System.out.println(r4.area()); // Output: 0
        
        Rectangle r5 = new Rectangle(10, 5);
        System.out.println(r5.area()); // Output: 50
    }
}
```

## 🔍 Complete Class Components
- Properties (private variables)
- Constructors (multiple types)
- Getter/Setter methods (property methods)
- Utility methods (area, perimeter)
- Inquiry methods (isSquare)

## 💡 Best Practices
- Use constructors to initialize object properties
- Validate parameters in constructors or setter methods
- Constructors can call setter methods for validation
- Create specialized constructors for common use cases