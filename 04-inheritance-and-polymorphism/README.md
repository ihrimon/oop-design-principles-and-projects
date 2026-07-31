# Phase 04 — Inheritance & Polymorphism

Detailed checklist for code reuse through hierarchy, and behavior that changes shape at runtime.

## Checklist

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

## Project

`Shape Drawing System` — a base `Shape` class with `Circle`, `Rectangle`, `Triangle` overriding `area()` and `draw()`; a renderer that works polymorphically over any `Shape`.

## Common Pitfalls

Deep inheritance chains that are hard to reason about; overriding a method in a way that violates the parent's contract (a Liskov Substitution violation — see Phase 08).
