# Decorator Pattern
## To avoid class explosion 
Decorator is is a has a both relation 

We create layers like pizza and each layer is of base  Type itself , that how we avoid class explotion 

Key Takeaways:

Decorator Pattern Overview: The Decorator Pattern is a design pattern that allows you to dynamically add additional features or responsibilities to an object without changing its core structure. It involves a base object and decorators that can be added on top of it.

Real-World Applications: The Decorator Pattern is widely used in the real world, such as in the context of pizza toppings. You can add various toppings to a base pizza to create different variations.

Implementation Steps:

Start with a base object (e.g., a basic pizza).
Use decorators to add additional features or responsibilities to the base object.
The decorators can be nested, allowing you to stack multiple features on top of the base object.
Each decorator encapsulates the base object and adds its own functionality.
Example: Pizza Toppings:

The base pizza is the core object.
You can add various toppings (decorators) to the base pizza, such as mushrooms, extra cheese, or pepperoni.
Each additional topping is a decorator that wraps the base pizza and adds its own functionality.
You can continue to add more decorators to the pizza, creating increasingly complex combinations.
Example: Car Customization:

The base car is the core object.
You can add various customizations (decorators) to the base car, such as a cover seat, power steering, or extra features.
Each customization is a decorator that wraps the base car and adds its own functionality.
You can continue to add more decorators to the car, creating increasingly customized versions.
Benefits of the Decorator Pattern:

Allows you to add or remove features from an object at runtime without affecting its core structure.
Provides a flexible and extensible way to enhance the functionality of an object.
Promotes the Open/Closed Principle, where you can extend the functionality of an object without modifying its existing code.
Real-World Usages and Interview Questions:

The Decorator Pattern is often used in scenarios where you need to dynamically add or remove features from an object.
Interview questions may ask you to design a decorator for a specific object, such as a coffee machine or a car.
By understanding the Decorator Pattern and its applications, you can demonstrate your knowledge of design patterns and be better prepared to answer related interview questions.


-------------------------------Example why we are using abstract class waht if we dont use it ------------------------------------
Let's consider a scenario where we want to add a new feature: logging the description and cost of the pizza each time a decorator is applied. If we do not use an abstract class, we need to update every decorator class to include this logging logic. This will illustrate the drawback of code duplication and the benefit of having an abstract class.

Without Abstract Class
Pizza Interface

```
public interface Pizza {
    String getDescription();
    double getCost();
}
```


Concrete Pizza Classes


```
public class PlainPizza implements Pizza {
    @Override
    public String getDescription() {
        return "Plain Pizza";
    }

    @Override
    public double getCost() {
        return 5.00;
    }
}

public class MargheritaPizza implements Pizza {
    @Override
    public String getDescription() {
        return "Margherita Pizza";
    }

    @Override
    public double getCost() {
        return 7.00;
    }
}
```
Decorator Classes Directly Implementing Pizza
CheeseDecorator


```
public class CheeseDecorator implements Pizza {
    private Pizza decoratedPizza;

    public CheeseDecorator(Pizza pizza) {
        this.decoratedPizza = pizza;
    }

    @Override
    public String getDescription() {
        String description = decoratedPizza.getDescription() + ", Cheese";
        System.out.println("Description: " + description); // Logging
        return description;
    }

    @Override
    public double getCost() {
        double cost = decoratedPizza.getCost() + 1.50;
        System.out.println("Cost: " + cost); // Logging
        return cost;
    }
}
```

PepperoniDecorator

```
public class PepperoniDecorator implements Pizza {
    private Pizza decoratedPizza;

    public PepperoniDecorator(Pizza pizza) {
        this.decoratedPizza = pizza;
    }

    @Override
    public String getDescription() {
        String description = decoratedPizza.getDescription() + ", Pepperoni";
        System.out.println("Description: " + description); // Logging
        return description;
    }

    @Override
    public double getCost() {
        double cost = decoratedPizza.getCost() + 2.00;
        System.out.println("Cost: " + cost); // Logging
        return cost;
    }
}
```
## With Abstract Class
Pizza Interface
java

```
public interface Pizza {
    String getDescription();
    double getCost();
}
```

Concrete Pizza Classes
java



````
public class PlainPizza implements Pizza {
    @Override
    public String getDescription() {
        return "Plain Pizza";
    }

    @Override
    public double getCost() {
        return 5.00;
    }
}


public class MargheritaPizza implements Pizza {
    @Override
    public String getDescription() {
        return "Margherita Pizza";
    }

    @Override
    public double getCost() {
        return 7.00;
    }
}
```


Abstract PizzaDecorator Class
java
Copy code

```
public abstract class PizzaDecorator implements Pizza {
    protected Pizza decoratedPizza;

    public PizzaDecorator(Pizza pizza) {
        this.decoratedPizza = pizza;
    }

    @Override
    public String getDescription() {
        String description = decoratedPizza.getDescription();
        System.out.println("Description: " + description); // Logging
        return description;
    }

    @Override
    public double getCost() {
        double cost = decoratedPizza.getCost();
        System.out.println("Cost: " + cost); // Logging
        return cost;
    }
}

```


Concrete Decorator Classes
CheeseDecorator
java

```
public class CheeseDecorator extends PizzaDecorator {
    public CheeseDecorator(Pizza pizza) {
        super(pizza);
    }

    @Override
    public String getDescription() {
        return super.getDescription() + ", Cheese";
    }

    @Override
    public double getCost() {
        return super.getCost() + 1.50;
    }
}
```

PepperoniDecorator

```
public class PepperoniDecorator extends PizzaDecorator {
    public PepperoniDecorator(Pizza pizza) {
        super(pizza);
    }

    @Override
    public String getDescription() {
        return super.getDescription() + ", Pepperoni";
    }

    @Override
    public double getCost() {
        return super.getCost() + 2.00;
    }
}
```

Analysis
Without Abstract Class
Repetition of Logging Logic: Each decorator (e.g., CheeseDecorator, PepperoniDecorator) must independently implement the logging logic within their getDescription() and getCost() methods.
Error Prone: If you forget to add logging in one of the decorators or if there’s an inconsistency, it can lead to bugs.
Maintenance: If the logging logic needs to change, you must update it in every decorator class, increasing the maintenance burden.
With Abstract Class
Centralized Logging Logic: The logging logic is implemented once in the PizzaDecorator abstract class.
Consistency: Ensures that all decorators inherit the logging behavior without needing to reimplement it.
Easy Maintenance: If the logging logic changes, you only need to update it in the PizzaDecorator abstract class.
Conclusion
Using an abstract class like PizzaDecorator allows you to implement common functionality (such as logging) in one place, making the code more reusable, maintainable, and less error-prone. When the same logic needs to be applied across multiple decorators, the abstract class provides a single point of modification, ensuring consistency and reducing the risk of errors.
