# 🧱 OOP Mastery Roadmap — Junior → Production Engineer Track

> A complete, **10-phase** Object-Oriented Programming checklist — built for a junior engineer who needs OOP not just for interviews, but for real, day-to-day production work: reading enterprise codebases, designing maintainable classes, applying SOLID and Design Patterns correctly, and knowing _when not to_ use them. Each phase moves from concept → industry best-practice rule → hands-on project, so this document doubles as both a study tracker and a portfolio plan.

## 📑 Table of Contents

- [Phase 01 — Programming Foundations \& Object Thinking](#phase-01--programming-foundations--object-thinking)
- [Phase 02 — Classes, Objects \& Object Lifecycle](#phase-02--classes-objects--object-lifecycle)
- [Phase 03 — Encapsulation \& Abstraction](#phase-03--encapsulation--abstraction)
- [Phase 04 — Inheritance \& Polymorphism](#phase-04--inheritance--polymorphism)
- [Phase 05 — Object Relationships \& Composition vs Inheritance](#phase-05--object-relationships--composition-vs-inheritance)
- [Phase 06 — Access Control, Static Members \& Memory Model](#phase-06--access-control-static-members--memory-model)
- [Phase 07 — Interfaces, Abstract Classes \& Dependency Injection](#phase-07--interfaces-abstract-classes--dependency-injection)
- [Phase 08 — SOLID Principles \& Design Patterns](#phase-08--solid-principles--design-patterns)
- [Phase 09 — Object Modeling, UML, Architecture \& Anti-Patterns](#phase-09--object-modeling-uml-architecture--anti-patterns)
- [Phase 10 — Testing, Refactoring, Production Practices \& Projects](#phase-10--testing-refactoring-production-practices--projects)
- [🎯 Final Production Engineer Checklist](#-final-production-engineer-checklist)

## Phase 01 — Programming Foundations & Object Thinking

- [ ] Variables, data types, primitive vs reference types
- [ ] Stack vs Heap, value vs reference, scope, memory allocation basics
- [ ] Control flow, collections, modules & packages (the pre-OOP building blocks)
- [ ] Procedural vs Object-Oriented programming — the difference, and _why_ OOP exists
- [ ] The "everything is an object" mindset — modeling real-world entities in code
- [ ] The Four Pillars overview: Encapsulation, Abstraction, Inheritance, Polymorphism
- [ ] Class vs Object — blueprint vs instance
- [ ] State vs Behavior — the relationship between attributes (data) and methods (functions)
- [ ] Message passing — how objects communicate with each other
- [ ] Responsibility-Driven Design — thinking in terms of "who owns this responsibility," not just "what data exists"
- [ ] Where OOP fits and where it doesn't (cases where a functional/procedural approach is the better fit)

🎯 **Projects:** [Library Management →](./01-programming-foundations/library-management/PROJECT_PLAN.md)

📖 **[Deep dive → 01-programming-foundations](./01-programming-foundations/README.md)**

## Phase 02 — Classes, Objects & Object Lifecycle

- [ ] Class definition syntax (in your primary language)
- [ ] Object instantiation (`new` keyword, factory functions, etc.)
- [ ] Fields, instance variables/attributes, instance methods
- [ ] `this` / `self` keyword — referring to the current instance
- [ ] Multiple objects from the same class — independent state
- [ ] Object comparison — reference equality vs value equality
- [ ] Nested/inner classes and their practical use cases
- [ ] Default constructor vs parameterized constructor
- [ ] Constructor overloading (in languages that support it) & constructor chaining (`super()`)
- [ ] Object creation lifecycle: memory allocation → initialization → usage → destruction
- [ ] Destructor/finalizer concept and its relationship with garbage collection
- [ ] Copy constructor / cloning — shallow copy vs deep copy
- [ ] Solving complex constructor problems with the Builder pattern (preview — full pattern in Phase 08)

🎯 **Projects:** Student Management System →

⚠ **Common pitfall:** Confusing "class" (blueprint) with "object" (instance) when explaining code out loud — a frequent interview stumble.

📖 **[Deep dive → 02-classes-and-objects](./02-classes-and-objects/README.md)**

## Phase 03 — Encapsulation & Abstraction

- [ ] What is Encapsulation, and why internal state shouldn't be exposed directly
- [ ] Private, protected, and public fields — the practical difference between them
- [ ] Getter/Setter methods — controlled access, not just boilerplate
- [ ] Protecting invariants — keeping validation logic inside setters, not scattered across callers
- [ ] Common ways encapsulation gets broken (public mutable fields, getters returning internal mutable objects directly)
- [ ] Designing immutable/readonly objects
- [ ] Defensive programming — guarding against invalid state at the boundary
- [ ] Abstraction vs Encapsulation — the difference, clearly (a very common interview mix-up)
- [ ] Exposing the "what," hiding the "how"
- [ ] Abstract classes and interfaces as abstraction tools
- [ ] Real-world example: a car's steering wheel (interface) vs the engine's internal mechanism (implementation)
- [ ] Layered abstraction — API layer, service layer, repository layer

🎯 **Projects:** Bank Account → | Payment System →

📖 **[Deep dive → 03-encapsulation-and-abstraction](./03-encapsulation-and-abstraction/README.md)**

## Phase 04 — Inheritance & Polymorphism

- [ ] Parent/child class, single and multilevel inheritance
- [ ] Code reuse via inheritance, method extension, hierarchical inheritance
- [ ] `super` keyword — calling the parent constructor/method
- [ ] Multiple inheritance — the Diamond Problem and language-specific solutions
- [ ] Correctly identifying an "is-a" relationship (vs forcing one that doesn't exist)
- [ ] Misuse of inheritance — cases where composition would have been more appropriate
- [ ] Sealed/final classes — when you need to explicitly block further inheritance
- [ ] Method Overloading (compile-time polymorphism) vs Method Overriding (runtime polymorphism)
- [ ] Dynamic method dispatch — how the correct overridden method gets resolved at runtime
- [ ] Duck typing (dynamically-typed languages like Python/JS)
- [ ] Operator overloading (in languages that support it) & parametric polymorphism/Generics
- [ ] Using polymorphism to eliminate long `if/else`/`switch` chains — the role of the Strategy pattern

🎯 **Projects:** Shape Drawing System →

⚠ **Common pitfalls:** Deep inheritance chains that are hard to reason about; overriding a method in a way that violates the parent's contract (a Liskov Substitution violation — see Phase 08).

📖 **[Deep dive → 04-inheritance-and-polymorphism](./04-inheritance-and-polymorphism/README.md)**

## Phase 05 — Object Relationships & Composition vs Inheritance

- [ ] Association, Aggregation, Composition, Dependency — the difference between each
- [ ] One-to-One, One-to-Many, Many-to-Many relationships
- [ ] "has-a" relationship vs "is-a" relationship
- [ ] "Favor composition over inheritance" — why this principle matters so much in practice
- [ ] Aggregation vs Composition — weak ownership vs strong ownership (lifetime dependency)
- [ ] Sharing behavior with Mixins/Traits (in languages that support them)
- [ ] Making composition flexible with Dependency Injection (preview — full topic in Phase 07)
- [ ] Loose coupling vs strong/tight coupling — recognizing which one your design has

🎯 **Projects:** Library Management System → | Car & Engine System →

📖 **[Deep dive → 05-object-relationships-and-composition](./05-object-relationships-and-composition/README.md)**

## Phase 06 — Access Control, Static Members & Memory Model

- [ ] `public`, `private`, `protected` — visibility rules and accessibility
- [ ] Package-private / internal (language-specific) and module-level encapsulation (e.g. privacy via closures in JS)
- [ ] What architectural problems arise from ignoring access modifiers (leaky internals, fragile refactors)
- [ ] Static variables — class-level shared state, and its risks
- [ ] Static methods — utility logic callable without an instance
- [ ] Static blocks/initializers
- [ ] Misuse of static — the specific risk to testability and flexibility (why static makes mocking hard)
- [ ] The relationship between the Singleton pattern and `static` (preview — Phase 08)
- [ ] Stack vs Heap memory, reference variables, garbage collection
- [ ] Memory leaks in OOP code — lingering references, unclosed resources, forgotten event listeners

⚠ **Common pitfall:** Reaching for a `static` method/field to "make it easy to access from anywhere" — this is almost always a hidden coupling problem in disguise.

📖 **[Deep dive → 06-access-control-and-memory-model](./06-access-control-and-memory-model/README.md)**

## Phase 07 — Interfaces, Abstract Classes & Dependency Injection

- [ ] Interface basics — a pure contract, no implementation (or default methods in modern languages)
- [ ] Multiple interfaces — implementing more than one (multiple inheritance of _type_, not implementation)
- [ ] Interface Segregation — breaking a large, "fat" interface into small, focused ones
- [ ] Abstract classes — partial implementation + abstract methods together
- [ ] Template Method design — fixing an algorithm's skeleton while letting subclasses override specific steps
- [ ] Interface vs Abstract Class — a clear decision rule for when to use which
- [ ] Dependency, tight coupling vs loose coupling
- [ ] Constructor Injection, Setter Injection, Interface Injection
- [ ] Inversion of Control (IoC) basics — who's responsible for creating dependencies, and why that matters

🎯 **Projects:** Dependency Injection Refactor →

📖 **[Deep dive → 07-interfaces-and-dependency-injection](./07-interfaces-and-dependency-injection/README.md)**

## Phase 08 — SOLID Principles & Design Patterns

- [ ] **S** — Single Responsibility Principle (a class should have only one reason to change)
- [ ] **O** — Open/Closed Principle (open for extension, closed for modification)
- [ ] **L** — Liskov Substitution Principle (a subclass must be substitutable for its parent without breaking correctness)
- [ ] **I** — Interface Segregation Principle (clients shouldn't be forced to depend on methods they don't use)
- [ ] **D** — Dependency Inversion Principle (depend on abstractions, not concrete implementations)
- [ ] For each principle: write a "bad code → refactored code" example, and learn to recognize the code smell that signals a violation

🎯 **Projects:** Refactor Legacy Code →

- [ ] Singleton — ensuring only one instance exists (and its testing/global-state downsides)
- [ ] Factory Method — delegating object creation logic to subclasses
- [ ] Abstract Factory — creating families of related objects
- [ ] Builder — constructing a complex object step by step
- [ ] Prototype — creating new objects by cloning existing ones
- [ ] Adapter — making incompatible interfaces compatible
- [ ] Bridge — decoupling abstraction from implementation so each can vary independently
- [ ] Composite — treating individual objects and groups of objects uniformly in a tree structure
- [ ] Decorator — dynamically adding behavior to an object without subclassing
- [ ] Facade — a simple interface in front of a complex subsystem
- [ ] Flyweight — sharing common state across many similar objects to save memory
- [ ] Proxy — controlling access to an object (lazy loading, access control, caching)
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

**For every pattern you study, answer all of these — not just "how it's implemented":**

- [ ] Problem it solves
- [ ] Solution / how it works
- [ ] UML sketch
- [ ] Implementation in your language
- [ ] A real-world example
- [ ] Advantages
- [ ] Disadvantages
- [ ] When to use it
- [ ] When **not** to use it (don't reach for a pattern just because you know it)

🎯 **Projects:** Notification System → | Plugin/Extension System →

📖 **[Deep dive → 08-solid-and-design-patterns](./08-solid-and-design-patterns/README.md)**

## Phase 09 — Object Modeling, UML, Architecture & Anti-Patterns

- [ ] Entity, Value Object, Domain Object, DTO — the practical difference between each
- [ ] Business rules living inside the domain model, not scattered in controllers
- [ ] Domain modeling fundamentals
- [ ] UML: class diagrams (attribute/method/visibility notation), sequence diagrams, activity diagrams, use case diagrams, object diagrams
- [ ] Relationship notation: association, aggregation, composition, inheritance, dependency
- [ ] Multiplicity: 1-to-1, 1-to-many, many-to-many
- [ ] Building the habit of sketching a diagram _before_ writing classes, not after
- [ ] Layered Architecture, Clean Architecture, Onion Architecture, Hexagonal Architecture
- [ ] Domain-Driven Design (DDD) basics and the Dependency Rule (dependencies point inward, toward the domain)
- [ ] Enterprise OOP building blocks: Entity, Repository, Service, Controller, Mapper, DTO, Value Object, Domain Service, Specification, Policy, Aggregate, Factory
- [ ] OOP across languages — know the differences, don't assume they're all identical:
  - [ ] JavaScript — prototype-based inheritance, and what ES6 `class` really compiles down to
  - [ ] TypeScript — interfaces, generics, access modifiers, abstract classes
  - [ ] Python — duck typing, `self`, multiple inheritance (MRO/C3 linearization), dunder methods (`__init__`, `__str__`)
  - [ ] Java — strict static typing, interfaces with default methods, checked exceptions
  - [ ] PHP — traits, abstract classes, interfaces, magic methods
- [ ] Anti-patterns & code smells to recognize on sight:
  - [ ] God Object — piling too much responsibility into one class
  - [ ] Tight Coupling — a change in one class rippling across many others
  - [ ] Anemic Domain Model — classes with only getters/setters and no real behavior
  - [ ] Deep Inheritance Hierarchy — chains so long no one can trace behavior
  - [ ] Circular Dependency — two classes depending on each other
  - [ ] Feature Envy — a method that reaches into another class's data more than its own

📖 **[Deep dive → 09-object-modeling-and-architecture](./09-object-modeling-and-architecture/README.md)**

## Phase 10 — Testing, Refactoring, Production Practices & Projects

- [ ] Unit testing individual classes/methods in isolation
- [ ] Mock objects & test doubles — an interface/abstraction makes this dramatically easier (the real payoff of Dependency Inversion)
- [ ] Testable design — constructor injection specifically for testability
- [ ] Using tests to verify a subclass actually respects Liskov Substitution
- [ ] TDD basics
- [ ] Recognizing code smells before they calcify into architecture
- [ ] Extract Method, Extract Class, Rename Method, Remove Duplication
- [ ] Replace Conditional with Polymorphism
- [ ] Exceptions, custom exception hierarchies
- [ ] Graceful recovery and resource cleanup (try/finally, `using`/context managers, disposal patterns)
- [ ] DRY, KISS, YAGNI — and knowing when _not_ to over-apply them
- [ ] Favor composition, keep classes small and single-purpose (SRP in practice)
- [ ] Don't blindly add getters/setters to every field — keep meaningful behavior on the object, not just data access
- [ ] Keep immutability as the default wherever practical
- [ ] Use Dependency Injection to keep classes loosely coupled
- [ ] Don't use a Design Pattern just because you know it — pick the one that fits the actual problem
- [ ] Documentation and code review as part of the engineering habit, not an afterthought
- [ ] Keep a personal OOP code-review checklist and actually apply it to your own PRs before requesting review

📖 **[Deep dive → 10-testing-and-production-practices](./10-testing-and-production-practices/README.md)**

## 🎯 Final Production Engineer Checklist

- [ ] Strong OOP fundamentals — can explain every pillar with a real example, not just a definition
- [ ] Object thinking — can model a new domain into classes before writing any code
- [ ] All five SOLID principles, applied and recognized when violated
- [ ] Design Patterns — know the catalog, and more importantly, know when _not_ to use one
- [ ] Comfortable reading and drawing UML
- [ ] Understands Clean/Onion/Hexagonal architecture and the dependency rule
- [ ] Knows enterprise-level building blocks (Repository, Service, DTO, Aggregate, Mapper)
- [ ] Uses Dependency Injection by default for testability and loose coupling
- [ ] Can do domain modeling for a real business problem
- [ ] Writes tests that would actually catch a regression
- [ ] Refactors confidently — recognizes code smells and fixes them with the right technique
- [ ] Applies production code practices (DRY/KISS/YAGNI, immutability, code review discipline)
- [ ] Has shipped real projects across beginner → enterprise difficulty
- [ ] Interview-ready — can explain design decisions out loud, not just recite terms
