Whenever we create object and there is condition based on it we create object, It is heavily used in company 

In factory pattern we create a factory and an inteface ex shape and diffent classes like circle, rectangle , and square will implement , factroy will be source of truth and bases on the input it will retrun the object

![factoryPattern](factoryPattern1.png)

Factory Pattern Summary and Java Implementation
Key Learnings and Takeaways:
1. Factory Pattern Overview:

The Factory Pattern is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.
It helps avoid the need for explicit object creation by clients and provides a way to encapsulate the object creation logic.
2. Use Cases of Factory Pattern:

When you have multiple classes that share a common superclass, and you want to create objects of these classes based on some condition or configuration.
When you want to provide a way to create objects without exposing the creation logic to the client.
When you have a class with multiple subclasses and you want to hide the creation logic from the client.
3. Factory Pattern Implementation:

Create an interface or abstract class that defines the common methods for the objects to be created.
Create concrete classes that implement the interface or extend the abstract class.
Create a factory class that encapsulates the object creation logic and provides a method to create the objects based on some condition or configuration.
The client uses the factory class to create the objects instead of directly instantiating the concrete classes.
Java Code Implementation:

// Step 1: Create the interface/abstract class
```
public interface Vehicle {
    void drive();
}
```
// Step 2: Create the concrete classes
```
public class Car implements Vehicle {
    public void drive() {
        System.out.println("Driving a car...");
    }
}

public class Motorcycle implements Vehicle {
    public void drive() {
        System.out.println("Driving a motorcycle...");
    }
}
```

// Step 3: Create the factory class
```
public class VehicleFactory {
    public static Vehicle createVehicle(String type) {
        if (type.equalsIgnoreCase("car")) {
            return new Car();
        } else if (type.equalsIgnoreCase("motorcycle")) {
            return new Motorcycle();
        } else {
            throw new IllegalArgumentException("Invalid vehicle type");
        }
    }
}
```
// Step 4: Client code
```
public class Main {
    public static void main(String[] args) {
        Vehicle car = VehicleFactory.createVehicle("car");
        car.drive(); // Output: Driving a car...

        Vehicle motorcycle = VehicleFactory.createVehicle("motorcycle");
        motorcycle.drive(); // Output: Driving a motorcycle...
    }
}
```
In this example, the VehicleFactory class encapsulates the object creation logic and provides a createVehicle() method to create the appropriate Vehicle object based on the input type. The client code uses the factory to create the desired Vehicle object without needing to know the specific implementation details.

Abstract fractory pattern is Factory of Factory 
![Abstract factoryPattern](AbstractFactryPattern1.png)


