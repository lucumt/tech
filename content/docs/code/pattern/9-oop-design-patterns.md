---
title: "9种面向对象的设计模式"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![10个良好编码规则](/img/code/pattern/9-oop-design-patterns.gif)

9 OOP Design Patterns You Must Know

These patterns can be divided into 3 categories:

A - **Creational Patterns**
Deal with object creation mechanism to decouple the client code from concrete classes.

1. Factory Pattern: Centralizes object creation logic and returns different subclasses based on input
2. Singleton Pattern: Ensures only one instance of a class exists and provides global access to it.
3. Builder Pattern: Constructs complex objects step-by-step, allowing optional configuration.

B - **Structural Patterns**
Help compose classes and objects into larger structures.

1. Adapter Pattern: Allows incompatible interfaces to work together by translating one interface into another.
2. Decorator Pattern: Adds new behavior to objects dynamically without altering their original structure.
3. Proxy Pattern: Acts as a placeholder for accessing another object.

C - **Behavioral Patterns**
Focus on communication and interaction between objects.

1. Strategy Pattern: Allows selecting an algorithm or behavior from a family of interchangeable strategies at runtime.
2. Observer Pattern: Enables a one-to-many dependency so that when one object changes state, all its dependents are notified.
3. Command Pattern: An object encapsulates all information needed to perform an action or trigger an event.