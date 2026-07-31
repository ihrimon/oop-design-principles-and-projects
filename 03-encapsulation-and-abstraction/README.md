# Phase 03 — Encapsulation & Abstraction

Detailed checklist for the two pillars people confuse most often: hiding state (Encapsulation) vs hiding complexity (Abstraction).

## Checklist

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

## Projects

`Bank Account` — balance is private, mutated only through `deposit()`/`withdraw()` methods that enforce invariants (never negative, minimum balance rules).

`Payment System` — expose a single `pay()` method; hide gateway-specific logic (Stripe/PayPal/bKash) behind it.

## Interview Angle

"Explain Abstraction vs Encapsulation with a real example — not just the textbook definition."
