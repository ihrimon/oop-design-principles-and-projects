# Interview Questions & Answers — Phase 07: Interfaces, Abstract Classes & Dependency Injection

**Q1. Interface vs Abstract Class — when do you use which?**
A: Use an interface when you're defining a pure contract — a set of methods any implementing class must provide, with no shared implementation (or only default methods in modern languages), especially when unrelated classes need to satisfy the same contract. Use an abstract class when you have *shared implementation* to provide alongside some methods that must be overridden — i.e., a real "is-a" relationship where subclasses share common code, not just a shared signature.

**Q2. Why does depending on an interface instead of a concrete class make a class easier to test?**
A: If a class depends on a concrete class, tests are stuck exercising the real implementation (a real database connection, a real email sender). If it depends on an interface, tests can substitute a fake/mock implementation that returns controlled responses instantly, without side effects — letting you test the class's own logic in isolation rather than its dependency's behavior.

**Q3. What is Interface Segregation, and why does it matter in practice?**
A: It means breaking a large "fat" interface into smaller, focused ones, so a class only has to implement the methods it actually needs. Without it, implementing classes end up with dummy/no-op implementations of methods irrelevant to them just to satisfy the interface — a sign the interface is doing too much and should be split.

**Q4. Explain the three main forms of Dependency Injection.**
A: Constructor Injection — dependencies are passed into the constructor and stored as fields, the most common and testable form since dependencies are required upfront. Setter Injection — dependencies are set via a setter method after construction, useful for optional dependencies. Interface Injection — the dependency itself defines a method the client must implement to receive the injection, less common in practice.

**Q5. What is Inversion of Control, and how does it relate to Dependency Injection?**
A: IoC is the broader principle that a class shouldn't control the creation of its own dependencies — that responsibility is inverted to something external (a caller, a framework, a DI container). Dependency Injection is the specific technique used to achieve IoC: dependencies are handed to the class rather than the class reaching out and constructing them itself.

**Q6. You have a `NotificationService` that does `new EmailSender()` internally. What's wrong with this, and how would you fix it?**
A: It's tightly coupled to one concrete implementation — you can't swap in SMS/push notifications without editing `NotificationService`, and you can't unit-test it without actually sending an email. The fix: define an `INotifier` interface with a `send()` method, have `EmailSender` implement it, and inject an `INotifier` into `NotificationService`'s constructor instead of instantiating it internally.
