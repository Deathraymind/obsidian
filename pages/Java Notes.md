### Function (Java)
- A block of code that completes a specific goal.
	- First, specify the return type of the function (often `void`).
	- Inside the parentheses of `void nameOfFunction()`, include the parameters.
	- The `main` function needs to exist so that it gets called.
- ### Class
- A container for related functions.
	- In Java, we define a class with the keyword `class` followed by curly braces `{}`.
	- When a function is outside of a class, it's referred to as a function. Inside a class, it's referred to as a **method**.
	- All classes should have an **access modifier**.
		- Access modifiers determine if other classes can call these methods (e.g., `public`, `private`, etc.).
- ### Basic Structure of a Java Program
  ```java
  public class Main {
    public void main() {
        // code here
    }
  }
  ```
- **Classes** should use the **PascalNamingConvention** while **methods** should use the **camelNamingConvention**.
- ### Packages
- Groups of classes are contained within packages.
- ### System.out.println
- `System` is the class.
- `out` is the member.
- `println` is the method.
- ### Compilation
- The command `javac main.java` compiles the `.java` file into Java bytecode, which can be run on any OS with a Java runtime. The JVM (Java Virtual Machine) translates the Java bytecode so the OS can run the program.
  
  ---
- ### Variables #card
- Temporarily store data in computer memory.
- ### Primitive Types
- `byte`
- `short` (3 bytes)
- `int` (5 bytes)
- `long` (9 bytes)
- `float`
- `double`
- `char`
- `boolean`
- ### References
- Unlike primitive types, references store complex objects instead of simple values.
- References store variables or data in memory and use pointers to reference memory addresses. If a value is changed at the referenced location, other pointers referencing that location will reflect the change.
  
  ```java
  import java.awt.*;
  
  public class Main {
    public static void main(String[] args) {
        Point point1 = new Point(1, 2);
        Point point2 = point1;
        System.out.println(point2);
    }
  }
  ```
- Primitives are copied by value, while references are copied by their memory location.
- ### Strings
- We can create a string using the `String` class and call methods on it.
  
  ```java
  String message = "hello" + " world";
  System.out.println(message.endsWith("world"));
  ```
- The previous example creates a variable `message` with the string "hello world". It accesses the `endsWith()` method of the `String` class to check if the string ends with the provided suffix ("world"). Since it does, the terminal prints `true`.
  
  ---