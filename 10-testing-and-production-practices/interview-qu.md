# Interview Questions & Answers — Phase 10: Testing, Refactoring, Production Practices & Projects

**Q1. Why does Dependency Injection make unit testing so much easier?**
A: If a class's dependencies are injected (typically via constructor) rather than created internally, a test can pass in mock/stub implementations instead of the real ones. This lets you test the class's own logic in isolation — no real database, network call, or filesystem access needed — and lets you simulate edge cases (errors, empty results) that would be hard to trigger with real dependencies.

**Q2. How do you use tests to verify Liskov Substitution compliance?**
A: Write a shared test suite against the parent class's contract (its expected behavior/invariants), then run that exact same suite against every subclass. If a subclass fails a test that the parent and its siblings pass, it's violating the parent's contract — a concrete, automated way to catch LSP violations instead of relying on manual reasoning.

**Q3. What's the difference between a mock and a test double, generally speaking?**
A: "Test double" is the umbrella term for any stand-in object used in tests (dummies, stubs, fakes, mocks, spies). A mock specifically is a test double that also records how it was called (which methods, how many times, with what arguments) so the test can assert on those interactions — not just on the return value it provided.

**Q4. What's the "Extract Method" refactoring, and when should you reach for it?**
A: It means pulling a chunk of code out of a larger method into its own well-named method. Reach for it when a method is doing more than one clearly nameable thing, when a block of logic is duplicated elsewhere, or when a method has grown long enough that understanding it requires scrolling — the extracted method's name then documents intent better than a comment would.

**Q5. What is "Replace Conditional with Polymorphism," and why prefer it over a big switch statement?**
A: Instead of a `switch`/`if-else` chain that branches on a type field to decide behavior, each type gets its own class implementing the varying method, and the caller just invokes the method polymorphically. It's preferable because adding a new type means adding a new class (Open/Closed Principle), rather than editing — and risking breaking — an existing conditional that every other type also depends on.

**Q6. In production code, why is "don't use a Design Pattern just because you know it" actually a best practice, not just a caution?**
A: Applying a pattern where the underlying problem doesn't exist adds a layer of indirection (extra classes, extra abstraction) that future readers have to mentally unwind for no payoff — it makes code harder to read, not easier. The best practice is recognizing the *symptom* first (rigid conditionals, unswappable dependencies, an exploding number of subclasses) and only then reaching for the pattern that specifically addresses that symptom.

**Q7. How would you explain TDD's red-green-refactor cycle in one sentence each?**
A: Red — write a failing test for behavior that doesn't exist yet, so you know exactly what "done" means. Green — write the simplest code that makes the test pass, without over-engineering. Refactor — clean up the implementation (and the test, if needed) now that you have a passing test as a safety net against regressions.
