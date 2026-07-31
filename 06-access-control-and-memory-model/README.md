# Phase 06 — Access Control, Static Members & Memory Model

Detailed checklist for visibility rules, class-level state, and the memory concepts underneath every object.

## Checklist

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

## Common Pitfall

Reaching for a `static` method/field to "make it easy to access from anywhere" — this is almost always a hidden coupling problem in disguise.

## Interview Angle

"Why are static methods hard to mock/test?" — a strong signal question for testable design maturity.
