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
	- We can not print this array variable by itself instead we need to use a classes methode in this case we import java.util.Arrays and then call that class and methode within the print line with Arrays.toString and we want the arraay numbers this converts our array table into a list of numbers.
	- Printing the length or amount of items in an array is easy. look at the following.
	- ```
	  import java.util.Arrays;
	  
	  public class Main {
	      public static void main(String[] args) {
	          int[] numbers = {2, 3, 4, 5, 6};
	          System.out.println(numbers.length);
	      }
	  }
	  ```
	- We have an array and values defined with int[] numbers = {2, 3, 4, 5, 6};
		- now to print the amount of items we have in numbers we use numbers.length length is not a method but is a field.
	- Arrays have a fixed length
	- You can sort arrays with Arrays.sort
- Multi Dimensional Arrays
	- These are basically matrixs
	- ```
	  import java.util.Arrays;
	  
	  public class Main {
	      public static void main(String[] args) {
	          int[][] numbers = new int [2][3];
	          numbers[0][0] = 1;
	          System.out.println(Arrays.deepToString(numbers));
	      }
	  }
	  ```
	- This is a two dimensional array int [][] means we have 2 dimensions but we need to have to other brackets on the other side [2][3] this defines our row and colloms
	- to print this out we cant use toString wee have to use a different methode in the Arrays class called deepToString and then define the array you want to print.
	- if you want to define a multidimensional array use the following.
	- ```
	          int[][] numbers = { { 1, 2, 3}, { 4, 5, 6} }; 
	  ```
- Constants
	- ```
	      final float PI = 3.14F;
	  ```
	- the final means that the variable can not be changed later in the code
		- be sure to all caps final variables.
- Arithmetic Expressions
	- +  * % / -
	- its important to not this
		- ```
		  int result = 10 / 3;
		  ```
			- This = 3 because it can not be a decimal as its not a double or a float
		- ```
		     double result = 10 / 3;
		  ```
			- This will also result in a 3 as their are two integers within the double
		- ```
		     double result = (double)10 / (double)3;
		  ```
			- This will result in 3.33333 as its a variable double contain two doubles in an expression
		- x++; is called the increment operator
	- Order of operations
		- ()
		- */
		- +-
		- and it would be left to right
- Expression
	- A piece of code that produces a value.
- Casting
	- changing a data type into another like turning an int into a double
	- ```
	   double result = (double)10 / (double)3;
	  ```
- Implicit Casting
	- we dont worry about it its automatic
		- This happens when were converting byte > short > long  basically a smaller data type into a larger one.
	- Another example of this is
	- ```
	  double x = 1.1;
	  double y = x + 2;
	  ```
		- After this the the result will be 3.3 for y
			- This is because were taking 1.1 a double and adding it to an integer 2. What java does is implicit casting to convert that 2 into a double 2.0  then adding it to the other double.
- Explicit Casting
	- This is when we convert a larger data type into a smaller one manually
	- ```
	  double x = 1.1;
	  int y = (int)x +2;
	  ```
	- we have to cast x to an int manually in this expression in order to add 2 and store it in an int
- String to intager casting
	- Integers/primitives and strings/references are not compatible to be casted so we must use wrapper classes like such
	- ```
	  String x = "1";
	  int y = Intager.pasreInt(x) + 2;
	  ```
		- In this we have a class which is a reference type called Integer. and in this we have a methode called parseInt.
- Math Class
	-