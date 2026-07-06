# State & Memory series — build plan

Thread 3 of the wiki (toward-the-metal). Branches off the CPU page. Grounds the
interview practice problems by showing what actually happens in memory. Pairs
with the codeviz tool. Principle: many small, composable pages.

## Core series (build order)

**A. Substrate**
1. **What is state?** — bits in memory, mutation over time, the (implicit) state machine. Anchor page; branches off the CPU page.
2. **Memory: bytes at addresses** — one big addressable array of cells; reading and writing a cell.
3. **Variables, values, and addresses** — a name bound to a place that holds a value.

**B. Shapes and references**
4. **Arrays (C-style)** — contiguous cells, address = base + i * size, O(1) access.
5. **What a pointer is: indirection** — a value whose content is an address ("the thing is over there"). Aside: a C array's name is a pointer to its first cell.
6. **Copy vs share (value vs reference)** — assign/pass: copy the thing or share a pointer? Two names, one piece of state.
7. **Aliasing bugs** — when changing "this" changes "that". The payoff page for the pointer cluster.
8. **Null and dangling pointers** — a pointer to nothing / to state that's gone. Centers on null; waves at dangling (deep version deferred).

**C. Where state lives and who can touch it**
9. **The stack and frames** — local state, appears/vanishes with each call. Leak-pair: recursion.
10. **Scope and globals** — who can see/change a piece of state; a global is uncontained mutable state.

**D. Capstone**
11. **An array problem, in memory** — walk a practice problem, watch state mutate cell by cell. Pairs with codeviz.

## Sibling (logged now; build right after the core; linked UP from page 1)

- **State machines (the explicit kind)** — a deliberate modeling tool: a finite
  set of named states plus the allowed transitions; make illegal states
  unrepresentable. A design/modeling page, one altitude up from the memory
  series. Links: UP from "What is state?"; SIDEWAYS to regex / formal languages
  (regular languages are finite automata) and to protocols/UI; DOWN to the CPU
  (itself a state machine). On the big map this sat under Mathematical
  Foundations, but it is really a design-and-modeling page.

## Deferred (later "deeper memory" cluster)

The heap and dynamic allocation; pointer arithmetic / indirection as a design
pattern; mutability vs immutability; garbage collection; the memory hierarchy,
caches, and data locality; true use-after-free.

## Status

All 12 pages are published: built, hardened over a multi-round reader-panel run,
hand-tuned, committed, and live at their URLs. They are deliberately NOT yet
linked from the landing page (index.html) / table of contents.

- [x] 1. What is state?  (published, unlisted)
- [x] 2. Memory: bytes at addresses  (published, unlisted)
- [x] 3. Variables, values, and addresses  (published, unlisted)
- [x] 4. Arrays (C-style)  (published, unlisted)
- [x] 5. What a pointer is: indirection  (published, unlisted)
- [x] 6. Copy vs share  (published, unlisted)
- [x] 7. Aliasing bugs  (published, unlisted)
- [x] 8. Null and dangling pointers  (published, unlisted)
- [x] 9. The stack and frames  (published, unlisted)
- [x] 10. Scope and globals  (published, unlisted)
- [x] 11. An array problem, in memory  (published, unlisted)
- [x] (sibling) State machines  (published, unlisted)

Next step when ready: add the 12 to index.html and the learning path.
