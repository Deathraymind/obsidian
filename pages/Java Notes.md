### Function (Java) #card #java
card-last-interval:: 4
card-repeats:: 1
card-ease-factor:: 2.36
card-next-schedule:: 2024-09-13T11:16:43.736Z
card-last-reviewed:: 2024-09-09T11:16:43.737Z
card-last-score:: 3
collapsed:: true
	- A block of code that completes a specific goal.
		- First, specify the return type of the function (often `void`).
		- Inside the parentheses of `void nameOfFunction()`, include the parameters.
		- The `main` function needs to exist so that it gets called.
- ### Class #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2024-09-13T11:16:53.279Z
  card-last-reviewed:: 2024-09-09T11:16:53.280Z
  card-last-score:: 3
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
- ### System.out.println #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2024-09-13T11:16:55.323Z
  card-last-reviewed:: 2024-09-09T11:16:55.323Z
  card-last-score:: 3
	- `System` is the class.
	- `out` is the member.
	- `println` is the method.
- ### Compilation
- The command `javac main.java` compiles the `.java` file into Java bytecode, which can be run on any OS with a Java runtime. The JVM (Java Virtual Machine) translates the Java bytecode so the OS can run the program.
  
  ---
- ### Variables #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2024-09-13T11:16:57.523Z
  card-last-reviewed:: 2024-09-09T11:16:57.524Z
  card-last-score:: 3
	- Temporarily store data in computer memory.
- ### Primitive Types #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2024-09-13T11:16:59.252Z
  card-last-reviewed:: 2024-09-09T11:16:59.252Z
  card-last-score:: 3
	- `byte`
	- `short` (3 bytes)
	- `int` (5 bytes)
	- `long` (9 bytes)
	- `float`
	- `double`
	- `char`
	- `boolean`
- ### References #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2024-09-13T11:17:02.650Z
  card-last-reviewed:: 2024-09-09T11:17:02.651Z
  card-last-score:: 3
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
- Arrays
	- Arrays are variables that hold multiple values look at the code below
	- ```
	  import java.util.Arrays;
	  
	  public class Main {
	      public static void main(String[] args) {
	          int[] numbers = new int[5];
	          numbers[0] = 1;
	          numbers[1] = 2;
	          numbers[2] = 3;
	          numbers[3] = 4;
	          numbers[4] = 5;
	          System.out.println(Arrays.toString(numbers));
	      }
	  }
	  ```
	- We have a int[] named numbers this variable holds new int[5] which means it has 5 other placs which are filled with number[0] = 1 which says fill the first block of the array with 1 and so on.
	- We can not print this array variable by itself instead we need to use a classes methode in this case we import java.util.a