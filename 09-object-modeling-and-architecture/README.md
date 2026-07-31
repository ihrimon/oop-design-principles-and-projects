# Phase 09 — Object Modeling, UML, Architecture & Anti-Patterns

Detailed checklist for modeling a domain correctly, communicating design with diagrams, structuring an application in layers, and recognizing OOP gone wrong.

## Checklist

- [ ] Entity, Value Object, Domain Object, DTO — the practical difference between each
- [ ] Business rules living inside the domain model, not scattered in controllers
- [ ] Domain modeling fundamentals
- [ ] UML: class diagrams (attribute/method/visibility notation), sequence diagrams, activity diagrams, use case diagrams, object diagrams
- [ ] Relationship notation: association, aggregation, composition, inheritance, dependency
- [ ] Multiplicity: 1-to-1, 1-to-many, many-to-many
- [ ] Building the habit of sketching a diagram *before* writing classes, not after
- [ ] Layered Architecture, Clean Architecture, Onion Architecture, Hexagonal Architecture
- [ ] Domain-Driven Design (DDD) basics and the Dependency Rule (dependencies point inward, toward the domain)
- [ ] Enterprise OOP building blocks: Entity, Repository, Service, Controller, Mapper, DTO, Value Object, Domain Service, Specification, Policy, Aggregate, Factory

## OOP Across Languages

- [ ] JavaScript — prototype-based inheritance, and what ES6 `class` really compiles down to
- [ ] TypeScript — interfaces, generics, access modifiers, abstract classes
- [ ] Python — duck typing, `self`, multiple inheritance (MRO/C3 linearization), dunder methods (`__init__`, `__str__`)
- [ ] Java — strict static typing, interfaces with default methods, checked exceptions
- [ ] PHP — traits, abstract classes, interfaces, magic methods

## Anti-Patterns & Code Smells

- [ ] God Object — piling too much responsibility into one class
- [ ] Tight Coupling — a change in one class rippling across many others
- [ ] Anemic Domain Model — classes with only getters/setters and no real behavior
- [ ] Deep Inheritance Hierarchy — chains so long no one can trace behavior
- [ ] Circular Dependency — two classes depending on each other
- [ ] Feature Envy — a method that reaches into another class's data more than its own

## Interview Angle

"What's an Anemic Domain Model, and why is it considered an anti-pattern in OOP?"
