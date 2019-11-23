# Design and DesignPatterns
#### About

This is a repository which I use for learning design patterns. 
This is formed as a notes with the book **Head First Design Patterns**
by *Eric Freeman and Elisabeth Freeman*. Although I have also been *googling* a whenever I get questions and put the
answers here :smirk: .

I have also used this repo to learn .md - *markdown*. Some Basic programming, vim and bla bla.

#### Some Basics
These are some basics of software and programming.

1)Abstraction

2)Encapsulation

3)Polimorphism

4)Inheritance


#### For UMLs

A ________> B  : A has-a type of B : composition

A ________I> B  : A extends B : Inheritance

A _ _ _ _ _ _I> B: A implements B : Interface
  

#### Basic Design Principles
>1) Identify the aspects of your application that vary and 
separate (*encpsulate*) them from what stays the same.
>2) Program to an *Interface* not to an Implementation.
>3) Favour composition over inheritance. Has-A is better than Is-A relationship.
>4) Strive for loosely coupled design between objects that interact.
 
#### SOLID Principles
1) S - single responsibility
2) O - open close
3) L - 
4) I -
5) D - 


# Design Patterns

#### Strategy Pattern
>Defines a family of algorithms, encapsulates each one and makes them interchangeable.
Strategy lets algorithm vary independently from clients that use it.

Problem in hand?

*Duck* base class has implementations of a duck. Now the new requirement
is to make ducks fly. 

![Make ducks to fly](/assets/Strategy-problem.jpg "Make ducks fly")

We can simply add fly method to base class - problem solved.
But some rubber ducks can also fly now. so simply override to null?

What if we have some other behaviour next? So **encapsulate** the changing behaviour (fly and quack),
create a **composition** so that duck **Has-a** behaviour that can be changed during runtime.
So behaviours are a *family of encapsulated algorithm that vary independently for each duck client.*    

The implementation looks like this.
![Encapsulate Fly as algorithm so duck clients can use it independently](/assets/Strategy-solution.jpg 
"Encapsulate Fly as algorithm so duck clients can use it independently")

#### Observer Pattern
> Defines a one to many dependency between objects so that when one object changes state, 
all of its dependents are notified and updated automatically.

Problem in hand?

*WeatherData* object collects the weather data from the weather station physical device and updates the display.
Now we need three different types of devices to be updated of latest weather.

![Update the weather data on 3 different display](./assets/Observer-problem.jpg
 "Update the weather data on 3 different display")

What if we add another display tomorrow? We need to change weather data object which should be built, tested again.
Display call - *the area of change* needs to be encapsulated. Weather Data - Subject (one who holds the data) *has-a* 
reference to Display - observers (one who wants the data), so that they are notified when a new data arrives.
The observer can register/unregister for the data. Then the WeatherData can call the update method on registered observers.
The observers can be provided with data or hey can poll for data on update call.

![Make the display object as observer on the weather data subject](./assets/Observer-solution.jpg 
"Make the display object as observer on the weather data subject")
