# 🧑‍💻 How to Write a Class in Java

## 📌 Recap
- Every **object** has:
  - **🔑 Properties** (variables)
  - **⚙️ Methods** (functions)

## 🧠 Identifying Properties and Methods
- Analyze real-world objects.
- Determine what characteristics (properties) and actions (methods) they have.

## 🧪 Examples of Objects and Classes

### 🔵 Circle
```java
class Circle {
    double radius;

    double area() {
        return 3.14 * radius * radius;
    }

    double perimeter() {
        return 2 * 3.14 * radius;
    }
}
