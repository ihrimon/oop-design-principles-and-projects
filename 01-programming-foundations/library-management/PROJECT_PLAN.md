# Project Plan — Library Management

Phase 01 project: identify real-world entities as objects before writing a single class.

## Goal

Take the `Library Management` domain and practice object thinking — recognizing entities, their state, and their behavior — without worrying about classes, inheritance, or patterns yet. This project is a modeling exercise, not a full build.

## Entities to Identify

- [ ] `Book` — state (title, author, ISBN, availability) and behavior (checkout, return)
- [ ] `Member` — state (name, membership ID, borrowed books) and behavior (borrow, return, pay fine)
- [ ] `Librarian` — state (staff ID) and behavior (register member, add book, remove book)
- [ ] `Loan` — the relationship connecting a `Member` to a `Book` (borrow date, due date, return date)

## Steps

1. [ ] List every noun in the problem statement — candidate entities
2. [ ] For each entity, write down its state (data it holds) separately from its behavior (what it can do)
3. [ ] Decide which entities are core domain objects vs supporting/utility concerns
4. [ ] Sketch the relationships between entities (who owns whom, who references whom)
5. [ ] Only after the above, write the first class definitions

## Status

- [ ] Not started
