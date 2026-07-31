# Interview Questions & Answers — Phase 08: SOLID Principles & Design Patterns

**Q1. Give a real-life example for each SOLID principle.**
A: **SRP** — a `ReportGenerator` class shouldn't also handle saving the report to a file and emailing it; each responsibility (generating, persisting, sending) belongs in its own class. **OCP** — instead of editing a `DiscountCalculator`'s `if/else` chain every time a new discount type appears, define a `DiscountStrategy` interface so new discounts are added as new classes. **LSP** — if `Square extends Rectangle` but overrides `setWidth()` to also change height, code that expects a `Rectangle` (and sets width/height independently) breaks — a classic LSP violation. **ISP** — a `Worker` interface shouldn't force a `RobotWorker` to implement `eat()` and `sleep()`; split into `Workable`, `Eatable`, `Sleepable`. **DIP** — a `PaymentProcessor` should depend on a `PaymentGateway` interface, not directly on `StripeGateway`, so the concrete gateway can be swapped or mocked.

**Q2. What's the code smell that signals a Single Responsibility Principle violation?**
A: A class that's hard to name without using "and" (e.g., `UserManagerAndEmailSender`), a class whose methods touch unrelated concerns, or a class that changes for multiple unrelated reasons (a UI tweak, a DB schema change, and a business rule change all require editing the same file).

**Q3. Explain the Liskov Substitution Principle without using the word "substitutable."**
A: If your code works correctly using a base class reference, it must keep working correctly when you swap in any subclass instance instead — the subclass shouldn't strengthen preconditions, weaken postconditions, or throw new exceptions the caller wasn't expecting, because that breaks the caller's assumptions about what "using a `Base`" means.

**Q4. When would you choose the Strategy pattern over Inheritance to vary behavior?**
A: When the behavior needs to change at *runtime* rather than being fixed at compile time via subclassing, or when you'd otherwise need a combinatorial explosion of subclasses to cover every behavior combination. Strategy lets you inject the varying algorithm as an object, so a `SortingContext` can switch between `QuickSort` and `MergeSort` strategies without being a different class for each.

**Q5. Explain the Observer pattern and where you'd actually use it.**
A: A subject maintains a list of observers and notifies them all when its state changes, without needing to know what each observer does with that notification. It's the backbone of event systems, UI reactivity, and pub/sub — e.g., a `NotificationSystem` where subscribers register interest and get notified automatically when a new event fires, decoupling the event source from every consumer of that event.

**Q6. What's the difference between the Factory Method and Abstract Factory patterns?**
A: Factory Method defines a single method for creating one type of object, letting subclasses decide which concrete class to instantiate. Abstract Factory goes a level higher — it creates *families of related objects* (e.g., a `UIFactory` that produces matching `Button`, `Checkbox`, and `Scrollbar` objects for a given theme), ensuring the objects it returns are designed to work together.

**Q7. Why shouldn't you reach for a Design Pattern just because you know it?**
A: Patterns exist to solve specific, recurring structural problems — applying one where the problem doesn't exist adds indirection and cognitive overhead without any real benefit (over-engineering). The right process is to recognize the problem first (tight coupling, an exploding conditional, an unmanageable object graph) and then reach for the pattern that fits it, not the other way around.

**Q8. Explain a Design Pattern you've actually used in a real project.**
A: (Answer this one from your own project experience — interviewers specifically want a real story, not a textbook recitation. Structure it as: what problem existed → why you picked that pattern → what changed in the code → what trade-off you accepted.)
