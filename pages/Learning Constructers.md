- ```java
  // Car.java
  public class Car {
  
      private String color;
      private int numSeats;
      private boolean yellowPlate;
      private double weight; 
      private int numDoors;
      
      public String toString() {
          return "A " + color + " car with " + " with " + numSeats + " seats " + "is yellow plate: " + (yellowPlate ? "yes" : "no");
          
      }
      
      public Car(String color, int numSeats, boolean yellowPlate, double weight, int numDoors){
         this.color = color; // this refers to the class atribute
         this.numSeats = numSeats; 
         this.yellowPlate = yellowPlate;
         this.weight = weight;
         this.numDoors = numDoors;
          
      }
  
  }
  ```
- This is in a file called Car.java this creates a class, we define variables or parameters in the top with private String or other data type. This will print when the object is called and  the atributes are defined.
- ```java
  // Car.java
  public String toString() {
          return "A " + color + " car with " + " with " + numSeats + " seats " + "is yellow plate: " + (yellowPlate ? "yes" : "no");
          
      }
  ```
- ```java
  //Car.java
  public Car(String color, int numSeats, boolean yellowPlate, double weight, int numDoors){
         this.color = color; // this refers to the class atribute
         this.numSeats = numSeats; 
         this.yellowPlate = yellowPlate;
         this.weight = weight;
         this.numDoors = numDoors;
          
      }
  ```
- This is the actual  constructor it sets the order of the attributes this. refers to the variables or atributes defined at the top public.String or other data type.
- ```java
  // MyProgram.java
  public class MyProgram {
      public static void main(String[] args) {
          // Write a Car class.  What attributes might it need?
          Car x = new Car("red", 4, true, 2000.0, 5);
          System.out.println(x); // Does this work yet?
      }
  }
  ```
- ```java
  // MyProgram.java
  Car x = new Car("red", 4, true, 2000.0, 5);
  ```
-
- Overloaded Constructors
	- you can have a constructer with the same paramters in a different order or with a different numbers of parameters.
	- ```java
	  Car.java
	  public  Car(int numSeats, int numDoors) { // The signature of the constructer is the parameters 
	          this.numSeats = numSeats;
	          this.numDoors = numDoors;
	          this.color = "Silver";
	          this.weight = 2000.0;
	      }
	  ```
		- This constructor just has numSeats and numDoors and sets the rest of the parameters default by setting them bellow.
		- ```java
		  //MyProgram.java
		  // contrsucts car with numSeats and numDoors
		          
		          Car bob = new Car(5, 4);
		  ```
			- This calls the constructor to create an object with numSeats and numDoors but the default parameters are set.