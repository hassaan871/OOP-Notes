# 📚 Types of Properties in Java

## 🔄 Read-Write Properties

* The most common type (90%+ of properties)
* Can both read and modify values
* Implemented with both getter and setter methods

### Examples:

```java
// Rectangle class example
public class Rectangle {
    private double length;
    
    public double getLength() {
        return length;
    }
    
    public void setLength(double length) {
        this.length = length;
    }
}

// Student class example
public class Student {
    private double m1; // Marks for subject 1
    
    public double getM1() {
        return m1;
    }
    
    public void setM1(double m1) {
        this.m1 = m1;
    }
}
```

## 📖 Read-Only Properties

* Can only read values, not modify them
* Implemented with only getter methods (no setters)
* Used for values that should never change after initialization

### Examples:

```java
// Student class with read-only roll number
public class Student {
    private int rollNo;
    
    // Roll number assigned once during admission (object creation)
    public Student(int rollNo) {
        this.rollNo = rollNo;
    }
    
    // Only getter, no setter allowed
    public int getRollNo() {
        return rollNo;
    }
}

// Account class with read-only account number
public class Account {
    private String accNo;
    
    // Account number assigned once when account is opened
    public Account(String accNo) {
        this.accNo = accNo;
    }
    
    // Only getter, no setter allowed
    public String getAccNo() {
        return accNo;
    }
}
```

## ✍️ Write-Only Properties

* Can only modify values, not read them
* Implemented with only setter methods (no getters)
* Rare but useful for producer-consumer scenarios
* Often used across different classes, threads, or programs

### Example:

```java
// Charity account example (write-only for donor)
public class CharityAccount {
    private double balance;
    
    // Only setter, no getter for donor class
    public void setBalance(double amount) {
        this.balance += amount; // Donor can add to balance
    }
    
    // Note: The charity organization might have additional methods
    // to both read and modify the balance
}

// Producer example
public class Producer {
    private int sharedData;
    
    // Only setter method
    public void setData(int d) {
        sharedData = d;
    }
}
```

## 💡 Key Concepts

* **Producer-Consumer Pattern**: One class produces (writes) values, another consumes (reads) them
* **Encapsulation**: Properties are private with controlled access through methods
* **Data Protection**: Using appropriate property types helps maintain data integrity

## 🔍 Use Cases Summary

| Property Type | Getter | Setter | Example Use Cases |
|---------------|--------|--------|------------------|
| Read-Write    | ✓      | ✓      | Most standard properties (length, marks) |
| Read-Only     | ✓      | ✗      | IDs, account numbers, immutable values |
| Write-Only    | ✗      | ✓      | Security-sensitive data, producer objects |