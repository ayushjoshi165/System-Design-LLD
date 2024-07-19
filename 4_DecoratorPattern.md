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
