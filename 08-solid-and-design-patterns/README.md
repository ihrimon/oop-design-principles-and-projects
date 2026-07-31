# Phase 08 — SOLID Principles & Design Patterns

Detailed checklist for the five rules and the pattern catalog every production engineer is expected to know — and know when to leave alone.

## SOLID Principles

- [ ] **S** — Single Responsibility Principle (a class should have only one reason to change)
- [ ] **O** — Open/Closed Principle (open for extension, closed for modification)
- [ ] **L** — Liskov Substitution Principle (a subclass must be substitutable for its parent without breaking correctness)
- [ ] **I** — Interface Segregation Principle (clients shouldn't be forced to depend on methods they don't use)
- [ ] **D** — Dependency Inversion Principle (depend on abstractions, not concrete implementations)
- [ ] For each principle: write a "bad code → refactored code" example, and learn to recognize the code smell that signals a violation

**Project:** `Refactor Legacy Code` — take a real "God Class" and split/refactor it until it satisfies all five SOLID principles.

## Design Patterns — Creational

- [ ] Singleton — ensuring only one instance exists (and its testing/global-state downsides)
- [ ] Factory Method — delegating object creation logic to subclasses
- [ ] Abstract Factory — creating families of related objects
- [ ] Builder — constructing a complex object step by step
- [ ] Prototype — creating new objects by cloning existing ones

## Design Patterns — Structural

- [ ] Adapter — making incompatible interfaces compatible
- [ ] Bridge — decoupling abstraction from implementation so each can vary independently
- [ ] Composite — treating individual objects and groups of objects uniformly in a tree structure
- [ ] Decorator — dynamically adding behavior to an object without subclassing
- [ ] Facade — a simple interface in front of a complex subsystem
- [ ] Flyweight — sharing common state across many similar objects to save memory
- [ ] Proxy — controlling access to an object (lazy loading, access control, caching)

## Design Patterns — Behavioral

- [ ] Observer — notifying subscribers on an event/state change
- [ ] Strategy — swapping an algorithm at runtime
- [ ] State — changing behavior based on an object's internal state
- [ ] Command — encapsulating a request as an object
- [ ] Chain of Responsibility — passing a request through a chain of handlers
- [ ] Iterator — traversing a collection without exposing its internal structure
- [ ] Mediator — reducing direct coupling between objects
- [ ] Memento — capturing/restoring an object's internal state (undo/redo)
- [ ] Template Method — see Phase 07
- [ ] Visitor — adding new operations to a class hierarchy without modifying it

## For every pattern you study, answer all of these

- [ ] Problem it solves
- [ ] Solution / how it works
- [ ] UML sketch
- [ ] Implementation in your language
- [ ] A real-world example
- [ ] Advantages
- [ ] Disadvantages
- [ ] When to use it
- [ ] When **not** to use it (don't reach for a pattern just because you know it)

## Projects

`Notification System` — Observer pattern for subscribers + Factory pattern for channel creation (Email/SMS/Push).

`Plugin/Extension System` — extensible architecture combining Decorator and Strategy.
