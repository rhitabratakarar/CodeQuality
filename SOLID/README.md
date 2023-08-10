# SOLID Principles

## S - Single Responsibility principle

A class should do one thing only.

## O - Open Closed principle

Classes are open for extension and closed for modification (using inheritance, or any other mechanisms to build a new class for new functionality extending the existing class thus declining any possible scenarios to break any existing code).

## L - Liskov's substitution principle

Defines that objects of a superclass shall be replaceable with objects of its subclasses without breaking the application (try to depend on abstractions than concretions).

## I - Interface segregation principle

Don’t force the user to use implement interfaces with unnecessary stuffs. Segregate the interfaces.

## D - Dependency Inversion principle

Defined that high level modules should not depend on low level modules and both should be depending on abstractions. (Use interfaces as types in place of classes).
