# **CHAPTER 1 CHEAT SHEET**

### **1. Computer & Program Basics**
*   **CPU (Central Processing Unit):** The brain of the computer that executes machine language instructions. It consists of the **Control Unit (CU)** and **Arithmetic Logic Unit (ALU)**.
*   **RAM (Main Memory):** Where programs and data are loaded for the CPU to execute.
*   **Program:** A sequence of instructions written in a programming language, compiled into machine language, and executed by the CPU.

### **2. Java Overview & History**
*   **Origin:** Developed by **James Gosling** at Sun Microsystems in 1995. Originally named **Oak**.
*   **WORA (Write Once, Run Anywhere):** Java code is compiled into bytecode, which can run on any platform that has a JVM, making it platform-independent.
*   **LTS (Long Term Supported):** Recommended versions for app development (e.g., Java 8, 11, 17, 21, 25).

### **3. Key Features of Java**
*   **Object-Oriented:** Everything is an object (except basic data types). Supports inheritance, polymorphism, encapsulation, and abstraction (but **no multiple inheritance**).
*   **Simple & Compact:** No pointers, no header files, and uses shorter syntax than C/C++.
*   **Robust & Secure:** Strict type checking, exception handling, and safe memory access (no pointers).
*   **Memory Management:** Automatic memory allocation and cleanup via the **Garbage Collector**.
*   **Multi-threaded:** Built-in support for running multiple threads simultaneously.

### **4. JVM, JRE, and JDK**
*   **JVM (Java Virtual Machine):** An engine that provides a runtime environment. It contains an **interpreter** that converts Java bytecode into machine-understandable code line by line.
*   **JRE (Java Runtime Environment):** Contains the JVM and the environment needed to *run* Java applications.
*   **JDK (Java Development Kit):** A full toolkit for developers. Includes the JRE, the compiler (`javac`), and other development tools.

### **5. The Compilation Process (Compiled + Interpreted)**
Unlike C/C++ which compiles directly to machine code, Java uses a two-step process:
1.  **Compiler (`javac`):** Converts `.java` source code into `.class` files containing bytecode.
2.  **Interpreter (`JVM`):** Executes the bytecode line by line into machine code.

### **6. Basic Syntax & Program Structure**
A typical Java program structure:
```java
package com.vncodelab;            // Specifies the directory/package
import java.util.Scanner;         // Imports necessary libraries

public class HelloWorld {         // Class declaration
    public static void main(String[] args) { // Program startup point
        System.out.println("Hello Java");    // Prints data to the console
    }
}
```
*   **`public`:** Access modifier allowing the method to be accessed from anywhere.
*   **`static`:** The method can be called without creating an object of the class.
*   **`void`:** The method does not return any value.
*   **`main`:** The entry point of the application.
*   **`String[] args`:** Used for command-line arguments.

### **7. Essential CLI Commands**
*   **Check Java version:** `java -version`
*   **Check Compiler version:** `javac -version`
*   **Compile a Java file:** `javac HelloWorld.java` (Creates `HelloWorld.class`)
*   **Run a compiled Java program:** `java HelloWorld`

### **8. Java vs C/C++**
| Feature | C/C++ | Java |
| :--- | :--- | :--- |
| **Platform** | Platform dependent | Platform Independent (JVM) |
| **Execution** | Direct to machine code | Compiled & Interpreted |
| **Pointers** | Supported | Not Supported |
| **Memory Allocation** | Manual (`malloc`/`new`) | Automatic (Garbage Collector) |
| **Multiple Inheritance** | Supported (C++) | Not Supported |

### **9. Development Tools**
*   **Professional IDEs:** NetBeans, Eclipse, IntelliJ IDEA.
*   **Online Compilers:** JDoodle, Programiz, W3Schools, etc., useful for quick practice.