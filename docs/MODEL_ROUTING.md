# 🧭 Cognitive Routing

## Goal

Cognitive routing decides **who should think, how deeply, with which tools, under what budget and with what verification**.

A router should not only pick a provider. It should configure the full cognitive execution path.

---

## Routing dimensions

```text
TASK
 │
 ├─ model role
 ├─ model family
 ├─ reasoning effort
 ├─ serving mode
 ├─ context strategy
 ├─ agent strategy
 ├─ tool set
 ├─ verifier
 ├─ privacy boundary
 ├─ latency target
 └─ cost budget
```

---

## Role taxonomy

```text
L0 — local reflex / trivial task
L1 — cheap worker
L2 — capable specialist
L3 — frontier reasoner
L4 — extreme orchestrator
```

A frontier model should not be consumed for every simple task.

---

## Example routing decision

```yaml
route:
  task_type: software_architecture
  complexity: high
  privacy: medium
  latency: normal
  budget: medium

  primary_role: strategic_reasoner
  reasoning_effort: high
  strategy: plan_execute

  tools:
    - repository_search
    - docs_search

  verification:
    - second_model_review
    - deterministic_tests
```

---

## Dynamic effort

Reasoning effort should be adaptive.

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

The router should learn from failure.

```text
High fails twice
    ↓
choose among:
- fresh context
- new model family
- different reasoning strategy
- stronger verifier
- better decomposition
```

Do not assume more reasoning tokens always solve the problem.

---

## Strategy routing

Possible strategies:

- Direct
- Chain-of-thought style internal reasoning
- ReAct
- Plan → Execute
- Reflection
- Debate
- Tree/graph search
- Multi-agent decomposition

No single strategy is optimal for every task.

---

## Cost-aware routing

The router should optimize **cost per completed verified task**, not cost per token.

A cheap model that needs 100 agent steps may cost more than a stronger model that succeeds in 20.

Useful metric:

```text
effective_cost =
  inference_cost
+ tool_cost
+ retry_cost
+ verifier_cost
+ failure_cost
```

---

## Independence-aware routing

For critical tasks, route verification to a sufficiently independent model family or deterministic process.

Example:

```text
Generator: family A
Reviewer: family B
Verifier: compiler/tests
Integrator: family C or deterministic rule
```

---

## Privacy-aware routing

```text
private / trivial
   → local model

private / complex
   → sanitized delegation

non-sensitive / complex
   → frontier cloud model
```

The router should minimize unnecessary disclosure.

---

## Latency-aware routing

Interactive tasks may prioritize:

- fast serving;
- smaller models;
- shallow effort;
- streaming.

Background tasks may prioritize:

- higher effort;
- multiple reviewers;
- long trajectories;
- slower but stronger models.

---

## Failure escalation policy

```text
attempt 1
  ↓
verify
  ↓ fail
attempt 2 with changed strategy
  ↓
verify
  ↓ fail
fresh context + different model family
  ↓
verify
  ↓ fail
human escalation / unresolved state
```

The system should prefer an explicit unresolved result over an infinite autonomous loop.

---

## Future router learning

A learned router could optimize against outcomes:

```text
reward =
  task_success
+ verification_success
+ user_fit
- cost
- latency
- unnecessary_delegation
- privacy_exposure
```

The long-term objective is **cognitive scheduling**, not static model selection.