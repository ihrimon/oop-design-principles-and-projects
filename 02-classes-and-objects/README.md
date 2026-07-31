# Phase 02 — Classes, Objects & Object Lifecycle

Detailed checklist for how a class becomes a living object: creation, initialization, and eventual cleanup.

## Checklist

- [ ] Class definition syntax (in your primary language)
- [ ] Object instantiation (`new` keyword, factory functions, etc.)
- [ ] Fields, instance variables/attributes, instance methods
- [ ] `this` / `self` keyword — referring to the current instance
- [ ] Multiple objects from the same class — independent state
- [ ] Object comparison — reference equality vs value equality
- [ ] Nested/inner classes and their practical use cases
- [ ] Default constructor vs parameterized constructor
- [ ] Constructor overloading (in languages that support it) & constructor chaining (`super()`)
- [ ] Object creation lifecycle: memory allocation → initialization → usage → destruction
- [ ] Destructor/finalizer concept and its relationship with garbage collection
- [ ] Copy constructor / cloning — shallow copy vs deep copy
- [ ] Solving complex constructor problems with the Builder pattern (preview — full pattern in Phase 08)

## Project

`Student Management System` — model multiple `Student` objects, each with independent state, and a constructor that validates input at creation time.

## Common Pitfall

Confusing "class" (blueprint) with "object" (instance) when explaining code out loud — a frequent interview stumble.
