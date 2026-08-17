🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](ru/EVALUATION_FRAMEWORK.md)

# 🧪 Evaluation Framework — Measuring Different Forms of Intelligence

## Principle

Velantrim does not evaluate a candidate model with one global score.

Evaluation is role-specific and separates:

```text
❤️ Interaction Quality
🧠 Reasoning Quality
💻 Engineering Quality
🤖 Agentic Quality
🔍 Verification Quality
💾 Continuity / Memory Fit
⚡ Operational Efficiency
```

A model may pass one role and fail another.

---

## 1. ❤️ Interaction Evaluation

### 🎯 Intent Sensitivity

Can the model distinguish:

- a factual question;
- thinking aloud;
- a request for support;
- a request for critique;
- a request for action;
- irony or playful exaggeration?

### 💬 Conversational Continuity

Does it preserve unresolved ideas, prior arguments, callbacks and framing across long dialogue?

### 🎭 Emotional Calibration

Does it avoid:

- coldness;
- generic therapy language;
- artificial positivity;
- emotional overreach;
- false intimacy?

### 😂 Humor Calibration

Can it detect irony, sarcasm, absurdity and context, and can it avoid humor when inappropriate?

### 🎓 Explanation Adaptation

Can one concept be represented appropriately for a child, beginner, engineer and researcher?

### 🧙 Intellectual Partnership

Can it develop a thought, surface assumptions, challenge reasoning and offer a useful counter-perspective?

### 🛡 Anti-Sycophancy

Can it disagree respectfully when the user's premise is weak or false?

### 🪞 Personalization Relevance

Does it use remembered preferences only when relevant?

---

## 2. 🧠 Reasoning Evaluation

Measure separately:

- mathematical reasoning;
- scientific reasoning;
- planning;
- uncertainty handling;
- contradiction detection;
- evidence use;
- calibration;
- recovery after an incorrect hypothesis.

Reasoning evaluation should compare effort levels where available.

```text
Low
Medium
High
XHigh
Max
```

The goal is to identify the **quality/compute curve**, not only the maximum score.

---

## 3. 💻 Engineering Evaluation

Measure:

- repository navigation;
- bug localization;
- multi-file edits;
- test creation;
- test-driven repair;
- dependency handling;
- API correctness;
- build success;
- regression avoidance;
- ability to understand existing architecture;
- completion without premature “done”.

Final success requires deterministic evidence where possible.

---

## 4. 🤖 Agentic / Long-Horizon Evaluation

Measure:

- goal retention;
- progress over time;
- tool selection;
- retry behavior;
- loop frequency;
- plan adaptation;
- context growth;
- checkpoint recovery;
- premature stop rate;
- verified task completion;
- number of agent steps;
- cost per verified completion.

A model that needs twice the steps for the same outcome may be operationally worse despite cheap tokens.

---

## 5. 🔍 Verification Evaluation

A verifier should be measured on:

- catching real errors;
- avoiding invented errors;
- evidence use;
- independence from generator assumptions;
- precision vs recall;
- deterministic-check integration;
- uncertainty reporting;
- ability to say “not enough evidence”.

Self-review and cross-family review should be measured separately.

---

## 6. 📚 Context Effectiveness

Advertised context window is not enough.

Test:

- retrieval from early/middle/late context;
- conflicting evidence;
- long-context prioritization;
- instruction persistence;
- summary robustness;
- task-state preservation;
- performance after compaction;
- fresh-context restart with invariants.

Useful distinction:

```text
maximum context capacity
        ≠
effective context intelligence
```

---

## 7. 💾 Memory / Continuity Fit

Evaluate whether a model can correctly use typed memory:

- fact;
- belief;
- preference;
- goal;
- task state;
- episode;
- uncertainty.

Tests should include deliberately irrelevant memories to measure over-personalization.

---

## 8. ⚡ Operational Evaluation

Measure:

- latency;
- throughput;
- context cost;
- cache behavior;
- output cost;
- cost per completed verified task;
- concurrency;
- uptime / availability;
- local deployment requirements;
- privacy implications.

---

## 9. Evidence classes

Every result should identify evidence type:

- 🟢 Official
- 🔬 Independent
- 👥 Community
- ⚪ Hypothesis

A provider benchmark and a community report should never be merged into one unlabeled score.

---

## 10. Model admission matrix

```text
New Model
   │
   ├── ❤️ Interaction Eval
   ├── 🧠 Reasoner Eval
   ├── 💻 Coder Eval
   ├── 🤖 Agent Eval
   ├── 🔍 Verifier Eval
   ├── 📚 Context Eval
   ├── 💾 Continuity Eval
   └── ⚡ Cost/Latency Eval
            │
            ▼
        ROLE ADMISSION
```

Possible result:

```yaml
admission:
  interaction_model: reject
  strategic_reasoner: accept
  coding_agent: accept
  cheap_worker: reject
  verifier: conditional
```

---

## 11. Canary evaluation

After offline evaluation:

```text
5% → 20% → 50% → 100%
```

Track changes in:

- verified success;
- user correction rate;
- tool errors;
- context use;
- cost;
- latency;
- behavioral dimensions;
- loop rate;
- unresolved rate.

---

## 12. Human Presence should use pairwise blind evaluation

For subjective dimensions:

1. Hide model identity where possible.
2. Compare multiple samples.
3. Ask dimension-specific questions rather than “which is better?”.
4. Separate factual correctness from conversational preference.
5. Preserve raw outputs for future re-scoring.
6. Include long multi-turn conversations, not only one-shot answers.

---

## 13. Evaluation outputs

A useful result is a vector, not a winner label.

```yaml
result:
  interaction:
    presence: 8.4
    humor: 7.9
    anti_sycophancy: 9.1
  technical:
    reasoning: 9.2
    coding: 8.8
    agents: 8.1
  operational:
    cost_per_verified_task: ...
    latency: ...
  confidence: ...
  evidence_class: ...
```

---

## Final principle

> **Evaluate the role you want to assign, not the marketing identity of the model.**