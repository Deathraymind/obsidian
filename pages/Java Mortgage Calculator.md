- For this project i had to input a principle the anaul interest rate and period in years
- ```
  import java.util.Scanner;
  import java.text.NumberFormat;
  
  public class Mortgage {
  
      public static void main (String[] args){
          Scanner scanner = new Scanner(System.in);
          byte PERCENT = 100;
          byte MONTHS_IN_YEAR = 12;
  
  
          System.out.print("Principle:");
          int principle = scanner.nextInt();
  
          System.out.print("Annual Intrest Rate: ");
          double monthlyIntrestRate = scanner.nextDouble() / PERCENT / MONTHS_IN_YEAR;
          
          System.out.print("Period (Years): ");
          int periodYears = scanner.nextInt();
  
  
          double numerator = monthlyIntrestRate * Math.pow(1.0 + monthlyIntrestRate, MONTHS_IN_YEAR * periodYears);
          double denominator = Math.pow((monthlyIntrestRate + 1.0), MONTHS_IN_YEAR * periodYears) - 1.0;
  
          double monthlyPayment = (numerator / denominator * principle);
  
          NumberFormat currency = NumberFormat.getCurrencyInstance();
          System.out.println(currency.format(monthlyPayment));
  
      }
  
  
  }
  ```