### Documentation for the Java Program: **Integer Overflow**
- #### Overview: #java 
  This Java program demonstrates **integer overflow** and **underflow** by working with the minimum and maximum values of the `int` data type in Java. It prints the minimum and maximum integer values using the constants `Integer.MIN_VALUE` and `Integer.MAX_VALUE`, and shows what happens when you add `1` to the maximum or subtract `1` from the minimum.
- #### Code Breakdown:
  
  ```java
  public class IntegerOverflow {
    public static void main(String[] args) {
        // Print the minimum integer value
        System.out.print("The minimum integer value in Java is ");
        System.out.println(Integer.MIN_VALUE);
  
        // Print the maximum integer value
        System.out.print("The maximum integer value in Java is ");
        System.out.println(Integer.MAX_VALUE);
  
        // Demonstrate integer overflow by adding 1 to the maximum value
        System.out.println(Integer.MAX_VALUE + 1);
  
        // Demonstrate integer underflow by subtracting 1 from the minimum value
        System.out.println(Integer.MIN_VALUE - 1);
    }
  }
  ```
- #### Key Concepts:
  
  1. **Integer Data Type**:
   In Java, an `int` (integer) is a 32-bit signed data type. It can hold values from `-2^31` to `2^31 - 1`, which corresponds to:
	- `Integer.MIN_VALUE`: `-2147483648`
	- `Integer.MAX_VALUE`: `2147483647`
	  
	  2. **Printing Minimum and Maximum Integer Values**:
	  The constants `Integer.MIN_VALUE` and `Integer.MAX_VALUE` are used to print the minimum and maximum integer values, respectively.
	  
	  ```java
	  System.out.println(Integer.MIN_VALUE);  // Output: -2147483648
	  System.out.println(Integer.MAX_VALUE);  // Output: 2147483647
	  ```
	  
	  3. **Integer Overflow**:
	  When you add `1` to the maximum possible value of an `int` (`2147483647`), the value "wraps around" to the minimum value (`-2147483648`). This is known as **integer overflow**.
	  
	  ```java
	  System.out.println(Integer.MAX_VALUE + 1);  // Output: -2147483648
	  ```
	  
	  4. **Integer Underflow**:
	  Similarly, subtracting `1` from the minimum possible value of an `int` (`-2147483648`) causes it to "wrap around" to the maximum value (`2147483647`). This is called **integer underflow**.
	  
	  ```java
	  System.out.println(Integer.MIN_VALUE - 1);  // Output: 2147483647
	  ```
- #### Example Output:
  ```
  The minimum integer value in Java is -2147483648
  The maximum integer value in Java is 2147483647
  -2147483648
  2147483647
  ```
- #### Summary:
- **Integer Overflow** occurs when you try to exceed the maximum value of an `int` by adding `1`, causing it to wrap around to the minimum value.
- **Integer Underflow** occurs when you try to go below the minimum value of an `int` by subtracting `1`, causing it to wrap around to the maximum value.
- In Java, `int` values are 32-bit signed integers, ranging from `-2147483648` to `2147483647`.
  
  This program is useful for understanding how Java handles overflow and underflow in fixed-size integer types.