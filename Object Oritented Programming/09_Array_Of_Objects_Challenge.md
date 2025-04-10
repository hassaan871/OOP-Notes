# 📦 Array of Objects in Java

## 🔑 Key Points
- Arrays can store references to objects in Java
- Each array element is a reference (similar to pointers in C/C++)
- Objects need to be created separately and assigned to array elements

## 🏗️ Challenge: Student and Subject Classes

### 📚 Subject Class
```java
class Subject {
    // Properties
    private String subjectId;
    private String name;
    private int maxMarks;
    private int marksObtained;
    
    // Constructor
    public Subject(String subjectId, String name, int maxMarks) {
        this.subjectId = subjectId;
        this.name = name;
        this.maxMarks = maxMarks;
        this.marksObtained = 0; // Default value
    }
    
    // Getter methods
    public String getSubjectId() {
        return subjectId;
    }
    
    public String getName() {
        return name;
    }
    
    public int getMaxMarks() {
        return maxMarks;
    }
    
    public int getMarksObtained() {
        return marksObtained;
    }
    
    // Setter methods (only for marks)
    public void setMaxMarks(int maxMarks) {
        this.maxMarks = maxMarks;
    }
    
    public void setMarksObtained(int marksObtained) {
        this.marksObtained = marksObtained;
    }
    
    // Utility methods
    public boolean isQualified(int marks) {
        return marks >= maxMarks * 0.4; // 40% criteria
    }
    
    public boolean isQualified() {
        return marksObtained >= maxMarks * 0.4; // 40% criteria
    }
    
    // Display method
    @Override
    public String toString() {
        return "Subject ID: " + subjectId + ", Name: " + name + ", Marks Obtained: " + marksObtained;
    }
}
```

### 👨‍🎓 Student Class Requirements
- Properties:
  - Roll number
  - Name 
  - Department (e.g., CSE, Mechanical)
  - Array of subjects
- Required Methods:
  - Getters for all properties
  - Setters (where appropriate)
  - Constructor(s)
  - `setSubjects()` method with variable arguments

## 💻 Creating an Array of Objects

```java
public class Main {
    public static void main(String[] args) {
        // Create an array to hold references to Subject objects
        Subject[] subs = new Subject[3];
        
        // Create individual Subject objects and assign to array
        subs[0] = new Subject("S101", "Data Structures", 100);
        subs[1] = new Subject("S102", "Algorithms", 100);
        subs[2] = new Subject("S103", "Operating Systems", 100);
        
        // Display all subjects using loop
        for(Subject s : subs) {
            System.out.println(s);
        }
    }
}
```

## 📝 Diagram Explanation
```
subs → [0][1][2]  // Array of references
         ↓  ↓  ↓
         O1 O2 O3  // Actual Subject objects with properties
```

## 💡 Best Practices
- Remember to initialize each array element with a new object
- Use loops to process arrays of objects efficiently
- The `toString()` method helps display object information
- Use 'this' keyword when parameter names match property names

## 🎯 Challenge Tasks
1. Complete the Subject class (shown above)
2. Create the Student class with specified properties
3. Implement all required methods for Student class
4. Create an array of Subjects and assign to a Student
5. Display student information including subjects