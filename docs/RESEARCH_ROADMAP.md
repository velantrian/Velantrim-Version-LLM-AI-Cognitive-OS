🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](ru/RESEARCH_ROADMAP.md)

# 🗺️ Research Roadmap

## Phase 0 — Preserve the concept

- [x] Establish repository
- [x] Define core architecture
- [x] Define Interaction Model concept
- [x] Define anti-degradation principles
- [x] Define model-evolution research framing
- [x] Define cognitive routing concept
- [x] Add bilingual documentation navigation
- [x] Preserve the full canonical handoff

---

## Phase 1 — Evaluation before implementation

### ❤️ Interaction benchmark suite

Design tests for:

- intent recognition;
- conversational continuity;
- humor;
- emotional calibration;
- explanation adaptation;
- intellectual partnership;
- anti-sycophancy;
- delegation quality.

### ⚙️ Capability benchmark suite

Track:

- reasoning;
- coding;
- long-horizon autonomy;
- tool use;
- verification quality;
- effective context use;
- cost/task;
- latency.

### 🏛️ Behavioral Museum

Create reproducible behavioral records for historically important model generations.

Candidate families:

- Claude 3 Opus;
- Sonnet 4.5;
- Opus 4.5;
- GPT-4o era;
- early/later Grok Voice;
- selected Gemini generations;
- selected open models.

---

## Phase 2 — Model Genome

Create a machine-readable schema for multidimensional model profiles.

```yaml
model_profile:
  identity:
    provider: ...
    model: ...
    date: ...

  human:
    presence: ...
    continuity: ...
    humor: ...
    emotional_calibration: ...
    creativity: ...
    explanation: ...

  technical:
    reasoning: ...
    coding: ...
    agents: ...
    tools: ...
    verification: ...

  operational:
    latency: ...
    cost: ...
    context: ...
    privacy: ...

  evidence:
    official: ...
    independent: ...
    community: ...
```

---

## Phase 3 — Router prototype

Build a simple router that can choose among:

- local Interaction Model;
- cheap worker model;
- strong reasoner;
- coding model;
- research model;
- verifier.

Start with explicit rules before learned routing.

Example:

```text
simple conversation → Interaction only
coding task → Coder + tests
research → Researcher + evidence verifier
critical architecture → Reasoner + independent reviewer
```

---

## Phase 4 — Structured memory

Implement typed memory:

- user preferences;
- user beliefs;
- verified facts;
- task state;
- episodic events;
- source provenance.

Introduce Hot / Warm / Cold layers.

---

## Phase 5 — Anti-degradation telemetry

Detect:

- context growth;
- repeated tool calls;
- failed verification loops;
- retry inflation;
- goal drift;
- user correction rate;
- summary divergence.

Implement automatic stop/replan/switch behavior.

---

## Phase 6 — Local-first Interaction Model experiment

Evaluate whether a local model can provide:

- stable conversational identity;
- low latency;
- user memory;
- intent routing;
- high-quality explanation;

while delegating hard technical work to cloud frontier models.

---

## Phase 7 — Joint training / distillation

Research training pairs for:

- Human → Technical task specification;
- Technical → Human semantic interpretation;
- delegation decisions;
- calibrated disagreement;
- anti-sycophancy;
- explanation adaptation.

Potential objective:

```text
final_user_outcome
+ technical_correctness
+ interaction_quality
+ verification_success
- cost
- latency
- unnecessary_delegation
```

---

## Phase 8 — Production-grade Cognitive OS

Long-term target:

```text
👤 User
  ↓
❤️ Interaction Intelligence
  ↓
🧭 Cognitive Scheduler
  ↓
🧠 Capability Mesh
  ↓
🔍 Assurance
  ↓
💾 Persistent Memory
  ↓
❤️ Human Interpretation
```

The system should survive model replacement without losing identity, task continuity or memory semantics.

---

## Open research questions

1. What is the minimum viable Interaction Model size?
2. Which conversational qualities are model-internal vs. harness-dependent?
3. How can Human Presence be measured reproducibly?
4. How much original context should be passed through a semantic handoff?
5. When is cross-vendor review actually independent enough?
6. How should uncertainty propagate across model handoffs?
7. Can a local Interaction Model safely sanitize tasks for cloud delegation?
8. How should long-horizon agent state be compacted without losing invariants?
9. How do we detect when a model is becoming overconfident rather than more correct?
10. Which historical model behaviors should be preserved through distillation?

---

## Research philosophy

This repository should prefer:

- measured behavior over mythology;
- role-specific evaluation over single leaderboards;
- evidence over confidence;
- explicit uncertainty over fabricated certainty;
- modular replacement over vendor lock-in;
- preserved human interaction quality alongside technical progress.

The Russian roadmap contains the expanded phase structure; the canonical architecture is preserved in [📜 FULL_HANDOFF.md](FULL_HANDOFF.md).