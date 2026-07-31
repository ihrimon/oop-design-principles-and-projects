# Interview Questions & Answers — Phase 02: Classes, Objects & Object Lifecycle

**Q1. What happens, step by step, when you instantiate an object with `new`?**
A: Memory is allocated for the new object on the heap, its fields are set to default values, the constructor runs (initializing fields with the values you pass in, possibly calling a parent constructor first via `super()`), and finally a reference to the fully initialized object is returned to the caller.

**Q2. What is the difference between reference equality and value equality?**
A: Reference equality checks whether two variables point to the exact same object in memory. Value equality checks whether two objects are considered "equal" based on their data, even if they're different instances. Languages usually give you a default reference-equality check (`==` or `is`) and require you to override an equality method (e.g. `equals()`, `__eq__`) to get meaningful value equality.

**Q3. Why would you overload a constructor instead of just using default parameter values?**
A: Constructor overloading lets you offer clearly named, distinct ways to build an object (e.g., from raw values vs from another object vs from a partial set of fields) in languages that don't support default/optional parameters cleanly, or where the initialization logic genuinely differs between cases rather than just filling in defaults.

**Q4. Explain constructor chaining and why it matters in an inheritance hierarchy.**
A: Constructor chaining means one constructor calls another — either another constructor in the same class, or the parent class's constructor via `super()`. It matters because a subclass's constructor should not have to re-implement the parent's initialization logic; calling `super()` ensures the parent's invariants are set up correctly before the subclass adds its own fields.

**Q5. What's the difference between a shallow copy and a deep copy?**
A: A shallow copy creates a new object but copies references to any nested objects, so mutating a nested object through the copy affects the original too. A deep copy recursively copies nested objects as well, so the copy is fully independent of the original. Cloning logic should be explicit about which one it provides — it's a common source of subtle bugs otherwise.

**Q6. Why might you reach for the Builder pattern instead of a big constructor?**
A: When an object has many optional fields, a constructor with a dozen parameters becomes error-prone (easy to pass arguments in the wrong order) and unreadable at the call site. A Builder lets you set fields one at a time with named methods and validate the final state before construction, which scales much better as the number of optional fields grows.

**Q7. What's the relationship between an object's lifecycle and garbage collection?**
A: An object's lifecycle is allocation → initialization → use → and eventually becoming unreachable. In garbage-collected languages, you don't manually free memory — once nothing references an object anymore, the garbage collector reclaims it. This is why lingering references (e.g., objects added to a collection and never removed) are a common cause of memory leaks even without manual memory management.
