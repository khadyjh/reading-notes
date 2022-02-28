# OOP

Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields, and code, in the form of procedures.

**What Is an Object?**

An object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life.

Real-world objects share two characteristics: They all have state and behavior
each thing in real-world is an object table,chare ,phone , laptop .

benefits of using object =>
- Modularity:The code for an object can be written and maintained independently of the source code for other objects. Once created, an object can be easily passed around inside the system.

-  Information-hiding:encapsulation :By interacting only with an object's methods, the details of its internal implementation remain hidden from the outside world.

- Code re-use: it can be reused in another program 

**What Is a Class?**

A class is a blueprint or prototype from which objects are created.
the object created from class 

```
// Class Declaration
 
public class Dog
{
    // Instance Variables
    String name;
    String breed;
    int age;
    String color;
 

 
    // method 1
    public String getName()
    {
        return name;
    }
 
    // method 2
    public String getBreed()
    {
        return breed;
    }
 
    // method 3
    public int getAge()
    {
        return age;
    }
 
    // method 4
    public String getColor()
    {
        return color;
    }
 
    @Override
    public String toString()
    {
        return("Hi my name is "+ this.getName()+
               ".\nMy breed,age and color are " +
               this.getBreed()+"," + this.getAge()+
               ","+ this.getColor());
    }
 
    public static void main(String[] args)
    {
        Dog tuffy = new Dog("tuffy","papillon", 5, "white");
        System.out.println(tuffy.toString());
    }
}

```

**Access Modifiers**

- public modifier => the field is accessible from all classes.

- private modifier => the field is accessible only within its own class.

- protected modifier => the field is accessible only within its own package  


## Overloading Methods

java supports overloading methods, which means method with same name with different parameter 

Java can distinguish between methods with different method signatures. This means that methods within a class can have the same name if they have different parameter lists 


## Constructors for Classes

constructor is method except that it use the name of the class and have no return type

constructor invoked to create objects from the class blueprint

**example :**

```

    // Constructor Declaration of Class
    public Dog(String name, String breed,
                   int age, String color)
    {
        this.name = name;
        this.breed = breed;
        this.age = age;
        this.color = color;
    }

    
 ```   

## Creating Objects

you can create object using class name 
**example :**
```
Dog dog = new Dog(“bob”, “breed”, 5, “color”);
```

## Binary, Decimal and Hexadecimal Numbers

**Decimals**

The Decimal Number System called "Base 10", because it is based on the number 10, with these 10 symbols:
```
   0 , 1 , 2 , 3 , 4 , 5 , 6 , 7, 8 , 9

```

**Binary Numbers**

this system contain only of two symbols 
```
       0 , 1
```
that's why called binary 


**Hexadecimal Numbers**
 
this system contain of 16 symbols
```
0 , 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , A , B , C , D , E , F 
```





resources 

[oop](https://docs.oracle.com/javase/tutorial/java/javaOO/usingobject.html)

[Binary, Decimal and Hexadecimal Numbers](https://www.mathsisfun.com/binary-decimal-hexadecimal.html)