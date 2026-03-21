# Ved v0.1 — Deterministic Control-Plane Programming Language

## Foundational Design Reference

---

# 1. Vision

Ved is a deterministic control-plane programming language designed to build long-lived orchestration systems that converge toward declared goals.

It targets:

* infrastructure automation
* distributed resource coordination
* platform engineering control planes
* self-healing system management

Ved programs describe:

* desired stable conditions
* deterministic transitions
* controlled external side-effects

Runtime guarantees:

* replayable evolution
* persistent state
* deterministic scheduling
* authority-safe orchestration.

---

# 2. Execution Philosophy

Traditional programming:

* sequential execution
* program terminates
* developer manages retries and concurrency

Ved execution:

* persistent system evolution
* runtime drives convergence
* transitions execute in deterministic slices
* effects form boundary with real world

Ved is conceptually:

* closer to control systems than scripts.

---

# 3. Syntax Layering Model

Ved provides three developer surfaces.

## Script Mode

* implicit ephemeral domain
* quick utilities and learning

Example:

emit Log("Hello")

## System Mode

* explicit domain and state
* persistent execution

## Orchestration Mode

* goals
* reconciliation
* authority scopes
* production orchestration systems

All layers compile to same deterministic runtime semantics.

---

# 4. Core Language Constructs

System structure:

* system
* module
* domain
* state
* transition
* goal
* reconcile
* migration

Execution:

* start
* step
* slice
* emit
* send

Authority:

* scope
* elevate
* capability

Composition:

* import
* public
* private

Control:

* if
* else

Target keyword range: ~20.

---

# 5. Scope Hierarchy Model

Default spatial authority lattice:

Tenant
→ Environment
→ Workspace
→ Target
→ Context
→ Namespace

Rules:

* higher scope may orchestrate lower
* lower scope cannot mutate upward
* lateral mutation forbidden without ancestor mediation

Compiler must enforce:

* transition invocation legality
* effect emission scope safety.

---

# 6. Authority Type System

Authority is part of static typing.

Each construct has:

* value type
* authority scope type

Subtyping:

Higher authority ⊇ lower authority

Compiler guarantees:

* no illegal escalation
* capability compatibility
* safe cross-domain coordination.

Explicit elevation construct required for scope jump.

---

# 7. State Model

Domain state is:

* strongly typed
* versioned
* persistently snapshotted
* mutated only inside deterministic transitions

Persistence flow:

* load snapshot
* execute slice
* validate invariants
* commit snapshot

State evolution:

* schema versioning
* deterministic migration transitions
* compaction support
* terminal lifecycle states.

---

# 8. Goal Semantics

Goal represents persistent convergence target.

Components:

* deterministic predicate
* priority
* termination policy

Scheduler ensures:

* reconciliation opportunity
* deterministic ordering

Conflict resolution:

* priority dominance
* authority override
* deterministic arbitration
* optional exclusivity groups.

Oscillation detection required.

---

# 9. Scheduler Model

Scheduler is deterministic evolution engine.

Scheduling unit:

Transition slice.

Ranking function considers:

* goal priority
* authority level
* aging factor
* domain identifier

Features:

* soft real-time fairness
* slice preemption
* stable domain throttling
* logical time progression.

---

# 10. Effect Runtime Architecture

Effect lifecycle pipeline:

Transition → Intent Queue → Executor → Journal → Response Injection → Scheduler

Requirements:

* append-only journal
* idempotency classification
* crash recovery via replay
* authority validation before execution
* backlog backpressure control.

Effect state machine:

EMITTED → PERSISTED → EXECUTING → RECORDED → DELIVERED → CONSUMED

---

# 11. Bytecode VM

Register-based deterministic VM.

Core instruction categories:

* control flow
* state load/store
* arithmetic / logical
* messaging
* effect emission

Fixed register frames.

HALT_SLICE defines scheduling yield point.

No nondeterministic primitives allowed.

---

# 12. Bundle Format (.vedx)

Binary container sections:

* magic header
* version
* metadata
* authority lattice
* domain schemas
* goal definitions
* transition bytecode
* effect capabilities
* checksum

Runtime load must be:

* deterministic
* validated
* fail-fast on incompatibility.

---

# 13. Module & Package System

Structure:

Package → Modules → Domains

Properties:

* static imports
* acyclic dependency graph
* schema compatibility enforcement
* manifest-driven version resolution

One package produces one bundle in v0.1.

---

# 14. Testing & Simulation Model

Testing is deterministic replay simulation.

Test capabilities:

* synthetic effect responses
* temporal convergence assertions
* crash recovery simulation
* oscillation detection
* migration validation

Coverage metrics:

* goal convergence
* authority path
* effect lifecycle.

---

# 15. Fault Model

Fault classes:

* transition fault
* effect fault
* convergence fault
* persistence fault

Domain lifecycle:

ACTIVE → DEGRADED → FAULTED → RECOVERING

Features:

* deterministic retry scheduling
* compensation transitions
* escalation to higher scope
* terminal failure state.

---

# 16. Distributed Runtime Vision

Cluster properties:

* single-owner domain placement
* replicated effect journal
* global logical ordering
* partition safety favoring determinism

Evolution roadmap:

single node → journal replication → domain distribution → scheduler federation.

---

# 17. Security Model

Security principles:

* least authority execution
* capability-based effect permissions
* opaque credential handles
* runtime sandboxing
* audit-logged sensitive operations

Bundle integrity validation required.

Cross-tenant isolation mandatory.

---

# 18. Example Reference System

Mini Auto-Scaler Controller demonstrates:

* persistent state
* goal convergence
* effect retries
* scheduler fairness
* deterministic stabilization.

This should be first implementation target.

---

# 19. Recommended Build Order

1. Bytecode interpreter
2. Snapshot persistence layer
3. Deterministic scheduler
4. Effect intent journal
5. Minimal compiler frontend
6. Goal engine
7. Simulation test runner

Avoid distributed runtime initially.

---

# 20. Strategic Positioning

Ved is:

Deterministic control-plane programming language.

It is not:

* general backend language
* UI framework
* scripting replacement

Primary value:

* reproducible orchestration
* compile-time governance
* safe long-lived system automation.

---

End of Ved v0.1 Reference
