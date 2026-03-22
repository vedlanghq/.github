# Ved Language

Ved is a deterministic control-plane programming language for building reliable,
long-running orchestration systems.

It focuses on describing how complex distributed software environments should
evolve and stabilize over time rather than implementing application business
logic.

---

## Motivation

Modern systems consist of many interacting services, workflows, and autonomous
components. The logic that governs their deployment, coordination, scaling, and
recovery is often implemented through ad-hoc scripts or controller frameworks.

Ved explores a programming model where:

- desired system behaviour is expressed as stable goals
- execution is deterministic and replayable
- persistent state evolution is a first-class concern
- authority and isolation boundaries are enforced statically
- orchestration logic becomes analyzable and reproducible

---

## Core Repositories

- ved-runtime  
  Deterministic execution engine responsible for scheduling, persistence, and
  effect orchestration.

- ved-compiler  
  Language frontend that transforms Ved source programs into executable bundles.

- ved-cli  
  Command-line tooling for compiling, running, and inspecting Ved systems.

---

## Project Status

Ved is in early design and prototyping stages.

Current focus areas include:

- deterministic scheduling model
- persistent state journal and replay
- goal-driven convergence semantics
- authority-aware orchestration structure

Distributed runtime capabilities and advanced tooling are planned for later
phases after core execution behaviour is validated.

---

## Contributing

Design discussions are ongoing.  
Contributors interested in distributed systems, orchestration reliability, and
deterministic execution models are encouraged to participate.

Please open issues to discuss ideas before submitting large changes.

---

## License

Core repositories are released under the Apache License 2.0.
