# Interview Questions & Answers — Phase 03: Encapsulation & Abstraction

**Q1. Explain Abstraction vs Encapsulation with a real example — not just the textbook definition.**
A: Encapsulation is about *hiding data* — bundling an object's state with the methods that operate on it, and restricting direct access (e.g., a `BankAccount`'s `balance` field is private, only changeable through `deposit()`/`withdraw()`). Abstraction is about *hiding complexity* — exposing a simple interface while hiding how it works underneath (e.g., a car's steering wheel lets you turn without knowing anything about the steering rack mechanism). You can have encapsulation without strong abstraction, and vice versa, but production code needs both.

**Q2. Why shouldn't you just make every field public and skip getters/setters?**
A: Public mutable fields mean any code anywhere can put the object into an invalid state (e.g., setting a negative balance) with no chance to validate or react. Getters/setters — when they actually contain logic, not just pass-through boilerplate — let the object protect its own invariants and give you a single place to add validation, logging, or change detection later without breaking every caller.

**Q3. What's a subtle way encapsulation gets broken even when fields are private?**
A: Returning a mutable internal object directly from a getter. Even if the field itself is private, if `getItems()` returns the actual internal `List` object, the caller can mutate it directly and bypass any validation the class would otherwise enforce. The fix is returning a copy or an immutable view.

**Q4. What's the point of designing immutable objects?**
A: An immutable object's state can't change after construction, which eliminates a whole category of bugs around unexpected mutation — especially in concurrent code, or when an object is passed around and cached by multiple parts of a system. It also makes reasoning about the object trivial: what you got at construction time is what you'll always have.

**Q5. What is "defensive programming" in the context of encapsulation?**
A: Guarding against invalid state at the boundary — validating constructor arguments and setter inputs so an object can never exist in a state that violates its own rules, rather than trusting callers to only pass valid data and hoping bugs show up somewhere downstream instead.

**Q6. Give an example of layered abstraction in a typical backend application.**
A: A controller (API layer) calls a service (business logic layer), which calls a repository (data access layer). Each layer only needs to know the *interface* of the layer below it, not its implementation — the controller doesn't know or care whether the repository is backed by Postgres or MongoDB. This is abstraction applied at the architecture level, not just within a single class.
