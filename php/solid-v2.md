# Solid Principals

### Usefull links
Perfect Article about [solid](https://blog.keytech.dev/implementing-the-solid-principles-in-laravel-a-comprehensive-example)

### Single Responsibility Principle (SRP)
This principle states that a class should have only one reason to change.
In other words, a class should have only one responsibility.
Example: Consider a class called Order. 
Instead of having all the functionality related to an order in one class, 
we can break it down into smaller classes like OrderCalculator, OrderRepository, and OrderMailer.

### Open-Closed Principle (OCP)
This principle states that a class should be open for extension but closed for modification.
In other words, we should be able to add new functionality without modifying existing code.
Example: Consider a class called PaymentGateway.
Instead of modifying this class every time we add a new payment method,
we can create a new class for each payment method that extends the PaymentGateway class.

### Liskov Substitution Principle (LSP)
This principle states that objects of a superclass should be able to be replaced with objects of a subclass without affecting the correctness of the program.
Example: Consider a class called Shape with subclasses Circle, Rectangle, and Square.
If we have a function that takes an object of type Shape, we should be able to pass in objects of type Circle, Rectangle, or Square without affecting the behavior of the function.

### Interface Segregation Principle (ISP)
This principle states that clients should not be forced to depend on methods they do not use.
Example: Consider an interface called PaymentMethod with methods like pay, refund, and getTransactions.
Instead of having all these methods in one interface, we can create separate interfaces for each method and have classes implement only the interfaces they need.

### Dependency Inversion Principle (DIP)
This principle states that high-level modules should not depend on low-level modules. Both should depend on abstractions.
Example: Consider a class called Order that depends on a class called OrderRepository. Instead of directly instantiating OrderRepository in Order, we can use dependency injection to inject an instance of OrderRepository into Order.
