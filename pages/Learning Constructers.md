- ```java
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
  public String toString() {
          return "A " + color + " car with " + " with " + numSeats + " seats " + "is yellow plate: " + (yellowPlate ? "yes" : "no");
          
      }
  ```
- ```java
   public Car(String color, int numSeats, boolean yellowPlate, double weight, int numDoors){
         this.color = color; // this refers to the class atribute
         this.numSeats = numSeats; 
         this.yellowPlate = yellowPlate;
         this.weight = weight;
         this.numDoors = numDoors;
          
      }
  ```
- This is the actual  contrscter