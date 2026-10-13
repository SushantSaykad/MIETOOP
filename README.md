# OOP Syllabus
1. Introduction to Classes and Objects (Java): Introduction, Java Class Libraries,
Typical Java Development Environment, Memory Concepts, Arithmetic.
Classes, Objects, Methods and Instance Variables, Declaring a Class with a
Method and Instantiating an Object of a Class, Declaring a Method, Instance
variables, set Methods and get Methods, Primitive Types vs. Reference type
double Types, Initializing Objects with Constructors, floating point numbers.
Contro Statements and Array

2. Modulization in Java: Java Package, importing packages, Methods: static
methods, static Fields, scope of declaration, method overloading, and Java API
packages.
   
3. Inheritance and Polymorphism in Java: Inheritance: Super classes and
Subclasses, protected members, relationship between super classes and
subclasses, constructors in subclasses, object class. Polymorphism: Abstract
classes and methods, final methods and classes, polymorphism examples, and
Interfaces.
   
4. Exception-handling: Exception-handling overview, handling Arithmetic
Exceptions and Input Mismatch Exceptions, when to use exception handling,
Java exception hierarchy, finally block. Java Iterator Methods Parametrized
Classes in Java.
   

# MIETOOP
Miet OOP Practical
# Java Programming Practical Programs

This repository contains 11 Java practical programs covering operators, classes, methods, constructors, arrays, inheritance, polymorphism, interfaces, exception handling, packages, GUI programming, and collections.

## Table of Contents

1. Operators, Arithmetic Promotion, and Method Calling
2. String and Math Classes
3. Function Concepts
4. Arrays
5. String and Math Classes — Additional Examples
6. Inheritance and Polymorphism
7. Interfaces, Initializers, Final Modifier, and Binding
8. Exception Handling
9. Packages and Interfaces
10. GUI Using Swing and Action Listeners
11. List, Set, Map, Enhanced For-Loop, and Iterator

---

## 1. Operators, Arithmetic Promotion, and Method Calling

**Aim:** To demonstrate arithmetic operators, arithmetic promotion, and method calling.

**File:** `OperatorDemo.java`

```java
public class OperatorDemo {
    static void showResult(int value) {
        System.out.println("Method received: " + value);
    }

    public static void main(String[] args) {
        int a = 10, b = 3;

        System.out.println("Addition: " + (a + b));
        System.out.println("Subtraction: " + (a - b));
        System.out.println("Multiplication: " + (a * b));
        System.out.println("Division: " + (a / b));
        System.out.println("Remainder: " + (a % b));

        byte x = 10, y = 20;
        int result = x + y;

        System.out.println("Arithmetic promotion: " + result);

        showResult(result);
    }
}
```

## 2. String and Math Classes

**Aim:** To demonstrate the methods of the `String` and `Math` classes.

**File:** `StringMathDemo.java`

```java
public class StringMathDemo {
    public static void main(String[] args) {
        String text = "Hello Java";

        System.out.println("Text: " + text);
        System.out.println("Length: " + text.length());
        System.out.println("Uppercase: " + text.toUpperCase());
        System.out.println("Lowercase: " + text.toLowerCase());
        System.out.println("Character: " + text.charAt(1));
        System.out.println("Contains Java: " + text.contains("Java"));

        System.out.println("Square root: " + Math.sqrt(64));
        System.out.println("Power: " + Math.pow(2, 3));
        System.out.println("Absolute value: " + Math.abs(-25));
        System.out.println("Maximum: " + Math.max(10, 20));
        System.out.println("Rounded value: " + Math.round(4.6));
    }
}
```

## 3. Function Concepts

**Aim:** To demonstrate method overloading, constructors, default-like parameters, and returning object references.

**File:** `FunctionConcepts.java`

```java
class Student {
    String name;
    int marks;

    // Default constructor
    Student() {
        name = "Unknown";
        marks = 0;
    }

    // Parameterized constructor
    Student(String name, int marks) {
        this.name = name;
        this.marks = marks;
    }

    // User-defined copy constructor
    Student(Student other) {
        this.name = other.name;
        this.marks = other.marks;
    }

    void display() {
        System.out.println("Name: " + name + ", Marks: " + marks);
    }
}

public class FunctionConcepts {
    // Method overloading
    static int add(int a, int b) {
        return a + b;
    }

    static int add(int a, int b, int c) {
        return a + b + c;
    }

    // Default-like parameter using method overloading
    static void greet() {
        greet("Student");
    }

    static void greet(String name) {
        System.out.println("Hello, " + name);
    }

    // Returning an object reference
    static Student getStudent() {
        return new Student("Asha", 90);
    }

    public static void main(String[] args) {
        System.out.println("Sum: " + add(2, 3));
        System.out.println("Sum: " + add(2, 3, 4));

        Student s1 = new Student();
        Student s2 = new Student("Rahul", 85);
        Student s3 = new Student(s2);

        s1.display();
        s2.display();
        s3.display();

        greet();
        greet("Riya");

        Student s4 = getStudent();
        s4.display();
    }
}
```

**Note:** Java does not support default parameters or C++-style reference return types. Method overloading can provide default-like behavior, and Java methods can return object references.

## 4. Arrays

**Aim:** To initialize, display, and calculate the sum of array elements.

**File:** `ArrayDemo.java`

```java
public class ArrayDemo {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int sum = 0;

        System.out.println("Array elements:");

        for (int number : numbers) {
            System.out.println(number);
            sum += number;
        }

        System.out.println("Sum = " + sum);
        System.out.println("Array length = " + numbers.length);
    }
}
```

## 5. String and Math Classes — Additional Examples

**Aim:** To demonstrate additional methods of the `String` and `Math` classes.

**File:** `StringMathExtra.java`

```java
public class StringMathExtra {
    public static void main(String[] args) {
        String first = "Java";
        String second = "Java";
        String sentence = "Programming in Java";

        System.out.println("Strings equal: " + first.equals(second));
        System.out.println("Substring: " + sentence.substring(15));
        System.out.println("Replace: " + sentence.replace("Java", "C++"));
        System.out.println("Index of Java: " + sentence.indexOf("Java"));

        System.out.println("Ceiling: " + Math.ceil(4.2));
        System.out.println("Floor: " + Math.floor(4.8));
        System.out.println("Sine: " + Math.sin(0));
        System.out.println("Random number: " + Math.random());
    }
}
```

## 6. Inheritance and Polymorphism

**Aim:** To demonstrate inheritance and runtime polymorphism using method overriding.

**File:** `InheritancePolymorphism.java`

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class InheritancePolymorphism {
    public static void main(String[] args) {
        Animal animal;

        animal = new Dog();
        animal.sound();

        animal = new Cat();
        animal.sound();
    }
}
```

## 7. Interfaces, Initializers, Final Modifier, and Binding

**Aim:** To demonstrate interfaces, initializer blocks, the `final` modifier, and static and dynamic binding.

**File:** `InterfaceBindingDemo.java`

```java
interface Printable {
    void print();
}

class Report implements Printable {
    static {
        System.out.println("Static initializer executed");
    }

    {
        System.out.println("Instance initializer executed");
    }

    final int pages = 5;

    @Override
    public void print() {
        System.out.println("Report pages: " + pages);
    }

    static void category() {
        System.out.println("Static method: Report");
    }
}

class SpecialReport extends Report {
    @Override
    public void print() {
        System.out.println("Printing a special report");
    }
}

public class InterfaceBindingDemo {
    public static void main(String[] args) {
        Report.category();

        Printable item = new SpecialReport();
        item.print();

        final int limit = 100;
        System.out.println("Final limit: " + limit);
    }
}
```

**Explanation:**
- **Interface:** Defines methods that implementing classes provide.
- **Static initializer:** Runs when the class is initialized.
- **Instance initializer:** Runs when an object is created.
- **Final modifier:** Prevents reassignment of a final variable.
- **Static binding:** Static methods are resolved at compile time.
- **Dynamic binding:** Overridden instance methods are selected at runtime.

## 8. Exception Handling

**Aim:** To demonstrate exception handling using `try`, `catch`, and `finally`.

**File:** `ExceptionHandlingDemo.java`

```java
import java.util.Scanner;
import java.util.InputMismatchException;

public class ExceptionHandlingDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter numerator: ");
            int a = sc.nextInt();

            System.out.print("Enter denominator: ");
            int b = sc.nextInt();

            int result = a / b;
            System.out.println("Result = " + result);

        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero is not allowed.");

        } catch (InputMismatchException e) {
            System.out.println("Error: Enter integers only.");

        } finally {
            System.out.println("Execution completed.");
            sc.close();
        }
    }
}
```

## 9. Packages and Interfaces

**Aim:** To create a package, access it from another package, and implement an interface.

**Directory structure:**

```text
PackageDemo/
├── tools/
│   └── Message.java
└── app/
    └── Main.java
```

**File:** `tools/Message.java`

```java
package tools;

public class Message {
    public void show() {
        System.out.println("Hello from the tools package!");
    }
}
```

**File:** `app/Main.java`

```java
package app;

import tools.Message;

interface Greeting {
    void greet();
}

class EnglishGreeting implements Greeting {
    @Override
    public void greet() {
        System.out.println("Hello from the implemented interface!");
    }
}

public class Main {
    public static void main(String[] args) {
        Message message = new Message();
        message.show();

        Greeting greeting = new EnglishGreeting();
        greeting.greet();
    }
}
```

**Compile and run:**

Open a terminal inside the `PackageDemo` directory.

```bash
javac tools/Message.java app/Main.java
java app.Main
```

## 10. GUI Using Swing and Action Listeners

**Aim:** To create a GUI using `JFrame`, `JButton`, `JLabel`, and `JTextField`, and handle events using an action listener.

**File:** `SimpleGUI.java`

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class SimpleGUI extends JFrame implements ActionListener {
    private final JTextField nameField;
    private final JLabel resultLabel;
    private final JButton greetButton;

    public SimpleGUI() {
        setTitle("Simple Java GUI");
        setSize(350, 180);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        add(new JLabel("Enter your name:"));

        nameField = new JTextField(15);
        add(nameField);

        greetButton = new JButton("Greet");
        greetButton.addActionListener(this);
        add(greetButton);

        resultLabel = new JLabel("Enter a name and click Greet.");
        add(resultLabel);

        setLocationRelativeTo(null);
        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        String name = nameField.getText().trim();

        if (name.isEmpty()) {
            resultLabel.setText("Please enter your name.");
        } else {
            resultLabel.setText("Hello, " + name + "!");
        }
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(SimpleGUI::new);
    }
}
```

**Compile and run:**

```bash
javac SimpleGUI.java
java SimpleGUI
```

A desktop environment is required to display the GUI.

## 11. List, Set, Map, Enhanced For-Loop, and Iterator

**Aim:** To demonstrate `List`, `Set`, and `Map`, using an enhanced for-loop and an `Iterator`.

**File:** `CollectionsDemo.java`

```java
import java.util.*;

public class CollectionsDemo {
    public static void main(String[] args) {
        // List allows duplicate elements
        List<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");
        fruits.add("Apple");

        // Set stores unique elements
        Set<String> cities = new LinkedHashSet<>();
        cities.add("Pune");
        cities.add("Mumbai");
        cities.add("Pune");

        // Map stores key-value pairs
        Map<Integer, String> students = new LinkedHashMap<>();
        students.put(101, "Asha");
        students.put(102, "Rahul");
        students.put(103, "Neha");

        System.out.println("List using enhanced for-loop:");
        for (String fruit : fruits) {
            System.out.println(fruit);
        }

        System.out.println("\nSet using Iterator:");
        Iterator<String> iterator = cities.iterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }

        System.out.println("\nMap using enhanced for-loop:");
        for (Map.Entry<Integer, String> entry : students.entrySet()) {
            System.out.println(
                "Roll: " + entry.getKey()
                + ", Name: " + entry.getValue()
            );
        }
    }
}
```

**Explanation:**
- **List:** Ordered collection that allows duplicates.
- **Set:** Collection that stores unique elements.
- **Map:** Stores key-value pairs with unique keys.
- **Enhanced for-loop:** Iterates through collection elements.
- **Iterator:** Traverses elements using `hasNext()` and `next()`.

---

## How to Compile and Run

Install the Java Development Kit (JDK). Check the installation:

```bash
java -version
javac -version
```

Compile and run a program:

```bash
javac OperatorDemo.java
java OperatorDemo
```

Replace `OperatorDemo` with the class name of the program you want to execute. The `.java` filename must match the public class name.

For the package example, use the special commands in Section 9.

## Topics Covered

- Operators and arithmetic promotion
- Method calling and method overloading
- String and Math classes
- Constructors and object references
- Arrays
- Inheritance and polymorphism
- Interfaces and initializer blocks
- Final modifier and binding
- Exception handling
- Packages
- GUI programming using Swing
- Collections: List, Set, and Map
- Enhanced for-loop and Iterator

## Author

Add your name and GitHub profile here.
