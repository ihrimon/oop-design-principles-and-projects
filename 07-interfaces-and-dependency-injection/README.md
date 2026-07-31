# Phase 07 — Interfaces, Abstract Classes & Dependency Injection

Detailed checklist for contracts between classes, and the technique that makes those contracts swappable and testable.

## Checklist

- [ ] Interface basics — a pure contract, no implementation (or default methods in modern languages)
- [ ] Multiple interfaces — implementing more than one (multiple inheritance of *type*, not implementation)
- [ ] Interface Segregation — breaking a large, "fat" interface into small, focused ones
- [ ] Abstract classes — partial implementation + abstract methods together
- [ ] Template Method design — fixing an algorithm's skeleton while letting subclasses override specific steps
- [ ] Interface vs Abstract Class — a clear decision rule for when to use which
- [ ] Dependency, tight coupling vs loose coupling
- [ ] Constructor Injection, Setter Injection, Interface Injection
- [ ] Inversion of Control (IoC) basics — who's responsible for creating dependencies, and why that matters

## Project

`Dependency Injection Refactor` — take a class that directly `new`s its own dependency (e.g. a `NotificationService` that does `new EmailSender()` internally) and refactor it to accept an `INotifier` interface via constructor injection.

## Interview Angle

"Why does depending on an interface instead of a concrete class make a class easier to test?"
