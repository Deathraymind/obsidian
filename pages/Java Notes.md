-
- primitives are copied by their value while references are referenced by their locations
-
- we can create a string with such and call it with a the String class and run a methode with it
- ```
  String messege = "hello" + " world";
  System.out.println(messege.endsWith("world"));
  ```
- the previose creates a variable with the string hellow world, this variable is named messege and can be acsessed through the string class as a member class so the print line looks at the class messege and apends the endsWith which looks for a provided suffix and returns a boolean in this class our suffix is world which it does end with so the termeinal will print out true.
-