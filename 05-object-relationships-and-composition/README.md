# Phase 05 — Object Relationships & Composition vs Inheritance

Detailed checklist for how objects relate to each other, and why "favor composition over inheritance" is one of the most repeated rules in production OOP.

## Checklist

- [ ] Association, Aggregation, Composition, Dependency — the difference between each
- [ ] One-to-One, One-to-Many, Many-to-Many relationships
- [ ] "has-a" relationship vs "is-a" relationship
- [ ] "Favor composition over inheritance" — why this principle matters so much in practice
- [ ] Aggregation vs Composition — weak ownership vs strong ownership (lifetime dependency)
- [ ] Sharing behavior with Mixins/Traits (in languages that support them)
- [ ] Making composition flexible with Dependency Injection (preview — full topic in Phase 07)
- [ ] Loose coupling vs strong/tight coupling — recognizing which one your design has

## Projects

`Library Management System` — `Library` *has-a* collection of `Book`s, *has-a* collection of `Member`s; a `Loan` associates a `Member` with a `Book`.

`Car & Engine System` — swap engine types (`PetrolEngine`, `ElectricEngine`) at runtime via composition, without touching `Car`'s code.

## Practice Note

Work through a real example where inheritance seems tempting (e.g. `SportsCar extends Car`) and show why composing a `Car` from an `Engine`, `Wheels`, and `Transmission` object is more flexible.
