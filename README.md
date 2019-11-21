# Design and DesignPatterns
#### About

This is a repository which I use for learning design patterns. 
This is formed as a notes with the book **Head First Design Patterns**
by *Eric Freeman and Elisabeth Freeman*. Although I have also been *googling* a whenever I get questions and put the
answers here :smirk: .

I have also used this repo to learn .md - *markdown*. Some Basic programming, vim and bla bla.

#### Some Basics
These are some basics of software and programming.


#### Basic Design Principles
>1) Identify the aspects of your application that vary and 
separate (*encpsulate*) them from what stays the same.
>2) Program to an *Interface* not to an Implementation.
>3) Favour composition over inheritance. Has-A is better than Is-A relationship.


# Design Patterns

#### Strategy Pattern
>Defines a family of algorithms, encapsulates each one and makes them interchangeable.
Strategy lets algorithm vary independently from clients that use it.

Problem in hand?

So *Duck* base class has implementations of a duck. Now the new requirement
is to make ducks fly. 

![Make ducks to fly](/assets/Strategy-problem.jpg "Make ducks fly")

We can simply add fly method to base class - problem solved.
But some rubber ducks can also fly now. so simply override to null?

What if we have some other behaviour next? So **encapsulate** the changing behaviour,
create a **composition** so that duck **Has-a** behaviour that can be changed during runtime.
So behaviours are a *family of encapsulated algorithm that vary independently for each duck client.*    

So the implementation looks like this.
![Encapsulate Fly as algorithm so duck clients can use it independently](/assets/Strategy-solution.jpg 
"Encapsulate Fly as algorithm so duck clients can use it independently")