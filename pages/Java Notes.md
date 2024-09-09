- Function #java
	- a block of code that completes a goal
		- First specify the return type of the function this is often void
		- inside of the perenthsies of void nameoffuntion() goes the parameters
		- the main function needs to exist so it gets called
- class
	- is a container for related functions
	- in java we define a class with class and closed  squiggly parentheses
	- when a function is out of class its refereed to as a function but when its in a class its refereed to as a method.
	- all classes sould have a acsess modifier
		- is a special keyword if other classes can call these methods
		- public private ect
- This is a basic structure of a java program
  ```public class Main {
  public class Main {
  	public void main() {
      
      ...
      
  	}
  }
  ```
- Methods should use the PascalNamingConvention while methods should use the camelNamingConventions.
- Packages contain groups of classes
- System.out.println
	- System is the class
	- out is the member
	- println is a methode
- The command javac main.java compiles the .java file into java byte code which can be ran on any OS with java runtime which runs the code in JVM or java virtual machine which translates the java byte code so the OS can run things.
-
- Varaibles
	- temp store data in computer memory
- Primative types
	- byte
	- short 2 bytes
	- int 4 byte
	- long 8 Byte
	- float
	- double
	- char
	- boolean
- References
	- unlike primative values references store complex objects instead of simple values
	- references store varaibles or data in memory and then use pointers to point back to the memory address, this means if the value of x is changed in a point and another pointer calls the previose pointer it will go to the address instead.
	- ```
	  import java.awt.*;
	  
	  public class Main {
	      public static void main(String[] args) {
	          Point point1 = new Point(1, 2);
	          Point point2 = point1;
	          System.out.println(point2);
	  
	      }
	  }
	  ```
-
- primatives are copt