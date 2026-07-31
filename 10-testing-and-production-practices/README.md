# Phase 10 — Testing, Refactoring, Production Practices & Projects

Detailed checklist for making OOP code testable, keeping it clean over time, and proving mastery through real projects and interview readiness.

## Testing OOP Code

- [ ] Unit testing individual classes/methods in isolation
- [ ] Mock objects & test doubles — an interface/abstraction makes this dramatically easier (the real payoff of Dependency Inversion)
- [ ] Testable design — constructor injection specifically for testability
- [ ] Using tests to verify a subclass actually respects Liskov Substitution
- [ ] TDD basics

## Refactoring & Error Handling

- [ ] Recognizing code smells before they calcify into architecture
- [ ] Extract Method, Extract Class, Rename Method, Remove Duplication
- [ ] Replace Conditional with Polymorphism
- [ ] Exceptions, custom exception hierarchies
- [ ] Graceful recovery and resource cleanup (try/finally, `using`/context managers, disposal patterns)

## Production Best Practices

- [ ] DRY, KISS, YAGNI — and knowing when *not* to over-apply them
- [ ] Favor composition, keep classes small and single-purpose (SRP in practice)
- [ ] Don't blindly add getters/setters to every field — keep meaningful behavior on the object, not just data access
- [ ] Keep immutability as the default wherever practical
- [ ] Use Dependency Injection to keep classes loosely coupled
- [ ] Don't use a Design Pattern just because you know it — pick the one that fits the actual problem
- [ ] Documentation and code review as part of the engineering habit, not an afterthought
- [ ] Keep a personal OOP code-review checklist and actually apply it to your own PRs before requesting review

## Practical Projects — build these in order of difficulty

**Beginner**

- [ ] Student Management System
- [ ] Library Management System
- [ ] Banking System
- [ ] Hospital Management System
- [ ] Inventory Management System

**Intermediate**

- [ ] Hotel Booking System
- [ ] Food Delivery System
- [ ] CRM (Customer Relationship Management)
- [ ] Task Management System
- [ ] E-Commerce Domain Model + Cart System (Composition + Strategy pattern for pricing/discounts)

**Advanced**

- [ ] Parking Lot System (a classic interview design problem — practices every pillar together)
- [ ] Airline Reservation System
- [ ] Ride-Sharing System
- [ ] Payment Gateway Integration Simulator (Adapter pattern + Interface Segregation)
- [ ] Game Character System / RPG (Polymorphism + State pattern for idle/attack/dead states)
- [ ] Warehouse Management System

**Enterprise**

- [ ] ERP Module
- [ ] HRM (Human Resource Management)
- [ ] POS (Point of Sale)
- [ ] Healthcare System
- [ ] Accounting Software

## Interview Question Bank

- [ ] Explain "Abstraction vs Encapsulation" with a real example, not just definitions
- [ ] Explain "Overloading vs Overriding" with code
- [ ] "Interface vs Abstract Class" — when to use which, and why
- [ ] What is the Diamond Problem, and how is it resolved in your language(s) of choice
- [ ] Give a real-life example for each SOLID principle
- [ ] Why "composition over inheritance" — with a concrete before/after example
- [ ] Explain a Design Pattern you've actually used in a real project (not a textbook one)
- [ ] Why are static methods hard to mock — explain from a testing perspective
- [ ] Scenario-based design questions (e.g. "design a parking lot," "design a notification system")
- [ ] Code review / refactoring / debugging questions on OOP code someone else wrote
