# Interview Questions & Answers — Phase 04: Inheritance & Polymorphism

**Q1. What is the Diamond Problem, and how is it resolved?**
A: It arises when a class inherits from two classes that both inherit from a common base class, and the two paths override the same method differently — the compiler can't tell which version the diamond's bottom class should use. Languages resolve it differently: Java/C# disallow multiple class inheritance entirely (only single inheritance + multiple interfaces); C++ requires virtual inheritance to share the base; Python uses the C3 linearization algorithm (MRO) to define a deterministic method resolution order.

**Q2. Explain Method Overloading vs Method Overriding with examples.**
A: Overloading is defining multiple methods with the *same name but different parameter signatures* in the same class — resolved at compile time based on the arguments you pass (compile-time/static polymorphism). Overriding is a subclass providing its *own implementation of a method that already exists in its parent class*, with the same signature — resolved at runtime based on the actual object type (runtime/dynamic polymorphism).

**Q3. How does dynamic method dispatch actually work at runtime?**
A: When you call a method on an object through a reference typed as the parent class, the runtime looks at the object's *actual* type (not the reference's declared type) to decide which overridden method to execute. This is what lets a single line of code like `shape.draw()` call `Circle.draw()` or `Rectangle.draw()` depending on what `shape` actually points to.

**Q4. When is inheritance the wrong tool, even if an "is-a" relationship technically exists?**
A: When the subclass needs to override or disable most of the parent's behavior to fit, when the hierarchy grows deep and fragile, or when the relationship might change over the object's lifetime (a `Employee` isn't always a `Manager`, but could become one). In these cases, composition — the object *has-a* role or capability, swappable at runtime — models reality more accurately than a rigid inheritance chain.

**Q5. What is duck typing, and which languages rely on it?**
A: "If it walks like a duck and quacks like a duck, treat it as a duck" — code doesn't check an object's declared type, only whether it has the method/attribute being called. Python and JavaScript lean on this heavily: a function can accept any object that implements `.read()`, regardless of its class hierarchy, because there's no compile-time interface check.

**Q6. How does polymorphism help you avoid long `if/else` or `switch` chains?**
A: Instead of writing `if (type == 'circle') ... else if (type == 'square') ...` to decide behavior, you give each type its own class with its own implementation of the shared method, and let dynamic dispatch pick the right one. This is exactly the mechanism behind the Strategy pattern — adding a new type means adding a new class, not editing an existing conditional.
