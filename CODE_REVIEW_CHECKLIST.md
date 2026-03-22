# Ved Code Review Checklist

This checklist guides maintainers and contributors during pull request review.

The goal is to preserve determinism, clarity, and long-term system stability.

Reviewers should use these criteria before approving changes.

---

## 1. Architectural Alignment

- [ ] Does the change align with Ved architectural principles?
- [ ] Does it avoid known architectural anti-patterns?
- [ ] Does it preserve the control-plane focus of the language?
- [ ] Is the change justified by a clear system-level need?

---

## 2. Determinism Guarantees

- [ ] Does the change introduce any hidden nondeterminism?
- [ ] Are all external inputs explicitly modeled?
- [ ] Is execution behaviour reproducible under replay?
- [ ] Are time, randomness, or concurrency handled safely?

---

## 3. State Integrity

- [ ] Are state mutations explicit and traceable?
- [ ] Does the change maintain persistence invariants?
- [ ] Is state schema evolution considered if relevant?
- [ ] Does it avoid uncontrolled state growth?

---

## 4. Execution Model Discipline

- [ ] Does the change respect bounded execution slices?
- [ ] Could it introduce scheduler starvation or unfairness?
- [ ] Are long-running operations structured safely?
- [ ] Is transition logic focused and composable?

---

## 5. Effect Isolation

- [ ] Are side-effects explicitly declared?
- [ ] Are effect results recorded for replay?
- [ ] Does the runtime remain independent of uncontrolled I/O?
- [ ] Are retries or failure handling visible and systematic?

---

## 6. Authority and Isolation

- [ ] Does the change respect scope hierarchy rules?
- [ ] Are privilege escalations explicit and validated?
- [ ] Is cross-domain interaction intentional and controlled?
- [ ] Does it maintain domain isolation guarantees?

---

## 7. Goal Semantics

- [ ] Does the change contribute to goal-driven behaviour?
- [ ] Could it introduce goal conflicts or oscillations?
- [ ] Is convergence reasoning still clear?
- [ ] Are new goals observable and measurable?

---

## 8. Simplicity and Clarity

- [ ] Is the implementation understandable without deep context?
- [ ] Does it avoid unnecessary abstraction?
- [ ] Are naming and structure consistent with existing code?
- [ ] Could the change be simplified further?

---

## 9. Observability

- [ ] Are important state transitions visible?
- [ ] Does the change improve or degrade debuggability?
- [ ] Are logs, traces, or metrics needed?
- [ ] Can failures be diagnosed from runtime output?

---

## 10. Testing and Validation

- [ ] Are relevant tests added or updated?
- [ ] Do tests cover failure and recovery scenarios?
- [ ] Is deterministic replay validated?
- [ ] Are edge cases considered?

---

## 11. Documentation Impact

- [ ] Does the change require documentation updates?
- [ ] Are new concepts explained clearly?
- [ ] Is terminology consistent with existing docs?
- [ ] Are examples updated if behaviour changes?

---

## 12. Performance Considerations

- [ ] Could the change affect scheduler performance?
- [ ] Does it increase persistence overhead?
- [ ] Are memory implications understood?
- [ ] Is the performance impact acceptable for long-lived systems?

---

## 13. Security Considerations

- [ ] Could the change introduce authority bypass?
- [ ] Are external interactions validated?
- [ ] Does it expose sensitive data paths?
- [ ] Is the failure mode safe?

---

## 14. Long-Term Maintainability

- [ ] Will future contributors understand this code?
- [ ] Does it increase coupling between components?
- [ ] Does it preserve modular boundaries?
- [ ] Is technical debt being introduced?

---

## Reviewer Guidance

Not all checklist items apply to every change.

However, reviewers should actively consider:

- determinism
- state safety
- convergence behaviour
- architectural consistency

Approval should be based on system impact rather than code size alone.
