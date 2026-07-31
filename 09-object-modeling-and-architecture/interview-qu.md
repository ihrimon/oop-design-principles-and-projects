# Interview Questions & Answers — Phase 09: Object Modeling, UML, Architecture & Anti-Patterns

**Q1. What's an Anemic Domain Model, and why is it considered an anti-pattern in OOP?**
A: It's when domain classes contain only fields with getters/setters and no real behavior — all the actual business logic lives in separate "service" classes that operate on these data bags. It's considered an anti-pattern because it defeats the point of OOP: state and the behavior that should protect its invariants are separated, so nothing stops a service from putting an entity into an invalid state, and behavior ends up duplicated across services instead of centralized on the object it belongs to.

**Q2. What is the difference between an Entity, a Value Object, and a DTO?**
A: An Entity has a distinct identity that persists over time even as its attributes change (two `User` objects with the same name are still different users if their IDs differ). A Value Object has no identity — it's defined entirely by its attributes (two `Money` objects with the same amount and currency are interchangeable). A DTO (Data Transfer Object) carries data across a boundary (e.g., API response) and has no behavior at all — it's not a domain concept, just a shape for moving data.

**Q3. Explain the Dependency Rule in Clean/Onion/Hexagonal architecture.**
A: Dependencies must point inward, toward the domain/business logic core, never outward. The domain layer knows nothing about the database, the web framework, or the UI — it's the outer layers (infrastructure, presentation) that depend on and implement interfaces defined by the inner layers. This keeps the core business logic testable and framework-agnostic.

**Q4. What's the Feature Envy code smell?**
A: A method that spends more time reaching into another class's data (via its getters) than working with its own class's data. It's a signal the method is probably in the wrong class — it should likely be moved to (or delegate to) the class whose data it's so interested in.

**Q5. What's the difference between the Circular Dependency anti-pattern and normal object collaboration?**
A: Normal collaboration is one-directional or clearly layered — `A` depends on `B`, and `B` doesn't depend back on `A`. A circular dependency is when `A` depends on `B` and `B` depends on `A` (directly or through a chain), which makes the two classes impossible to understand, test, or reuse independently, and can cause real initialization-order problems in some languages.

**Q6. Why does Python's multiple inheritance not run into the same Diamond Problem crisis as naive multiple inheritance?**
A: Python resolves method lookup using C3 linearization (the MRO — Method Resolution Order), which produces a single, consistent, deterministic order to search through a class's ancestors, even in diamond-shaped hierarchies — so there's always exactly one method that gets called, decided by a well-defined algorithm rather than ambiguity.
