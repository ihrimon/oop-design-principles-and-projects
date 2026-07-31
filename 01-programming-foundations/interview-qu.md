# Interview Questions & Answers — Phase 01: Programming Foundations & Object Thinking

**Q1. Why does OOP exist? What problem does it solve that procedural code doesn't?**
A: Procedural code organizes a program around functions operating on shared, often global data — as a codebase grows, it becomes hard to know which function can change which data, and changes ripple unpredictably. OOP groups state and the behavior that operates on it into a single unit (an object), so each unit owns and protects its own data. This makes large systems easier to reason about, extend, and maintain because responsibility is localized instead of scattered.

**Q2. What is the "everything is an object" mindset, and is it always the right approach?**
A: It means modeling real-world (or domain) entities as objects that bundle their own state and behavior, rather than treating data and logic as separate things floating around. It is not always the right approach — small scripts, pure data transformations, or math-heavy code often read more clearly in a functional/procedural style. OOP earns its cost when a domain has many interrelated entities with rules that need to be protected and reused.

**Q3. What is the difference between state and behavior in an object?**
A: State is the data an object holds (its attributes/fields) at any given moment — it answers "what does this object know?" Behavior is the set of methods an object exposes — it answers "what can this object do?" Good object design keeps behavior close to the state it operates on, instead of letting external code reach in and manipulate state directly.

**Q4. What is "message passing" in OOP?**
A: It's the idea that objects don't reach into each other's internals — they communicate by calling each other's public methods, i.e., sending a "message" and getting a response. This is the mechanism that keeps encapsulation meaningful: an object's internal state stays private, and all interaction happens through its public interface.

**Q5. What is Responsibility-Driven Design, briefly?**
A: Instead of starting from "what data do I need," you start from "who is responsible for this piece of knowledge or this action?" You assign responsibilities to objects based on what they naturally should own, which tends to produce classes with clear, single purposes rather than classes built around convenient data groupings.

**Q6. Class vs Object — explain the difference the way you would to a beginner.**
A: A class is a blueprint — it defines what fields and methods every object of that type will have, but it doesn't hold any real data itself. An object is a concrete instance created from that blueprint, with its own actual values in memory. You can create many objects from one class, each with independent state.
