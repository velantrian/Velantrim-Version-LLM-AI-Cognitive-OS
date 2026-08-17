🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](ru/ANTI_DEGRADATION.md)

# 🛡️ Anti-Degradation Architecture

## 1. Degradation is multidimensional

Velantrim uses the term **degradation** for several distinct failure modes rather than one vague phenomenon.

```text
                    DEGRADATION
                         │
       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
 🧠 Cognitive       💬 Conversational    🔄 Temporal
 reasoning drift     loss of nuance      context rot
 hallucinations      style flattening    summary drift
 overthinking        sycophancy          memory noise

       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
 🤖 Agent           💾 Memory           🏭 Model/Product
 loops              stale retrieval     behavioral regression
 goal drift         false memory        checkpoint personality shift
 tool misuse        belief/fact mix     provider optimization shift
```

The architecture should detect and contain each class independently.

---

## 2. 🌀 Context rot

Large context windows are useful but do not guarantee effective recall or reasoning.

Long trajectories accumulate:

- stale plans;
- old assumptions;
- tool outputs;
- failed branches;
- summaries of summaries;
- duplicated evidence;
- contradictory instructions;
- irrelevant history.

Therefore:

> **Maximum context ≠ effective context.**

Preferred active context:

```text
Original Objective
+ Current State
+ Relevant Memory
+ Recent Trajectory
+ Required Evidence
```

rather than an unfiltered transcript.

---

## 3. 🎯 Goal drift

An agent can gradually optimize the wrong objective.

Protection mechanism:

```yaml
task_invariants:
  original_goal: ...
  hard_constraints: [...]
  user_non_goals: [...]
  acceptance_criteria: [...]
  safety_boundaries: [...]
```

Working plans may change.

Task invariants should require explicit revision.

---

## 4. 🧠 Overthinking

More reasoning compute is not always better.

Potential failure pattern:

```text
simple task
   ↓
very high reasoning budget
   ↓
unnecessary hypotheses
   ↓
extra tools
   ↓
more context
   ↓
more opportunities for error
```

Dynamic policy:

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

Repeated failure should trigger a **strategy change**, not automatic compute escalation.

---

## 5. ♻️ Agent loops

Signals:

- repeated tool calls with equivalent arguments;
- repeated edits to the same region;
- oscillation between two plans;
- increasing context without measurable progress;
- repeated self-justification;
- retry count rising while verification remains red.

Suggested response:

```text
loop detected
    ↓
STOP current trajectory
    ↓
extract evidence + current state
    ↓
compact / fresh context
    ↓
replan
    ↓
possibly switch model family
```

---

## 6. 🧠 Single-model monoculture

A single model that generates, reviews and explains can preserve the same hidden assumption across all stages.

Preferred pattern:

```text
Generator A
    ↓
Reviewer B
    ↓
Deterministic checks
    ↓
Integrator C
```

Independent errors are more useful than repeated self-reflection from the same model family.

---

## 7. 💾 Memory degradation

Memory failures include:

- stale information;
- retrieval of irrelevant facts;
- summary drift;
- user opinion stored as objective fact;
- duplicate memories;
- provenance loss;
- confidence inflation.

Memory record example:

```yaml
memory:
  type: preference|belief|fact|task_state|episode
  content: ...
  source: ...
  created_at: ...
  confidence: ...
  verified: true|false
  supersedes: ...
```

Critical rule:

> **Memory exists ≠ memory should be used.**

Retrieval needs a relevance policy.

---

## 8. 🤝 Sycophancy

An Interaction Model must not optimize only for approval.

Dangerous objective:

```text
user satisfaction
      ↓
agreement
      ↓
flattery
      ↓
confirmation of bad assumptions
```

Preferred objective:

```text
truth
+ understanding
+ usefulness
+ tact
+ calibrated disagreement
+ intellectual honesty
- sycophancy
- manipulation
```

---

## 9. 🏭 Model-update regression

A newer checkpoint can improve some dimensions and regress others.

Therefore upgrades must be admitted **by role**.

Example:

```text
New model:
+ coding +15%
+ tool reliability +10%
- human presence -20%

Decision:
✅ replace Coder
❌ do not replace Interaction Model
```

---

## 10. 🐤 Canary deployment

New models should not instantly receive 100% of production responsibilities.

```text
5%
 ↓ evaluate
20%
 ↓ evaluate
50%
 ↓ evaluate
100% only if role-specific evidence is green
```

Track:

- completion rate;
- verification failures;
- retries;
- cost/task;
- latency;
- context growth;
- user corrections;
- tool failures;
- behavioral changes.

---

## 11. Automatic degradation detection

Possible telemetry:

```text
retry_count ↑
context_size ↑
verification_failures ↑
user_corrections ↑
repeated_tool_calls ↑
progress_rate ↓
confidence/evidence mismatch ↑
```

Threshold response:

```text
STOP
 ↓
compact state
 ↓
restore task invariants
 ↓
replan
 ↓
switch strategy/model if needed
 ↓
verify independently
```

---

## 12. Summary provenance

A summary must never become unchallengeable truth.

```yaml
summary:
  content: ...
  source_refs: [...]
  created_by: ...
  confidence: 0.0-1.0
  timestamp: ...
```

If there is a conflict, the system must be able to return to primary evidence.

---

## 13. Core anti-degradation laws

1. Preserve the original objective outside model context.
2. Keep critical constraints explicit and immutable by default.
3. Separate memory from transcript.
4. Separate belief from fact.
5. Separate interaction quality from technical quality.
6. Separate generation from verification.
7. Change strategy before blindly increasing compute.
8. Treat model upgrades as role-specific admissions.
9. Detect loops from telemetry, not intuition.
10. Preserve behavioral baselines across generations.

---

## 14. Final principle

> **The system should remain coherent even when an individual model becomes confused, changes behavior, is upgraded, or disappears entirely.**

For the full 57-point architecture and historical motivation, see [📜 Full Canonical Handoff](FULL_HANDOFF.md).