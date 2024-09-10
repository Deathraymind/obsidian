### **Mortgage Calculator Program Documentation**
- #### **Imports**
- `import java.util.Scanner;`
	- This imports the `Scanner` class from `java.util` package, which allows for user input from the console.
- `import java.text.NumberFormat;`
	- This imports the `NumberFormat` class from `java.text` package, which is used to format numbers as currency.
- #### **Main Class: `Mortgage`**
  The `Mortgage` class contains the main method that runs the program, calculating the monthly mortgage payments based on user input.
- #### **Constants**
- `byte PERCENT = 100;`
	- Used to convert percentages into decimals when calculating the interest rate.
- `byte MONTHS_IN_YEAR = 12;`
	- Represents the number of months in a year and is used to calculate the total number of monthly payments.
- #### **Main Method: `public static void main (String[] args)`**
  This method executes the program and performs the following steps:
  
  1. **Initialize Scanner:**
	- `Scanner scanner = new Scanner(System.in);`
	- This initializes the `Scanner` object, which allows the user to input values for the principal, annual interest rate, and loan period.
	  
	  2. **User Input:**
	- `System.out.print("Principle:");`
	- `int principle = scanner.nextInt();`
		- The program prompts the user to enter the **principal** (the loan amount). The user's input is stored as an integer.
	- `System.out.print("Annual Intrest Rate: ");`
	- `double monthlyIntrestRate = scanner.nextDouble() / PERCENT / MONTHS_IN_YEAR;`
		- The program prompts the user to enter the **annual interest rate**. This value is converted to a monthly interest rate by dividing it by 100 and then by 12.
	- `System.out.print("Period (Years): ");`
	- `int periodYears = scanner.nextInt();`
		- The user enters the loan period in **years**.
		  
		  3. **Mortgage Calculation:**
	- The formula for calculating the monthly mortgage payment is split into two parts: the `numerator` and the `denominator`.
	- **Numerator:**
	  ```java
	  double numerator = monthlyIntrestRate * Math.pow(1.0 + monthlyIntrestRate, MONTHS_IN_YEAR * periodYears);
	  ```
	  This calculates the top part of the mortgage formula:
	  \[
	  \text{Numerator} = r \times (1 + r)^n
	  \]
	  Where `r` is the monthly interest rate, and `n` is the total number of monthly payments.
	- **Denominator:**
	  ```java
	  double denominator = Math.pow((1.0 + monthlyIntrestRate), MONTHS_IN_YEAR * periodYears) - 1.0;
	  ```
	  This calculates the bottom part of the mortgage formula:
	  \[
	  \text{Denominator} = (1 + r)^n - 1
	  \]
	- **Monthly Payment:**
	  ```java
	  double monthlyPayment = (numerator / denominator * principle);
	  ```
	  The formula for the monthly payment is derived by dividing the `numerator` by the `denominator` and multiplying it by the principal loan amount:
	  \[
	  M = \frac{P \times r \times (1 + r)^n}{(1 + r)^n - 1}
	  \]
	  Where:
		- \( M \) = monthly payment
		- \( P \) = principal loan amount
		- \( r \) = monthly interest rate
		- \( n \) = total number of payments (months)
		  
		  4. **Formatting and Output:**
	- `NumberFormat currency = NumberFormat.getCurrencyInstance();`
		- This creates a `NumberFormat` instance to format the final monthly payment as a currency.
	- `System.out.println(currency.format(monthlyPayment));`
		- The monthly payment is formatted and printed as a currency value (e.g., `$86.10`).
- #### **Example Usage:**
  ```
  Principle: 10000
  Annual Intrest Rate: 3.7
  Period (Years): 12
  ```
  Output:
  ```
  $86.10
  ```
  
  ---
-
- ```java
  import java.util.Scanner;
  import java.text.NumberFormat;
  
  public class Mortgage {
  
      public static void main (String[] args){
          Scanner scanner = new Scanner(System.in);
          byte PERCENT = 100;
          byte MONTHS_IN_YEAR = 12;
  
          // Step 1: Get User Input
          System.out.print("Principal:");
          int principal = scanner.nextInt();
  
          System.out.print("Annual Interest Rate: ");
          double monthlyInterestRate = scanner.nextDouble() / PERCENT / MONTHS_IN_YEAR;
  
          System.out.print("Period (Years): ");
          int periodYears = scanner.nextInt();
  
          // Step 2: Calculate the mortgage
          double numerator = monthlyInterestRate * Math.pow(1.0 + monthlyInterestRate, MONTHS_IN_YEAR * periodYears);
          double denominator = Math.pow(1.0 + monthlyInterestRate, MONTHS_IN_YEAR * periodYears) - 1.0;
          double monthlyPayment = (numerator / denominator) * principal;
  
          // Step 3: Format and display result as currency
          NumberFormat currency = NumberFormat.getCurrencyInstance();
          System.out.println(currency.format(monthlyPayment));
      }
  }
  
  ```
-