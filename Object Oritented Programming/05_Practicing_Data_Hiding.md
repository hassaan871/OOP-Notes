# Practicing Data Hiding in Java 👨‍💻

## Demonstration Overview 🔍
- Practical implementation of data hiding using Rectangle class
- Converting public properties to private
- Creating getter and setter methods
- Adding validation logic

## Starting Point: Rectangle Class 📏
```java
class Rectangle {
    // Originally public properties
    public double length;
    public double breadth;
    
    // Methods
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

## Step 1: Make Properties Private 🔒
```java
class Rectangle {
    private double length;
    private double breadth;
    
    // Methods remain the same
}
```

- Once properties are marked private, they cannot be accessed directly from outside the class
- Attempting to access directly (like `r.length = 10;`) will cause compilation errors
- Error message: "length has private access in Rectangle"
- This achieves data hiding - properties are hidden from outside the class 🙈

## Step 2: Create Getter Methods 📖
```java
public double getLength() {
    return length;
}

public double getBreadth() {
    return breadth;
}
```

- Getter methods allow reading property values from outside the class
- Follow naming convention: `get` + PropertyName
- Return type matches property type

## Step 3: Create Setter Methods ✏️
```java
public void setLength(double l) {
    length = l;  // Simple version without validation
}

public void setBreadth(double b) {
    breadth = b;  // Simple version without validation
}
```

- Setter methods allow changing property values from outside the class
- Follow naming convention: `set` + PropertyName
- Take parameter of appropriate type
- Return type is typically void

## Step 4: Update Code to Use Getters and Setters 🔄
```java
public class Main {
    public static void main(String[] args) {
        Rectangle r = new Rectangle();
        
        // Old code (no longer works):
        // r.length = 10.5;
        // r.breadth = 5.5;
        
        // New code using setters:
        r.setLength(10.5);
        r.setBreadth(5.5);
        
        // Display results
        System.out.println(r.area());
        System.out.println(r.perimeter());
        System.out.println(r.isSquare());
        
        // Read values using getters
        System.out.println(r.getLength());
        System.out.println(r.getBreadth());
    }
}
```

## Step 5: Add Validation in Setters ✅
```java
public void setLength(double l) {
    if (l >= 0)
        length = l;
    else
        length = 0;  // Set to zero if negative value provided
}

public void setBreadth(double b) {
    if (b >= 0)
        breadth = b;
    else
        breadth = 0;  // Set to zero if negative value provided
}
```

- Validation ensures data integrity
- In this example, Rectangle dimensions cannot be negative
- If negative value is provided, it defaults to zero

## Testing the Validation Logic 🧪
```java
public class Main {
    public static void main(String[] args) {
        Rectangle r = new Rectangle();
        
        // Testing validation
        r.setLength(-10.5);  // Should set length to 0
        r.setBreadth(5.5);
        
        System.out.println(r.area());        // Should be 0 (0 × 5.5)
        System.out.println(r.perimeter());   // Should be 11 (2 × 5.5)
        System.out.println(r.isSquare());    // Should be false
        System.out.println(r.getLength());   // Should be 0
        System.out.println(r.getBreadth());  // Should be 5.5
    }
}
```

## Using Getters Inside Class Methods 🔄
- Within the class methods, you can either:
  - Access properties directly: `return length * breadth;`
  - Or use getters: `return getLength() * getBreadth();`
- Both approaches are valid inside the class

## Summary of Property Methods 📝
- Getter methods (for reading):
  - Named as `get` + PropertyName
  - Return property value
  - No parameters
- Setter methods (for writing):
  - Named as `set` + PropertyName
  - Return type is void
  - Take parameter to set property value
  - Can include validation logic

## Benefits of Data Hiding Demonstrated 🏆
- Controlled access to internal data
- Data validation to maintain integrity
- Ability to change internal implementation without affecting client code
- Proper encapsulation of class details
- Enhanced security of data