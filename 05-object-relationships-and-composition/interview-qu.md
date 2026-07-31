# Interview Questions & Answers — Phase 05: Object Relationships & Composition vs Inheritance

**Q1. Why "composition over inheritance" — explain with a concrete before/after example.**
A: Before: `class SportsCar extends Car` — but now every new engine type needs a new subclass, and you can't change a car's engine at runtime. After: `class Car { constructor(engine) { this.engine = engine } }` — the car *has-a* engine object (`PetrolEngine`, `ElectricEngine`, etc.) injected in, so you can swap engines freely without touching `Car`'s code or creating a new class per combination. Composition keeps the design flexible where inheritance would force a rigid, combinatorial class hierarchy.

**Q2. What's the difference between Aggregation and Composition?**
A: Both are "has-a" relationships, but they differ in ownership/lifetime. In Composition, the contained object's lifetime is tied to the container — if the container is destroyed, so is the contained object (a `House` and its `Room`s). In Aggregation, the contained object can exist independently and be shared — a `Library` has `Book`s, but a `Book` can exist and be referenced even if that particular library record is deleted.

**Q3. Explain Association, Aggregation, Composition, and Dependency in one line each.**
A: Association — a general relationship where one object uses or knows about another. Aggregation — a "has-a" relationship with independent lifetimes (weak ownership). Composition — a "has-a" relationship with tied lifetimes (strong ownership). Dependency — a temporary relationship where one object uses another, usually just within a method call, without holding a long-term reference.

**Q4. How does Dependency Injection relate to composition?**
A: DI is the mechanism that makes composition flexible in practice — instead of a class hardcoding `new ConcreteDependency()` internally, the dependency is passed in (via constructor, typically) from the outside. This means the "has-a" relationship can point to any implementation that satisfies the expected interface, which is what makes composed objects swappable and testable.

**Q5. What does "loose coupling" actually look like in code, versus tight coupling?**
A: Tight coupling: a class directly instantiates and calls methods on a specific concrete class, so changing that dependency means changing this class too. Loose coupling: a class depends on an abstraction (interface/contract) and receives a concrete implementation from outside, so the dependency can be swapped, mocked in tests, or extended without modifying the dependent class at all.

**Q6. In a Library Management System, is the relationship between `Library` and `Book` composition or aggregation? Justify it.**
A: It's typically aggregation — a `Book` can exist as a record even if it's not currently tied to a specific `Library` instance (e.g., moved between branches, or existing in a catalog before assignment), so its lifetime isn't strictly owned by one `Library` object. If the domain instead required that a `Book` only ever exists as part of exactly one `Library` and is deleted with it, composition would be the more accurate model — the "right" answer depends on the actual business rules, which is the point of asking the question.
