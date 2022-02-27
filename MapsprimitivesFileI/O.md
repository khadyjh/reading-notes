# Maps, primitives, File I/O

## Java Primitives versus Objects

- primitives => int ,boolean,float,char
- reference types =>Integer, Boolean

and  Every primitive type corresponds to a reference type.

```
Integer j = 1;          // autoboxing
int i = new Integer(1); // unboxing
```

**converting a primitive type to a reference one is called autoboxing**
**converting a reference type to a primitive one is called unboxing**

what to use from them is depend on what your application need and how much memory you have 


primitive variable holding memory like that =>
- boolean – 1 bit
- byte – 8 bits
- short, char – 16 bits
- int, float – 32 bits
- long, double – 64 bits

Variables of primitive types live in the stack and hence are accessed fast

***in other hand*** 

The reference types are objects, they live on the heap and are relatively slow to access. They have a certain overhead concerning their primitive counterparts.
reference types holding memory like that =>

- Boolean – 128 bits
- Byte – 128 bits
- Short, Character – 128 bits
- Integer, Float – 128 bits
- Long, Double – 192 bits

*the default value for primitive types are 0 for numeric types,false for boolean* 

*for the referance type it null*

## Exceptions
we use try and catch to avoid errores , and to use it in efficient way we need to use the Exceptions

what is Exceptions?

An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.

The Three Kinds of Exceptions :
1. checked exception.
2. the error.
3. runtime exception.


and here example :


```
   try (Scanner scanner = new Scanner(file)) {

           while (scanner.hasNextLine()) {
               System.out.println(scanner.nextLine());
           }
       } catch (FileNotFoundException fileNotFoundException) {
           System.err.println(fileNotFoundException.getMessage());
       }

```       



## Scanner 

is a class in java allow to read from user or from external file 

and here is example :

```
   public void consoleInput() {

       Scanner scanner = new Scanner(System.in);
       System.out.println("Please type something");
       String input = scanner.nextLine();
       System.out.println("Your input was => " + input + "\n\n");

       System.out.println("Type in your age");
       int age = scanner.nextInt();
       System.out.println("Your age is => " + age);
       scanner.close();
   }


```

resources 

[Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)

[Scanning](https://docs.oracle.com/javase/tutorial/essential/io/scanning.html)

[Java Primitives versus Objects](https://www.baeldung.com/java-primitives-vs-objects)
