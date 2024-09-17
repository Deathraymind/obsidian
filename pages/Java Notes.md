### Function (Java) #card #java
card-last-interval:: -1
card-repeats:: 1
card-ease-factor:: 2.36
card-next-schedule:: 2024-09-17T15:00:00.000Z
card-last-reviewed:: 2024-09-17T00:17:49.598Z
card-last-score:: 1
collapsed:: true
	- A block of code that completes a specific goal.
		- First, specify the return type of the function (often `void`).
		- Inside the parentheses of `void nameOfFunction()`, include the parameters.
		- The `main` function needs to exist so that it gets called.
- ### Class #card
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2024-09-17T15:00:00.000Z
  card-last-reviewed:: 2024-09-17T00:17:50.867Z
  card-last-score:: 1
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
	- this is a class with a bunch of math methodes
		- Math.round
		- Math.ceil this prints the smallest integer that is equal too or greater than the provided number
- Formatting Numbers
	- ```
	  import java.text.NumberFormat;
	  ```
		- this has alot of classes such as getCurrencyInstance()
		- ```
		  import java.util.Arrays;
		  import java.text.NumberFormat;
		  
		  public class Main {
		      public static void main(String[] args) {
		         NumberFormat currency = NumberFormat.getCurrencyInstance();
		         String result = currency.format(12345667.657);
		         System.out.println(result);
		      }
		  }
		  ```
			- This prints out $12,345,667.66 due to the class and methode used above.
- Abstract Class
	- A class that can not be used with a new operator to create an instance with them.
- Methode Chaining
	- ```
	  import java.util.Arrays;
	  import java.text.NumberFormat;
	  
	  public class Main {
	      public static void main(String[] args) {
	         String percent = NumberFormat.getPercentInstance().format(.1);
	         System.out.println(percent);
	      }
	  }
	  ```
		- This basically is when we chain multiple methods together. the above example is creating a string variable and is using the class NumberFormat and method getPercentInstance() but it then needs to be formatted so instead of calling the variable in another line and uisng the method we just add .format and then the number right to the end.
- Reading input
	- ```
	  import java.util.Scanner;
	  
	  public class Main {
	      public static void main(String[] args) {
	          Scanner scanner = new Scanner(System.in);
	          System.out.print("Age:");
	          // using print instead of printls will make it so that they
	          // user input will be on the same line as the age strings
	          // this is because println prints the string then presses enter.
	          byte age = scanner.nextByte();
	          // byte age is the variable type and name and scanner calls the varaible above Which
	          // calls the scanner class and methode for in or inputs
	          // it then stores it as a byte
	          System.out.println(age + "You are");
	          // when we add a string to a byrte it uses inexplicit castings
	          // to turn the byte into a string and then prints it out. 
	      }
	  }
	  ```
	- To import a scanner use
		- ```
		  inport java.util.Scanner;
		  ```
	- Add this line so the scanner can be used within the Main fucntions
		- ```
		  		Scanner scanner = new Scanner(System.in);
		  ```
	- To scan for an input use
		- ```
		   byte age = scanner.nextByte();
		  ```
- comparison operators
	- || or
	- ! reverts bollean
	- && and
- Ternary Operator
	- ```
	  String className = x > 1 ? "more than one" : "less than one";
	  ```
	- Cretes a string named className and looks at the intager value of x if it is bigger than one it pritns more than one if its smaller than it types less than one.
- Switch Statements
- ```java
  import java.util.Arrays;
  import java.text.NumberFormat;
  
  public class Main {
      public static void main(String[] args) {
          String role = "admin";
          
          switch (role) {
              case "admin":
                  System.out.println("You are admin");
              break;
              case "moderator":
                  System.out.println("moderator");
              break;
              default:
              System.out.println("Loser");
          }
      }
  }
  ```
- Constructers
	- Constructors are called when an object of a class is called. It is used to set default values of class attributes.
	- ```java
	  public class Main {
	    int x;  // Create a class attribute
	  
	    // Create a class constructor for the Main class
	    public Main() {
	      x = 5;  // Set the initial value for the class attribute x
	    }
	  
	    public static void main(String[] args) {
	      Main myObj = new Main(); // Create an object of class Main (This will call the constructor)
	      System.out.println(myObj.x); // Print the value of x
	    }
	  }
	  ```
		- Note that the constructor name must **match the class name**, and it cannot have a 
		  **return type* (like `void`).
			- Also note that the constructor is called when the object is created.
			- All classes have constructors by default: if you do not create a class constructor 
			  yourself, Java creates one for you. However, then you are not able to set initial values for object attributes.
- ```java
  public class Main {
    int x;
  
    public Main(int y) {
      x = y;
    }
  
    public static void main(String[] args) {
      Main myObj = new Main(5); //sets the value of y and their for the value of x.
      System.out.println(myObj.x);
    }
  }
  
  ```
- ```java
  public class Main {
    int modelYear;
    String modelName;
  
    public Main(int year, String name) {
      modelYear = year;
      modelName = name;
    }
  
    public static void main(String[] args) {
      Main myCar = new Main(1969, "Mustang");
      System.out.println(myCar.modelYear + " " + myCar.modelName);
    }
  }
  
  // Outputs 1969 Mustang
  ```
- ```java
  public class Main {
    final int x = 10;
    final double PI = 3.14;
  
    public static void main(String[] args) {
      Main myObj = new Main();
      myObj.x = 50; // will generate an error: cannot assign a value to a final variable
      myObj.PI = 25; // will generate an error: cannot assign a value to a final variable
      System.out.println(myObj.x);
    }
  }
  
  ```
- Static vs Public
	- A static class does not require you to create an object public does, thats this goofy little line .
	- ```java
	  Main myObj = new Main();
	  ```
-