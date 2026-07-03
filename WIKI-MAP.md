# The Practical Foundations Wiki — Refined Map

A leveled, cross-linked web of short explainer pages for early-career engineers. This revision integrates the stress-test: it adds the product/impact, AI, operations-reality, and formal-languages material the critics found missing; cuts and merges the theory and gate-level tail; de-duplicates recurring concepts into canonical nodes; and re-levels topics by *when a junior needs them*, not by how hard they are to explain.

---

## How to read this map (two axes, not one)

The critics were right that "up/down" was overloaded. This map separates two independent axes and wires both explicitly.

- **Altitude** (the wiki's vertical spine): UP = more abstract, DOWN = toward the metal. This is a real, continuous stack for the "how computers work" columns (app → runtime → OS → CPU → gates → switches) and for every **leak pair** (see the index near the end). Not every area has altitude; that is fine.
- **Difficulty / when-you-need-it**: `F` foundational (learn early, prerequisite for others), `I` intermediate, `A` advanced (defer until it bites). This is calibrated against a year-one reading path, so a page can be low in the stack yet high in difficulty (gates) or high in the stack yet learned early (runtime).

**Edge types on each page:** `UP:` (more abstract), `DOWN:` (more concrete / drop a level when an abstraction leaks), `SIDEWAYS:` (related peer). Leak pairs are the most important edges in the whole wiki — they are the payoff of the metal-level pages.

**Three connective spines** run through every page as a required facet ("what this hides / where it leaks"):
1. **Encoding** — same meaning, many forms (source ↔ bytecode ↔ machine code ↔ voltages; object ↔ JSON ↔ row).
2. **Abstraction & layering** — complexity is hidden, not removed; hidden things leak.
3. **Interfaces & contracts** — the public promise vs the private how, for both code and data.

**Tags:** `[existing]` a page already drafted, `[planned]` already on the mentor's list, `[new]` surfaced or forced by the stress-test.

---

## The high-leverage core (start here — ~14 pages)

The overwhelm critic's fix: of ~250 topics, these are the vital few a junior should read in roughly this order in the first months. Everything else is "pull it when you hit it."

1. The layer stack: abstraction, interfaces, and where they leak `F` `[existing-adjacent]` — the home node.
2. Metacognition for problem-solving `F` `[existing]`
3. A repeatable method for single-function problems `F` `[existing]`
4. Reading a ticket and finding the real problem `F` `[new-level]` — *promoted to foundational.*
5. The edit-run-observe loop and small verifiable steps `F`
6. Reading code as the main activity + navigating a codebase `F`
7. Reading error messages and a stack trace `F`
8. Reproduce it first + print/log debugging `F`
9. Naming things well + small single-responsibility functions `F`
10. Big-O: how work grows with input `F` (canonical node)
11. Value vs reference semantics (copy vs share) `F`
12. Null / nil / undefined and optionals `F`
13. Why we test + arrange-act-assert + regression tests `F`
14. Git's model (snapshots + the graph) and commit hygiene `F`
15. Using AI assistants critically (verify before you trust) `F` `[new]`

*Note to the reader, stated on the home page: the core is small and learnable in months. The breadth below is a reference library, not a syllabus.*

---

## AREAS

### 1. Thinking, Problem-Solving, and Learning How to Learn
- Metacognition for problem-solving `F` `[existing]` — SIDEWAYS: practical intelligence, explaining out loud.
- Practical intelligence: prediction and steering `F` `[existing]`
- Decomposition: breaking a big problem into small parts `F`
- Abstraction and choosing a representation `F` — SIDEWAYS: data modeling.
- Frames: how experts recognize the kind of situation `I` `[existing]`
- A repeatable method for single-function problems `F` `[existing]`
- Brute force first, then optimize `F`
- Make it work, then right, then fast `I`
- Learning how to learn and deliberate practice `F`
- Experimenting to build intuition: the REPL, scratch file, minimal repro *as a learning tool* `F` `[new]` — SIDEWAYS: reproduce it first.
- Learning a new codebase or technology fast `I`
- Reading error messages and documentation `F`
- Asking good questions; timeboxing solo struggle before you ask `F`
- Explaining out loud to find the answer `F`
- Managing confusion, productive struggle, and imposter feelings `F` `[new]` — the affective-regulation page the overwhelm critic wanted.
- Reading the manual and official docs `F` (canonical; linked from Tooling)

### 2. Product, Users, and Impact  `[new area — the critics' #1 gap]`
The steering wheel for the whole engine. Impact was the stated goal and was one buried bullet; it is now first-class.
- Why the code exists: user, business, and outcome `F` `[new]` — UP from every build task; SIDEWAYS: engineering trade-offs.
- Turning a vague ask into the real requirement `F` `[new]` — merges/anchors "reading a ticket."
- Reading a ticket and finding the real problem `F` `[new-level]` — *promoted from intermediate.*
- Defining "done" as a user outcome, before coding `F` `[new]`
- Deciding what to build and what to cut (scope, prioritization) `I` `[new]`
- Did it work? Success metrics, analytics, and measuring a shipped change `I` `[new]` — SIDEWAYS: observability metrics.
- Experimentation basics: A/B tests and reading a result without fooling yourself `I` `[new]` — SIDEWAYS: probability, dashboards.
- Working with non-engineers: PM, design, stakeholders; pushing back and saying no `I` `[new]`
- Learning the business domain the software serves `I` `[new]`

### 3. Working Alongside AI  `[new area — the 2026 cohort's daily reality]`
Promoted from one buried topic to a hub, per the completeness critic. Maps onto the wiki's own thesis: nothing is magic, the model confabulates, verify before you trust.
- Using AI assistants critically `F` `[new]` — SIDEWAYS: reading code, testing, correctness.
- Giving an assistant the right context `F` `[new]`
- Reviewing and verifying generated code `F` `[new]` — DOWN: reading code; SIDEWAYS: code review.
- Hallucinated APIs and confident wrong answers `F` `[new]`
- When AI makes you faster vs slower; skill atrophy; using AI to learn, not to avoid learning `I` `[new]`
- Security of AI-generated code and prompt injection when your program calls an LLM `I` `[new]` — SIDEWAYS: trust boundaries, injection.
- Agentic coding tools and their failure modes `I` `[new]`

### 4. Reading and Writing Code Humans Can Understand
- Reading code as the main activity `F`
- Navigating a codebase: search, go-to-definition, find-references `F`
- Building a mental model of a codebase `I` — UP: architecture; SIDEWAYS: following control/data flow.
- Following control and data flow `I`
- Reading diffs `F` — SIDEWAYS: code review, git history.
- Tests and docs as specification `I`
- Facing unfamiliar or legacy code without panic `I`
- Naming things well `F`
- Small functions with a single responsibility `F`
- Control-flow shape: guard clauses and early returns `I`
- Comments that explain why, not what `F`
- Code smells and refactoring safely `I` — SIDEWAYS: testability, edit-run-observe.
- DRY vs premature abstraction `I` — SIDEWAYS: rule of three.

### 5. Software Design and Modularity  *(trimmed from 26 → the vital few plus grouped extras)*
The design critic's fix: keep the load-bearing pages, fold the near-synonyms, demote the jargon.
- Why software design exists: managing complexity `F`
- Cognitive load: what makes code complex `F`
- Abstraction: hiding complexity, not removing it `F` — the spine.
- Leaky abstractions `I` — DOWN: whatever leaked; the canonical "drop a level" page.
- Modules, boundaries, and information hiding `F`
- Encapsulation and protecting invariants `F` — SIDEWAYS: preconditions/invariants.
- Interface vs implementation `F` — SIDEWAYS: ADT vs data structure, designing an API.
- Coupling and cohesion `F` (connascence folded in as an `A` aside, not its own node — the buzzword tax the critics flagged).
- Separation of concerns and layering `F`
- Deep vs shallow modules `I`
- Designing an API others will use `I`
- Contracts and errors as part of the interface `I`
- Data modeling: shaping the domain in data `F` — SIDEWAYS: relational modeling, ADTs.
- Making illegal states unrepresentable `I` — DOWN: sum/product types (now named); SIDEWAYS: type guarantees.
- Single source of truth and derived state `I`
- Composition over inheritance, and inheritance traps `I`
- Dependency direction, inversion, and injection `I` `[re-leveled from advanced]` — juniors *consume* DI in frameworks day one.
- Acyclic dependencies `I` — SIDEWAYS: topological sort, build systems.
- Designing for change and evolution `F`
- Testability and seams as a design property `I`
- Design heuristics — KISS and YAGNI `F`; **SOLID `I`** `[split & re-leveled]` (a beginner has no scar tissue for SOLID); rule of three `I`; principle of least astonishment `F`; cargo-culting `I`. *(Merged into one "heuristics" cluster page with sub-sections instead of six peer nodes.)*
- Design patterns as shared vocabulary `I` (communication, not a mandate).

### 6. Formal Languages, Types, and Meaning  `[new area — the CS-purist spine]`
The disconnected pieces (regex, state machines, halting problem) now connect into one through-line: how a flat string of characters becomes a tree with structure and meaning.
- Grammars, tokenizing/lexing, parse trees and ASTs `I` `[new]` — the "unexpected token" page; SIDEWAYS: serialization, compilers.
- The language ladder: regular → context-free → Turing `A` `[new]` — ties regex, state machines, and computability together.
- Regular expressions `F` `[re-leveled from intermediate]` — used week one; includes catastrophic backtracking / ReDoS as a correctness+security hazard. UP: the language ladder.
- Abstract Data Type vs data structure `F` `[new]` — a stack/queue/map is a contract; array/list/hash-table are implementations. Same interface-vs-implementation idea, applied to data.
- Algebraic data types: sum types (tagged unions) and product types (records) `I` `[new]` — DOWN from "make illegal states unrepresentable."
- Types and what they guarantee `F`
- Static vs dynamic typing `F`
- Generics / parametric polymorphism; subtyping, variance (covariance/contravariance) `I` `[new]`
- Equality and identity: structural vs reference, the equals/hashCode contract, mutable keys corrupt a map `I` `[new]` — bites juniors weekly; SIDEWAYS: hash maps, comparators, total vs partial order.
- Null, nil, undefined, and optionals `F` (canonical node; also linked from Correctness).
- Pure functions, referential transparency, and the substitution model `I` `[new]` — names the property behind "side effects."
- Lexical vs dynamic scope; free vs bound variables `I` `[new]` — what makes closures make sense.

### 7. Programming Language Mechanics and Semantics
- Syntax vs semantics: form vs meaning `F`
- Control flow `F`
- Functions, parameters, and return values `F`
- Calling conventions: pass-by-value vs pass-by-reference `I` (canonical node for the copy-vs-share mechanic).
- Expressions, statements, evaluation order, and side effects `F`
- Recursion `I` — **single canonical page** (was 3 pages) covering base case, stacked frames, recursion↔iteration equivalence, and *why deep recursion overflows the stack while a loop does not* (tail calls). DOWN: the stack and call frames; SIDEWAYS: trees, divide and conquer.
- Closures and captured state `I` — DOWN: lexical scope; SIDEWAYS: the loop-capture bug.
- Error handling models: exceptions vs error values `F`
- What a framework is, and inversion of control ("the framework calls you") `F` `[new]` — the environment juniors actually live in; UP: runtime; SIDEWAYS: DI.

### 8. How Computers Work: From Switches to Runtime  *(down-weighted; gates merged)*
The metal critic and pragmatist both said this was fun-to-write and over-weighted. The demystification payoff is kept; the transistor detail is compressed and explicitly marked optional enrichment.
- The layer stack: abstraction, interfaces, and where they leak `F` `[existing-adjacent]` — **the wiki's home/hub node** (moved out of "buried in an area" per the placement critique).
- What a runtime is `F` `[existing]` — the layer juniors live inside.
- How a CPU runs a program: fetch, decode, execute `F` `[existing]`
- Registers and the machine's working set `I`
- Machine code and instruction sets `I`
- Compilation vs interpretation `I` — SIDEWAYS: build steps, where errors surface.
- The clock, cycles, and what a cycle costs `I` — canonical node for "what a nanosecond buys" (was duplicated 3×).
- **Optional deep dive (marked enrichment, not prerequisite):** How a computer is built from switches `A` `[existing]` → gates → adders and latches → assembly as a readable view `A`. *Three ideas compressed from four+ pages; "kills the magic" once, then you move on.*

### 9. Memory and State
- What state is, and why programs have it `F` `[planned]`
- Variables, values, and memory addresses `F`
- Memory as one big addressable array of bytes `F`
- The stack and call frames `I` `[planned]` — DOWN from recursion; SIDEWAYS: scope.
- The heap and dynamic allocation `I`
- Pointers and references `I` — canonical "pointer" definition node; SIDEWAYS: indirection as a general principle `[new aside]` (vtables, handles, symbol tables).
- Value vs reference semantics (copy vs share) `F`
- Arrays and contiguous memory layout `F` `[planned]`
- Scope, lifetime, and globals `F` `[planned]`
- Mutability and immutability `I`
- Memory lifetime, ownership, and leaks `A`
- Manual memory vs garbage collection `A` — **leak pair** with GC pauses; DOWN: allocation cost.
- The memory hierarchy and caches `A`
- Data locality and cache-friendly code `A` — why same Big-O differs 100×.

### 10. Data Representation and Encoding
- Encoding as the central idea: same meaning, many forms `F` — the spine page.
- Bits, bytes, and binary `F`
- Binary, hex, and other bases `F`
- Integer representation and two's complement `I` `[re-leveled from foundational]` — most juniors never touch it directly.
- Integer overflow and fixed-width arithmetic `I`
- Floating point and its surprises `I` — **and a standalone foundational lesson:** Never store money as a float; use integer cents or decimal `F` `[new]`.
- Text encoding: ASCII, Unicode, UTF-8 `F` — a string is bytes plus an encoding.
- Bitwise operations and bit fields `I`
- Endianness and byte order `A` — leak point at boundaries.
- Dates, times, and time zones `I` — SIDEWAYS: cron/DST bugs.
- Serialization formats: JSON, YAML, CSV `F` — DOWN: grammars/parsing; SIDEWAYS: the persistence boundary.
- Encoding vs encryption vs hashing `F` — SIDEWAYS: password storage.
- Line endings, whitespace, invisible characters `I`
- Information floor: entropy, and why you cannot compress random data `A` `[new]` — grounds the encoding thesis; SIDEWAYS: hashing.

### 11. Data Structures
- Choosing a data structure as a trade-off `F` — UP: ADT vs data structure.
- Dynamic arrays and amortized growth `F` — **leak pair** with `list.append`; SIDEWAYS: amortized analysis.
- Linked lists and pointer-based structures `I`
- Hash maps and hashing `F` — split levels honestly: constant-time lookup `F`; the hash contract, collisions, load factor `I`.
- Sets and membership `F`
- Stacks and queues `F` — SIDEWAYS: the call stack, schedulers, BFS/DFS.
- Trees and hierarchical data `I` — SIDEWAYS: DOM, parse trees, recursion.
- Balanced search trees and ordered maps `A`
- Heaps and priority queues `A`
- Graphs and their representations `I`
- Classic structures worth one page each `A` `[new]`: tries, union-find/disjoint sets, and (topological sort, shortest-path, MST as first-class rather than parentheticals).

### 12. Algorithms and Complexity  *(de-emphasized the contest middle)*
Kept because Big-O and structure choice do real work; the hand-rolled DP/Dijkstra pages are marked "interview-shaped, reach for a library in practice."
- What an algorithm is: a precise, finite procedure `F`
- Iteration and loop invariants `I`
- Searching: linear and binary `F` — canonical off-by-one trap.
- Sorting and why sorted data helps `F`
- Divide and conquer `I`
- Graph traversal: BFS and DFS `I`
- Greedy methods and when they fail `A` *(interview-shaped)*
- Dynamic programming and overlapping subproblems `A` *(interview-shaped; demystified as caching)*
- Common problem patterns: two pointers, sliding window, hashing `I` *(interview-shaped)*
- **Big-O: how work grows with input** `F` — **single canonical node** (was 4×). Includes Big-O vs Θ vs Ω `[new]` (the most common misuse).
- Time vs space complexity `I`
- Best, average, worst case `I`
- Amortized analysis `A`
- Constant factors and reality vs asymptotics `A`

### 13. Correctness and Reasoning About Programs
- What "correct" means: specification vs implementation `F`
- Preconditions, postconditions, and invariants `F` — SIDEWAYS: encapsulation, loop invariants.
- Building an accurate mental model (most bugs are the gap) `F`
- Edge cases and boundary thinking `F` — **canonical node** (was 2×; the Testing one links here).
- Off-by-one and boundary errors `F`
- Null and uninitialized values `F` — links to the canonical null page.
- Assertions and defensive checks `F`
- Fail fast `I`
- Partial correctness vs termination `I`
- Defining the valid input domain `I`
- Silent error swallowing `F`
- Resource leaks and cleanup on the error path `I`
- Partial failure and inconsistent state `I`
- Determinism, reproducibility, and flaky behavior `A` — SIDEWAYS: flaky tests, timing bugs.
- Invariants and proof by induction, informally `I` `[re-leveled from advanced]` — same idea that justifies recursion and loops, not a harder separate one.

### 14. Testing
- Why we test: confidence and feedback `F`
- What tests can and cannot prove `F`
- Anatomy of a test: arrange, act, assert `F`
- Unit, integration, end-to-end, and the pyramid `F`
- Running tests locally and fast `F`
- Regression tests `F`
- Edge cases and adversarial thinking `F` → canonical Correctness node.
- Test-driven development as design `I`
- Test doubles: mocks, stubs, fakes `I`
- What to test, and the limits of coverage `I`
- Flaky tests `I` — SIDEWAYS: determinism, timing bugs.
- Property-based testing `A`
- Fuzzing `A`

### 15. Debugging and Diagnosis
- Debugging as hypothesis testing `F`
- Reproduce it first `F`
- Reading a stack trace and error messages `F`
- Print and log debugging `F`
- Using a debugger: breakpoints, stepping, inspecting `I`
- Binary search and bisect (code, data, history) `I`
- The bug is in your assumptions `I`
- Correlation vs causation and "what changed?" `I` — SIDEWAYS: change is the enemy (Operations).
- Writing a good bug report / reproduction for others `F` `[new]` — the communication artifact, not just for yourself.
- Reasoning about what you cannot see (logs, traces, inference) `A`
- The core CLI diagnosis toolkit: curl, dig, ss, lsof, top, strace `I`
- Reproducing production issues locally `A`
- Flaky, timing, and nondeterministic bugs `A`

### 16. Concurrency and Parallelism
- Concurrency vs parallelism `I`
- Why concurrency is hard: no single global "now" `I`
- Blocking vs non-blocking, sync vs async `I` `[re-leveled from foundational]` — it presupposes threads/event loop.
- Processes vs threads vs async `I`
- Shared mutable state as the root problem `I`
- Race conditions and atomicity `I`
- Locks, mutual exclusion, and deadlock `A`
- The event loop and non-blocking I/O `I` — **leak pair** with async/await.
- Message passing vs shared memory `A`
- Happens-before, atomicity, and linearizability (named) `A` `[new]` — the relation that makes reasoning possible.
- Memory models and reordering `A`
- Time-of-check to time-of-use (TOCTOU) `A`
- Backpressure and flow control `I` — **canonical node** (Distributed links here).
- Thundering herd and stampedes `I` — SIDEWAYS: cache stampede, metastable failure.

### 17. Databases and Data Storage
- Why databases exist; files vs databases `F`
- Relational modeling and SQL `F`
- ORMs and the object-relational mismatch `I` `[new]` — the tool that *causes* N+1, now named.
- Indexes: why a query is slow `I`
- The N+1 query problem and query cost `I`
- Transactions and ACID `I`
- Schema design, normalization, denormalization `I`
- Pagination: offset vs cursor `I` `[new]` — one of the most common everyday tasks.
- SQL vs NoSQL trade-offs `I`
- Schema migrations under live data `I` — SIDEWAYS: safe ops against prod data.
- Backfills and one-off scripts over large tables: batching, dry-run, resumability, idempotency `I` `[new]` — more common than migrations, and dangerous.
- Connection pools and data-layer limits `I` — SIDEWAYS: resource-pool exhaustion.
- Replication and failover `I`
- Backups, restore, and disaster recovery `I` `[re-leveled from foundational]` (RPO/RTO).
- Caching and cache invalidation `I` `[re-leveled from advanced]` — **canonical node** (was in 2 areas); the danger is juniors reach for it early.
- The persistence boundary `A`

### 18. Networking and the Web
- Client, server, and request/response `F`
- IP addresses and ports `F`
- DNS: turning names into addresses `F`
- TCP and UDP `F`
- HTTP: methods, status codes, headers, bodies `F` — **leak pair** with TCP.
- Latency vs bandwidth and the cost of a round trip `F`
- The network is unreliable (fallacies of distributed computing) `F` `[re-leveled from intermediate]` — applies to everyone who makes a network call.
- TLS, certificates, and what https guarantees `I` — canonical node (was 2×); SIDEWAYS: cert expiry as a scheduled outage.
- REST APIs: designing and consuming `F`
- Validating input at the boundary `I` — SIDEWAYS: trust boundaries, injection.
- Rate limits and quotas: respect 429/Retry-After, token bucket (consumer and provider) `F` `[new]` — the everyday counterpart to backpressure theory.
- Webhooks and inbound third-party events: signature verification, retries, ordering, dedupe `I` `[new]` — half of real integration work.
- Load balancers and proxies `I`
- Connection lifecycle: timeouts, keep-alive, pooling `I`
- NAT, firewalls, and network boundaries `I` — "works on my machine, not in prod."
- CDNs and the edge `I`
- Modern integration and identity: GraphQL, gRPC, protobuf; OAuth/OIDC/JWT/SSO `I` `[new]` — how real-world auth actually works.
- Cookies, sessions, and tokens `I`
- API versioning and backward compatibility `I` — **canonical node** for versioning/migration/deprecation (was scattered across 4 areas).

### 19. Frontend and User Interface  `[new area — the audience critic's gap]`
Bootcamp/self-taught grads disproportionately land frontend; the old map had ~one page.
- The browser: DOM, rendering, and the event loop `I` — DOWN: event loop; UP: framework.
- Reactivity and client state management `I` `[new]`
- Client vs server rendering (CSR/SSR/hydration) `I` `[new]`
- CSS layout and the box model `F` `[new]`
- Forms, input handling, and validation UX `F` `[new]` — SIDEWAYS: validating input at the boundary.
- Re-render cost and render performance `I` `[new]`
- Accessibility (a11y) as first-class craft `F` `[new]` — professional expectation and increasingly a legal requirement.
- Internationalization and localization `I` `[new]` — SIDEWAYS: Unicode, time zones.

### 20. Operating Systems and Processes
- What an operating system does and why `F` `[planned]`
- The process as an abstraction `I` `[planned]`
- Processes, threads, and scheduling `I`
- System calls: the boundary to the kernel `I`
- Files, file systems, and persistence `F`
- Buffering, flushing, and the cost of I/O `I`
- File descriptors and "everything is a file" `I` — SIDEWAYS: resource-pool exhaustion.
- Permissions, users, and isolation `I`
- Signals and graceful shutdown `F` `[re-leveled from intermediate]` — in-flight draining bites on every deploy.
- Exit codes and process lifecycle `F`
- Resource limits and the OOM killer `I` — SIDEWAYS: disk full, metastable failure.
- Services and daemons `I`
- Cron, scheduled, and batch jobs: overlapping/missed runs, silent stop, DST bugs `I` `[new]` — a large source of quiet failures.
- Virtual memory and address translation `A`

### 21. Version Control and Collaboration
- What version control is for `F`
- Git's model: commits as snapshots and the history graph `F`
- Working tree, staging area, repository `F`
- Branches and merging `F`
- Remotes: push, pull, fetch `F`
- Merge vs rebase `I`
- Resolving conflicts without fear `I`
- Undoing things: reset, revert, restore, reflog `I`
- History as evidence: log, blame, bisect `I`
- Commit hygiene and good messages `F`
- .gitignore and what not to commit (above all, secrets) `F`
- Branching models: trunk-based and feature branches `I`
- Pull requests and code review: giving and receiving `F`
- Receiving review without ego `F`
- Issue tracking and shared context `I`
- Pairing and thinking out loud `I`

### 22. Developer Environment and Tooling
- The command line and the shell `F`
- The filesystem, paths, and the working directory `F`
- Files, permissions, and ownership `F`
- Standard streams, pipes, and redirection `F`
- Environment variables and PATH `F`
- Globbing, quoting, and shell expansion `I`
- Text tools: grep, find, sort, cut, wc `I`
- Shell scripting and safe, idempotent re-runs `I`
- Bootstrapping a project: blank folder → running program → first commit `F` `[new]` — the glue juniors fail at constantly.
- Reproducible local dev: standing the whole app up with seed data on a fresh machine `F` `[new]` — the inverse of "works on my machine."
- Package managers and dependencies `F`
- Versions, lockfiles, and reproducibility `I`
- Semantic versioning and dependency conflicts `I`
- Virtual environments and isolation `I`
- Containers, the practical view `I`
- Compilers, interpreters, and build steps `I`
- Build systems, task runners, and watch mode `I`
- Linters, formatters, and static analysis `F`
- Type checkers `I`
- Pre-commit checks `I`
- The editor or IDE as an instrument `F`
- SSH and working on remote machines `I`

### 23. Security
Trimmed to the app-developer core; memory-safety/UB/crypto internals kept but marked "matters less for managed-language app code."
- Trust boundaries and never trusting input `F` — canonical boundary node (Correctness/Networking link here, not restate).
- Think like an attacker `F`
- Confidentiality, integrity, availability `F`
- Authentication vs authorization `F`
- Broken access control `F`
- Injection: SQL, command, and relatives `F`
- Secrets and credential handling `F`
- Hashing vs encryption vs signing; storing passwords (salt + slow hash) `F`
- Do not roll your own crypto `F`
- Least privilege `F`
- Threat modeling and attack surface `I`
- Defense in depth and secure by default `I`
- Cross-site scripting (XSS) `I`
- Cross-site request forgery (CSRF) `I`
- Validation vs sanitization and canonicalization `I`
- What TLS guarantees, and secure randomness `I`
- Dependencies and the software supply chain `I`
- OWASP Top 10 as a shared checklist `I` `[re-leveled from foundational]` — a reference you consult once you have the concepts.
- Audit logs `I`
- Memory safety: buffer overflow and use-after-free `A` *(matters less for managed-language app code)*
- Undefined behavior `A`

### 24. Handling Data Responsibly: Privacy, Ethics, Licensing  `[new area]`
The prompt named ethics/impact explicitly and it was nearly absent.
- PII and what not to log (don't log passwords, tokens, personal data) `F` `[new]` — a real year-one landmine.
- Privacy, data retention, and the compliance frame (GDPR/PCI/HIPAA, lightly) `I` `[new]`
- Consequences of what you ship: dark patterns, algorithmic bias, responsible data use `I` `[new]`
- Open-source licensing: MIT vs GPL/copyleft, obligations of dependencies, contributing to OSS `I` `[new]` — juniors add packages and copy code daily with no model of what's allowed.

### 25. System-Scale Architecture  *(kept, marked "later — post-junior")*
- The layer stack and layered/MVC/ports-and-adapters/event-driven styles `A`
- Monolith vs services `A`
- Where to draw system boundaries `A`
- Cross-cutting concerns (logging, auth, error handling) `I`
- Separating configuration from code `I` — **canonical config-vs-code node** (was 2×).
- Synchronous vs asynchronous coupling `A`
- Versioning, compatibility, migration, deprecation `A` → links the canonical API-versioning node.

### 26. Distributed Systems and Reliability  *(junior-core split from the theory tail)*
Re-leveled per the SRE critic: the four everyday landmines are now foundational; consensus/CAP/clocks stay advanced.
- **Junior core:**
  - Failure is the normal case `F`
  - The network is unreliable → links the Networking canonical node.
  - Timeouts, retries, backoff, and jitter `F` `[re-leveled]` — a no-timeout HTTP client is a day-one landmine; naive retries turn a blip into a storm.
  - Idempotency `F` `[re-leveled]` — at-least-once means the double-run WILL happen (webhooks, payments, retries).
  - Partial failure `I`
- **Later (advanced destinations):**
  - Cascading failure and blast radius `I`
  - Circuit breakers, bulkheads, and backpressure `A`
  - Graceful degradation; fail-safe vs fail-open `I`
  - Single points of failure and redundancy `F`
  - Consistency vs availability (CAP intuition) `I`
  - Clocks, ordering, and "when did it happen" `A`
  - Message queues and asynchronous work `I`
  - Delivery guarantees: at-least-once / at-most-once / exactly-once `A`
  - Consensus in plain terms `A`
  - Back-of-the-envelope estimation `I` → links the canonical estimation node.

### 27. Performance and Efficiency
- Measure, do not guess: profiling basics `F`
- When to optimize, and when not to `F`
- Where time goes: CPU, memory, disk, network `I`
- Latency, throughput, and tail latency (p99) `F`
- Latency numbers every engineer should know `I` — **canonical node** (was 3×), links to "what a cycle costs."
- Algorithmic cost vs constant factors `I`
- Common performance mistakes: work in a loop, N+1, missing index, chatty calls `I`
- Queueing and saturation intuition `A`
- Load testing and capacity planning `I`
- Allocation cost and GC pauses `I` — leak pair with GC.
- Cost and the economics of running software (FinOps): compute, storage, egress are dollars `I` `[new]` — a bad query or unbounded loop is a bill; seniors reason in money.

### 28. Shipping Changes Safely
- Environments: dev, staging, production `F`
- The path from code to production (CI/CD) `I`
- Build, CI, and artifacts `F`
- Config vs code and secrets in operation `I` → canonical config-vs-code node.
- Stateless vs stateful `F`
- Deploys, rollbacks, and blast radius `I` — SIDEWAYS: rollback as default recovery.
- Progressive delivery: canary, blue-green, rolling `I`
- Feature flags and incremental release `I`
- Cold starts and warm-up (empty caches, cold JIT, unwarmed pools, health-check-passes-before-ready) `I` `[new]` — deploys and autoscaling trip this constantly.
- Versioning and compatibility during a deploy `I`
- The operational substrate: VMs, containers, serverless `I` `[re-leveled from foundational]`
- Orchestration (Kubernetes intuition) `I`
- Infrastructure as code `I`
- Immutable infrastructure `A`
- The cloud model and shared responsibility `I` `[re-leveled from foundational]`

### 29. Running Systems: Observability and On-Call
- You cannot debug what you cannot see `F`
- Logs and structured logging `F`
- Metrics, time series, dashboards (RED/USE) `I` — SIDEWAYS: measuring a shipped change.
- Traces and request flow `I`
- SLIs, SLOs, and error budgets `I`
- Alerting on symptoms, not causes `I`
- Health checks and readiness `F` — SIDEWAYS: cold-start (a check passing before routes serve sends users to a dead instance).
- On-call: triage, severity, mitigate first `F`
- Rollback as the default recovery `F`
- Runbooks `F`
- Escalation and asking for help `F`
- Communication during an incident `I`
- Blameless postmortems `I`
- Toil and automation `I`
- Cardinality and the cost of telemetry `A`

### 30. How Production Actually Breaks  `[new area — the SRE critic's biggest gap]`
The connective spine that assembles the failure mechanisms into the operational truth. Change is the enemy; failures cluster around a boring short list; the dangerous ones don't self-recover.
- Change is the enemy: most outages are self-inflicted by a recent deploy, config push, cert rotation, cron, or migration `F` `[new]` — makes "what changed?" the first question and rollback the default fix.
- The boring high-frequency causes: disk full & log rotation, OOM, resource-pool exhaustion, cache stampede, cert expiry, retry storm `F` `[new]`.
- Resource-pool exhaustion as one idea: threads, DB connections, file descriptors, ephemeral ports, memory `I` `[new]` — symptom is generic slowness or hangs.
- Metastable failure and retry amplification: why a system stays down after the trigger is gone `A` `[new]` — recovery needs load shedding, not more capacity.
- Rate limiting and load shedding you impose on purpose (serve 503 to survive) `I` `[new]`.
- Safe operations against production data: backfills, one-off scripts, locking a hot table, the DELETE without a WHERE `I` `[new]` — **data is forever, code is temporary**; a bad mutation usually doesn't roll back.
- Dependency and vendor outages: your provider's outage is your outage; degrade around it `I` `[new]`.
- Chaos engineering, game days, and failover drills: you don't know redundancy works until you break it `A` `[new]` — the practice behind "a backup you never restored is a hope."

### 31. Mathematical Foundations  *(theory tail cut, per every critic)*
- Boolean logic and truth tables `F` `[planned]`
- Growth rates and logarithms `F` `[planned]` → links Big-O.
- Estimation and orders of magnitude `F` `[planned]` — **canonical estimation node** (Distributed links here).
- State machines `I` `[planned]` — SIDEWAYS: the language ladder, protocols, UI.
- Sets, functions, and relations `I`
- Counting and combinatorics `I`
- Modular arithmetic and remainders `I`
- Probability and randomness, practically `I` — SIDEWAYS: A/B tests, retries, hashing.
- **The limits of computation (one page, was five):** determinism, code as data, Turing equivalence, the halting problem, and P vs NP — "here be dragons," `A` `[new-merged]`. Humility about limits, near-zero daily leverage, links to the language ladder.

### 32. Engineering Judgment, Trade-offs, and Professional Craft
- Engineering trade-offs as a discipline `F` `[planned]`
- Complexity has a cost; hiding is not removing `F` — the spine.
- The edit-run-observe loop and small verifiable steps `F`
- Reversible vs irreversible decisions `I`
- Good enough vs the cost of gold-plating `F`
- Over-engineering vs under-engineering (YAGNI folded in here) `I`
- Technical debt as a deliberate loan `I`
- Build vs buy vs reuse `I`
- Estimating and scoping work `I`
- Breaking work into shippable pieces `I`
- Writing that engineers respect `F`
- The design doc: thinking before building `I`
- Communicating status and managing up `F`
- Giving and taking feedback `F`
- Saying "I don't know" and calibrated confidence `F`
- Ownership and follow-through `F`
- Knowing when to drop a level (the payoff of the metal pages) `I` — SIDEWAYS: leaky abstractions.
- How professionals recognize each other `I` `[existing-adjacent]`
- Growing from junior to senior `I`
- Lifting others: mentoring, unblocking, spreading context `I` `[new]`

### 33. Working on a Team, Sustainably  `[new area]`
The human/organizational layer the completeness critic found thin.
- First 90 days: onboarding, finding the norms, learning who owns what, how much struggle before you ask `F` `[new]`.
- How software teams actually run: agile/scrum/kanban realistically, planning, estimation as a social act `I` `[new]`.
- Self-management over a multi-day task: timeboxing, avoiding rabbit holes, keeping work visible, progress while blocked, context switching `F` `[new]`.
- Working across roles: design, QA, PM, data `I` `[new]`.
- Navigating ambiguity and a large org `I` `[new]`.
- Sustainability and burnout; time and attention management `I` `[new]`.

---

## Leak-pair index (the wiki's most important up/down edges)

These are the "drop a level when the abstraction leaks" edges. Each is a bidirectional UP/DOWN link and is the concrete payoff of the metal-level pages.

- `list.append` ↔ dynamic arrays and amortized growth
- async/await ↔ the event loop and non-blocking I/O
- HTTP ↔ TCP/UDP
- ORM / N+1 ↔ SQL and query cost
- garbage collection ↔ manual memory / allocation cost / GC pauses
- serialization (JSON/YAML) ↔ grammars, tokenizing, parse trees
- "make illegal states unrepresentable" ↔ sum/product types
- closures ↔ lexical scope / free vs bound variables
- recursion ↔ the stack and call frames
- a framework ("it calls you") ↔ the runtime
- health check passes ↔ cold start / readiness
- same Big-O, different speed ↔ data locality and the cache hierarchy
- https padlock ↔ what TLS actually guarantees

---

## What the stress-test changed

**Biggest additions (new first-class areas the critics forced):**
- **Product, Users, and Impact** — the near-unanimous #1 gap. The old map built a superb engine with no steering wheel; "impact" was the stated goal yet was one buried bullet. Now an area covering turning a vague ask into the real problem, defining done as a user outcome, and measuring whether the change worked.
- **Working Alongside AI** — promoted from one buried topic to a hub, matching the 2026 cohort's daily reality and the wiki's own "verify before you trust" thesis.
- **How Production Actually Breaks** — the SRE's missing spine: change is the enemy, a short list of boring causes (disk full, OOM, pool exhaustion, cache stampede, cert expiry, retry storm), metastable failure that won't self-recover, and "data is forever, code is temporary."
- **Formal Languages, Types, and Meaning** — the CS-purist's missing spine: grammars/tokenizing/parse trees plus the regular→context-free→Turing ladder, and the named type concepts (ADT vs data structure, sum/product types, generics/variance, equality/identity).
- **Frontend and UI** (a11y, CSS/box model, forms, reactivity, CSR/SSR), **Handling Data Responsibly** (PII, privacy/compliance, ethics, licensing), and **Working on a Team, Sustainably** (first 90 days, self-management, how teams run).

**Smaller high-value additions:** framework & inversion of control; pagination; webhooks; rate limits/429; ORM named; OAuth/OIDC/JWT; FinOps/cost; "never store money as a float"; safe backfills; cold starts; cron jobs; bootstrapping a project and reproducible local dev; entropy/compression floor; happens-before; Big-O vs Θ vs Ω; a good bug report as an artifact; managing confusion/imposter feelings.

**Biggest cuts and merges:**
- The **computability quartet** (Turing equivalence, halting problem, P/NP, computational models) collapsed into one "limits of computation" page. Clear interview-trivia; near-zero daily leverage.
- The **gate-level chain** (switches → gates → adders/latches → assembly) compressed and explicitly marked optional enrichment, not prerequisite. It demystifies once; it was over-weighted.
- **Software Design** trimmed from 26 nodes; near-synonyms folded (connascence demoted to an aside, SOLID/KISS/YAGNI/rule-of-three/least-astonishment grouped into one heuristics page).
- **De-duplication into canonical nodes:** recursion (was 3×), Big-O (4×), estimation (2×), caching (2 areas), latency numbers (3×), edge cases (2×), config-vs-code (2×), TLS (2×), null and pass-by-value (2× each), and API-versioning/migration (scattered across 4 areas). The duplicates became sideways links, which is what a wiki needs.

**Level fixes (by when-you-need-it, not by how-hard-to-explain):**
- Promoted to foundational: reading a ticket / finding the real problem; idempotency; timeouts-retries-backoff; the network is unreliable; signals & graceful shutdown; regex; change-is-the-enemy.
- Demoted / re-scoped: SOLID → intermediate; dependency injection → intermediate (juniors consume it); caching → intermediate; two's complement → intermediate; OWASP Top 10, backups/DR, the cloud model, VMs/containers/serverless → intermediate (simple to explain ≠ needed early); induction → intermediate (same idea as recursion, not harder).

**Structural fix (the wiki-coherence critique):** two explicit axes now — altitude (declared UP/DOWN edges plus the leak-pair index) and difficulty (a year-one path tag) — instead of one overloaded "level." The layer-stack home node is pulled out of an area to serve as the enter-anywhere hub, the three spines (encoding, layering, interfaces) are named as connective tissue with a required "what this hides / where it leaks" facet per page, and a small explicit **high-leverage core** answers the overwhelm concern up front.