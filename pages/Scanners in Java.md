### Documentation for the Java Program: **Casting `double` to `int`**
- #### Overview:
  This Java program demonstrates how to take user input as a `double`, perform casting to an `int`, modify the double, and cast it again. It uses the `Scanner` class to get input from the console and shows how to convert a floating-point number to an integer.
- #### Code Breakdown:
  
  ```java
  import java.util.Scanner;
  
  public class CastingToInt {
    public static void main(String[] args) {
        // Create a Scanner object to read input from the console
        Scanner input = new Scanner(System.in);
        
        // Prompt the user to enter a double value
        System.out.println("Type:");
        
        // Read the input as a double
        double myDouble = input.nextDouble();
        System.out.println(myDouble);  // Output the original double value
        
        // Cast the double to an integer (truncates the decimal part)
        int cast = (int) myDouble;
        System.out.println(cast);  // Output the casted integer value
        
        // Add 0.5 to the original double value
        myDouble += 0.5;
        System.out.println(myDouble);  // Output the new double value
        
        // Cast the updated double value to an integer
        int stuff = (int) myDouble;
        System.out.println(stuff);  // Output the new casted integer value
        
        // Close the Scanner object to prevent memory leaks
        input.close();
    }
  }
  ```
- #### Steps in the Code:
  
  1. **Importing the Scanner Class**:  
   The `Scanner` class is imported from `java.util` to allow reading of input from the console.
   
  2. **Creating a `Scanner` Object**:  
   A `Scanner` object called `input` is created to receive user input from the console.
  
  3. **Reading Input**:  
   The program asks the user to type a value, which is read as a `double` using the `nextDouble()` method. This value is printed to the console.
  
  4. **Casting `double` to `int`**:  
   The double value is cast to an integer using `(int)`. When casting from a `double` to an `int`, the decimal portion is truncated (not rounded). The integer result is printed.
  
  5. **Modifying the Double**:  
   The program then adds 0.5 to the original double and prints the updated value.
  
  6. **Casting Again**:  
   After modifying the double value, it is cast to an integer again, and the result is printed.
  
  7. **Closing the `Scanner`**:  
   The `Scanner` object is closed using `input.close()` to avoid potential memory leaks.
- #### Key Concepts:
- **Casting**: In Java, casting is the process of converting one data type to another. When casting from `double` to `int`, the decimal portion is discarded.
- **Scanner**: This is a built-in class used to capture user input.
- **Type Safety**: Ensuring that a type can be safely converted from one to another.
- #### Example:
  Input:
  ```
  Type:
  4.7
  ```
  
  Output:
  ```
  4.7
  4  // First cast to int (truncates decimal)
  5.2  // After adding 0.5
  5  // Cast to int after adding 0.5
  ```
  
  This simple program provides a basic example of how to manage user input, cast between types, and perform arithmetic operations in Java.