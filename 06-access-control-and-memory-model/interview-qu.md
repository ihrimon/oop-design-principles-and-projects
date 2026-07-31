# Interview Questions & Answers — Phase 06: Access Control, Static Members & Memory Model

**Q1. Why are static methods hard to mock/test?**
A: A static method is called directly on the class, not through an object instance you control — so there's no seam to substitute a fake implementation at test time (no interface reference to swap out). Tests end up calling the real static method, which is a problem when it touches a database, the filesystem, or the network. This is why testable designs favor instance methods reached through an injected interface instead.

**Q2. What's the actual difference between `public`, `private`, and `protected`?**
A: `public` — accessible from anywhere. `private` — accessible only within the declaring class itself. `protected` — accessible within the declaring class and its subclasses (and sometimes same-package code, depending on the language), but not from unrelated external code. The goal of tightening visibility is to only expose what callers actually need, so the internal implementation can change freely.

**Q3. What risk does overusing `static` shared state introduce?**
A: Static fields are shared across every use of the class for the entire lifetime of the program, which creates hidden global state — any part of the codebase can read or mutate it, making bugs hard to trace and tests unpredictable if they run in the same process (one test's static mutation leaks into the next test). It also usually signals a missed opportunity for proper dependency injection.

**Q4. How does the Singleton pattern relate to `static`?**
A: A Singleton typically uses a static field to hold the one-and-only instance, and a static method (e.g., `getInstance()`) to access it, lazily creating it on first use. The static field is what guarantees there's exactly one instance shared across the whole application — which is also exactly why Singletons share the same testability downsides as any other static-heavy design.

**Q5. Explain the difference between stack memory and heap memory.**
A: Stack memory holds function call frames — local variables and references, automatically reclaimed the moment a function returns; it's fast and has a fixed, limited size. Heap memory holds objects created with `new` (or equivalent) — it persists as long as something references it, is managed by the garbage collector, and is larger but slower to allocate/deallocate than the stack.

**Q6. What causes a memory leak in a garbage-collected OOP language, if the GC handles cleanup automatically?**
A: A leak happens when something still holds a reference to an object that's logically no longer needed — e.g., an event listener that's never unsubscribed, an item added to a static/global collection and never removed, or a cache with no eviction policy. The GC can only reclaim objects that are truly unreachable; it can't tell the difference between "still needed" and "forgotten but referenced."
