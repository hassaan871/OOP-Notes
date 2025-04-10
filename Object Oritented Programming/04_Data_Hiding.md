# Data Hiding in Java 🔐

## Introduction 🎯
- Data hiding is an important concept in object-oriented programming
- Similar to engineering products (TVs, cars) where internal components are hidden
- Only the operations are visible to the user, not the internal implementation
- Makes code more secure and well-organized ✅

## Why Data Hiding? 🤔
- Makes usage simpler for end users 👥
- Hides complexity of implementation 🧩
- Follows good engineering principles 🛠️
- Protects data from misuse 🛡️

## Real-World Analogies 🌍

### Television Example 📺
- Users interact with buttons (operations)
- Actual operations are performed by circuitry (data) hidden inside
- Users don't need to understand internal circuitry to use the TV
- Similar to methods (buttons) operating on hidden data in programming

### Car Example 🚗
- Users operate steering and pedals (operations)
- Engine (data) is hidden under the hood
- Operations are performed on the engine, but users don't directly access it
- Makes driving easier as users don't need to understand engine mechanics

## Data Hiding in Programming 💻
- Similar principle applies to software development
- Hide data (variables/properties) 🙈
- Expose only operations (methods/functions) 👐
- All methods of a class use the data members or properties of the class

## How to Implement Data Hiding in Java ☕

### Example: Rectangle Class 📏

Basic structure:
```java
class Rectangle {
    // Data members/properties
    private int length;
    private int breadth;
    
    // Methods/operations
    public int area() {
        return length * breadth;
    }
    
    public int perimeter() {
        return 2 * (length + breadth);
    }
}
```

### Key Steps: 🔑
1. Make data members private
   ```java
   private int length;
   private int breadth;
   ```

2. Provide property methods (getters/setters) for controlled access
   ```java
   // Getter for length
   public int getLength() {
       return length;
   }
   
   // Setter for length
   public void setLength(int l) {
       if(l > 0)
           length = l;
       else
           length = 0;  // Data validation
   }
   ```

## Property Methods (Getters and Setters) 🔄
- For reading data: `getXxx()` methods 📖
- For writing data: `setXxx()` methods ✍️
- Naming convention: `get` + property name, `set` + property name
- Allow for data validation and processing

### Benefits of Property Methods ✨
- Control how data is accessed and modified
- Enable data validation (e.g., preventing negative values) ✅
- Hide implementation details
- Maintain encapsulation

### Example of Validation in Setter 🛑
```java
public void setLength(int l) {
    if(l > 0)
        length = l;
    else
        length = 0;  // Set to 0 if negative value is passed
}
```

## Usage Example 🧪

```java
public class Test {
    public static void main(String[] args) {
        Rectangle r = new Rectangle();
        
        // Cannot access directly (data is hidden)
        // r.length = 10;  // ERROR: length is private ❌
        // r.breadth = 5;  // ERROR: breadth is private ❌
        
        // Use property methods instead
        r.setLength(10);
        r.setBreadth(5);
        
        // If we try to set negative values
        r.setLength(-10);  // Will set length to 0 due to validation
        
        // Access values using getters
        System.out.println(r.area());  // Calculate and display area
    }
}
```

## Advantages of Data Hiding 🏆
- Makes code more organized 📋
- Prevents data misuse 🚫
- Makes classes more maintainable 🔧
- Allows for data validation ✓
- Common practice in object-oriented programming 🧠
- Simplifies usage for client code 👍