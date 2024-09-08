### Documentation for the Java Program: **Casting and Order of Operations**
- #### Overview: #java 
  This program demonstrates how casting and order of operations work in Java, particularly when dealing with arithmetic operations and how Java handles integer and floating-point division. It explores different cases of casting and its effects on calculations, showing how parentheses can impact the results.
- #### Code Breakdown:
  
  ```java
  public class CastingOrderOfOperations {
    public static void main(String[] args) {
        // Example 1: Casting double to int (truncates decimal)
        int doubleCastedToInt = (int) 10.9;
        System.out.println("Casting to an int: ");
        System.out.print("(int) 10.9 = ");
        System.out.println(doubleCastedToInt);
        System.out.println();
        
        // Example 2: Casting the numerator
        double castNumerator = (double) 2 / 3;
        System.out.println("Casting numerator: ");
        System.out.print("(double) 2 / 3 = ");
        System.out.println(castNumerator);
        System.out.println();
        
        // Example 3: Casting the denominator
        double castDenominator = 2 / (double) 3;
        System.out.println("Casting denominator: ");
        System.out.print("2 / (double) 3 = ");
        System.out.println(castDenominator);
        System.out.println();
        
        // Example 4: Neither operand casted, results in integer division
        double castNeither = 2 / 3;
        System.out.println("Casting neither (integer division): ");
        System.out.print("2 / 3 = ");
        System.out.println(castNeither);
        System.out.println();
        
        // Example 5: Casting outside parentheses (integer division happens first)
        double castOutsideOfParentheses = (double) (2 / 3);
        System.out.println("Casting outside of parentheses: ");
        System.out.print("(double) (2 / 3) = ");
        System.out.println(castOutsideOfParentheses);
        System.out.println();
        
        // Example 6: Casting the wrong element
        double castWrongElement = (double) 5 + 2 / 3;
        System.out.println("Casting the 5...\n2 / 3 is unaffected by cast (be careful):");
        System.out.print("(double) 5 + 2 / 3 = ");
        System.out.println(castWrongElement);
        System.out.println();
        
        // Example 7: Casting the correct element
        double castCorrectElement = 5 + (double) 2 / 3;
        System.out.println("Cast happens before the division here:");
        System.out.print("5 + (double) 2 / 3 = ");
        System.out.println(castCorrectElement);
        System.out.println();
    }
  }
  ```
- #### Concepts Demonstrated:
  
  1. **Casting Truncates Decimal**:
	- `(int) 10.9` results in `10` because casting a `double` to `int` truncates the decimal part, not rounding it.
	  
	  ```java
	  int doubleCastedToInt = (int) 10.9;  // Results in 10
	  ```
	  
	  2. **Casting the Numerator**:
	- `(double) 2 / 3` casts `2` to a `double`, which makes the entire expression a `double` division (`0.6666`).
	  
	  ```java
	  double castNumerator = (double) 2 / 3;  // Results in 0.6666
	  ```
	  
	  3. **Casting the Denominator**:
	- `2 / (double) 3` casts `3` to a `double`, leading to `double` division.
	  
	  ```java
	  double castDenominator = 2 / (double) 3;  // Results in 0.6666
	  ```
	  
	  4. **No Casting (Integer Division)**:
	- Without casting, `2 / 3` is an integer division, resulting in `0` because both operands are integers.
	  
	  ```java
	  double castNeither = 2 / 3;  // Results in 0
	  ```
	  
	  5. **Casting Outside Parentheses**:
	- `(double) (2 / 3)` applies integer division first, resulting in `0`. Then `0` is cast to `double`, which is still `0.0`.
	  
	  ```java
	  double castOutsideOfParentheses = (double) (2 / 3);  // Results in 0.0
	  ```
	  
	  6. **Casting the Wrong Element**:
	- `(double) 5 + 2 / 3` casts `5` to a `double` (`5.0`), but `2 / 3` remains an integer division resulting in `0`. So, `5.0 + 0` equals `5.0`.
	  
	  ```java
	  double castWrongElement = (double) 5 + 2 / 3;  // Results in 5.0
	  ```
	  
	  7. **Casting the Correct Element**:
	- `5 + (double) 2 / 3` casts `2` to `double`, resulting in `0.6666`. Therefore, `5 + 0.6666` equals `5.6666`.
	  
	  ```java
	  double castCorrectElement = 5 + (double) 2 / 3;  // Results in 5.6666
	  ```
- #### Key Takeaways:
- **Order of Operations**: Parentheses have the highest precedence. Operations inside parentheses are performed first.
- **Casting**: When casting a number to a different type, the casting happens before any arithmetic operation unless parentheses are used to enforce a different precedence.
- **Integer Division**: In Java, dividing two integers results in an integer, discarding the remainder. Casting one operand to `double` ensures that the result will be a floating-point division.
- **Be Careful with Casting**: It’s important to cast the correct operand to avoid unintended results (e.g., casting the wrong element leads to incorrect results).
  
  This program serves as a good exercise to understand Java’s typecasting and how the order of operations impacts expressions.