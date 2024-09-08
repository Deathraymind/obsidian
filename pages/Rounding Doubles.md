### Documentation for the Java Program: **Movie Ratings (Rounding a Double)**
- #### Overview: #java 
  This Java program prompts the user to input a movie rating as a `double`. The program then rounds the rating to the nearest integer using a common technique: adding 0.5 before casting the `double` to `int`. This ensures that the `double` is rounded correctly instead of being truncated.
- #### Code Breakdown:
  
  ```java
  import java.util.Scanner;
  
  public class MovieRatings {
    public static void main(String[] args) {
        // Create a Scanner object to read user input
        Scanner input = new Scanner(System.in);
        
        // Prompt the user to enter a movie rating
        System.out.println("Enter Movie Rating:");
        
        // Read the input as a double
        double rating = input.nextDouble();
        
        // Rounding the rating by adding 0.5 and casting to int
        int rounded = (int) (rating + 0.5);
        
        // Print the rounded rating
        System.out.println(rounded);
        
        // Close the Scanner to prevent resource leaks
        input.close();
    }
  }
  ```
- #### Key Concepts:
  1. **User Input with `Scanner`**: 
   The program uses the `Scanner` class to take input from the user. It reads the movie rating as a `double`.
   
   ```java
   Scanner input = new Scanner(System.in);
   double rating = input.nextDouble();
   ```
  
  2. **Rounding Technique**:
   To round the `double` to the nearest integer, the program adds `0.5` to the `double` value before casting it to `int`. This is a simple way to round numbers using integer casting:
	- If `rating` is 4.3, adding `0.5` makes it `4.8`, which when cast to `int`, becomes `4`.
	- If `rating` is 4.7, adding `0.5` makes it `5.2`, which when cast to `int`, becomes `5`.
	  
	  ```java
	  int rounded = (int) (rating + 0.5);
	  ```
	  
	  3. **Output**:
	  The program prints the rounded rating after casting it to an integer. The result is displayed as a whole number:
	  
	  ```java
	  System.out.println(rounded);
	  ```
	  
	  4. **Closing the `Scanner`**:
	  The `Scanner` object is closed after the input is taken to prevent memory leaks:
	  
	  ```java
	  input.close();
	  ```
- #### Example:
  **Input:**
  ```
  Enter Movie Rating:
  4.6
  ```
  
  **Output:**
  ```
  5
  ```
- #### Summary:
- This program demonstrates how to round a `double` to the nearest integer in Java by adding `0.5` and casting the result to `int`.
- It uses the `Scanner` class to take user input and applies basic rounding logic.
  
  This approach can be applied to any situation where simple rounding of floating-point numbers is needed.