# Inheritance And Interfaces

## Inheritance

The idea of inheritance is simple but powerful: When you want to create a new class and there is already a class that includes some of the code that you want, you can derive your new class from the existing class. In doing this, you can reuse the fields and methods of the existing class without having to write (and debug!) them yourself.


Object-oriented programming allows classes to inherit commonly used state and behavior from other classes.

in the Java programming language, each class is allowed to have one direct superclass, and each superclass has the potential for an unlimited number of subclasses:

        
![Inheritance](imges/concepts-bikeHierarchy.gif)

The syntax for creating a subclass is simple. At the beginning of your class declaration, use the **extends** keyword, followed by the name of the class to inherit from:
```
class MountainBike extends Bicycle {

    // new fields and methods defining 
    // a mountain bike would go here

}
```

A subclass inherits all the members (fields, methods, and nested classes) from its superclass. **Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.**

***Example of Inheritance***

```
public class Bicycle {
        
    // the Bicycle class has three fields
    public int cadence;
    public int gear;
    public int speed;
        
    // the Bicycle class has one constructor
    public Bicycle(int startCadence, int startSpeed, int startGear) {
        gear = startGear;
        cadence = startCadence;
        speed = startSpeed;
    }
        
    // the Bicycle class has four methods
    public void setCadence(int newValue) {
        cadence = newValue;
    }
        
    public void setGear(int newValue) {
        gear = newValue;
    }
        
    public void applyBrake(int decrement) {
        speed -= decrement;
    }
        
    public void speedUp(int increment) {
        speed += increment;
    }
        
}
```
**A class declaration for a MountainBike class that is a subclass of Bicycle might look like this:**

```
public class MountainBike extends Bicycle {
        
    // the MountainBike subclass adds one field
    public int seatHeight;

    // the MountainBike subclass has one constructor
    public MountainBike(int startHeight,
                        int startCadence,
                        int startSpeed,
                        int startGear) {
        super(startCadence, startSpeed, startGear);
        seatHeight = startHeight;
    }   
        
    // the MountainBike subclass adds one method
    public void setHeight(int newValue) {
        seatHeight = newValue;
    }   
}
```

### What You Can Do in a Subclass

A subclass inherits all of the **public and protected** members of its parent, no matter what package the subclass is in. **If the subclass is in the same package as its parent, it also inherits the package-private members of the parent**. You can use the inherited members as is, replace them, hide them, or supplement them with new members:


- The inherited fields can be used directly, just like any other fields.
- You can declare a field in the subclass with the same name as the one in the  superclass, thus hiding it (not recommended).
- You can declare new fields in the subclass that are not in the superclass.
- The inherited methods can be used directly as they are.
- You can write a new instance method in the subclass that has the same signature as - the one in the superclass, thus overriding it.
- You can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
- You can declare new methods in the subclass that are not in the superclass.
- You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.



## Interfaces

In the Java programming language, an interface is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods. Interfaces cannot be instantiated—they can only be **implemented** by classes or **extended** by other interfaces.

Defining an interface is similar to creating a new class:
```
public interface OperateCar {

   // constant declarations, if any

   // method signatures
   
   // An enum with values RIGHT, LEFT
   int turn(Direction direction,
            double radius,
            double startSpeed,
            double endSpeed);
   int changeLanes(Direction direction,
                   double startSpeed,
                   double endSpeed);
   int signalTurn(Direction direction,
                  boolean signalOn);
   int getRadarFront(double distanceToCar,
                     double speedOfCar);
   int getRadarRear(double distanceToCar,
                    double speedOfCar);
         ......
   // more method signatures
}
```

Note that the method signatures have no braces and are terminated with a semicolon.

To use an interface, you write a class that implements the interface. When an instantiable class implements an interface, it provides a method body for each of the methods declared in the interface.

The relationship between classes and interfaces

a class extends another class, an interface extends another interface, but a class implements an interface.

![interfacerelation](imges/interfacerelation.jpg)



