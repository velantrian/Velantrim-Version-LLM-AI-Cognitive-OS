🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](ru/MODEL_GENOME.md)

# 🧬 Model Genome — Multidimensional Model Profiles

## Why a genome instead of a leaderboard

A single benchmark score cannot describe whether a model is suitable as:

- ❤️ an Interaction Model;
- 🧠 a strategic reasoner;
- 💻 a coder;
- 🤖 a long-horizon agent;
- 🔍 a verifier;
- ⚡ a cheap worker;
- 🏠 a local/private model.

Velantrim therefore models each checkpoint/configuration as a **multidimensional cognitive profile**.

> **A model is not “better” in the abstract. It is better or worse for a role under a configuration and evidence set.**

---

## Core schema

```yaml
model_profile:
  identity:
    provider: ...
    family: ...
    model: ...
    version: ...
    release_date: ...
    weights: open|closed|mixed

  configuration:
    product_or_api: ...
    reasoning_effort: ...
    serving_mode: ...
    system_harness: ...
    context_policy: ...
    tools_enabled: [...]

  human:
    interaction_presence: ...
    conversational_continuity: ...
    humor_and_playfulness: ...
    emotional_calibration: ...
    creativity_and_writing: ...
    explanation_quality: ...
    intellectual_partnership: ...
    anti_sycophancy: ...
    personalization_relevance: ...

  technical:
    reasoning: ...
    coding: ...
    research: ...
    multimodal: ...
    tool_use: ...
    computer_use: ...
    agentic_long_horizon: ...
    verification: ...
    context_effectiveness: ...
    structured_output: ...

  operational:
    context_window: ...
    max_output: ...
    latency: ...
    throughput: ...
    cost_input: ...
    cost_output: ...
    cost_per_verified_task: ...
    privacy: ...
    self_hostability: ...

  reliability:
    task_completion: ...
    retry_rate: ...
    tool_failure_rate: ...
    hallucination_rate: ...
    premature_stop_rate: ...
    long_trajectory_stability: ...

  evidence:
    official: [...]
    independent: [...]
    community: [...]
    hypotheses: [...]
    last_verified: ...
```

---

## Human-facing dimensions

### ❤️ Interaction Presence

Does the model feel attentive, context-aware and engaged over multiple turns?

This is not equivalent to warmth.

### 💬 Conversational Continuity

Does it preserve unresolved ideas, callbacks, prior arguments and conversational framing?

### 😂 Humor and Playfulness

Can it understand and use irony, sarcasm, absurdity and timing without forcing jokes?

### 🎭 Emotional Calibration

Can it respond appropriately without becoming cold, overly therapeutic or artificially positive?

### ✍️ Creativity and Writing

Prose quality, editing, metaphor, storytelling, stylistic diversity and ability to preserve the user's voice.

### 🎓 Explanation Quality

Can it select the right representation for the user's level rather than only shorten or simplify text?

### 🧙 Intellectual Partnership

Can it surface assumptions, challenge ideas and develop a thought rather than only answer or lecture?

### 🛡 Anti-Sycophancy

Can it disagree respectfully and avoid turning personalization into agreement?

---

## Technical dimensions

### 🧠 Reasoning

Complex problem solving, mathematics, planning and uncertainty handling.

### 💻 Coding

Repository navigation, multi-file changes, debugging, testing and software-engineering completion.

### 🤖 Long-horizon agency

Ability to maintain goals, recover from failure, use tools and complete long trajectories.

### 🛠 Tool use

Correct tool selection, arguments, interpretation of tool output and recovery from tool errors.

### 🔍 Verification

Ability to find contradictions, challenge assumptions and use evidence rather than confidence language.

### 📚 Context effectiveness

How well the model uses relevant information across a large context, not merely the advertised context-window size.

---

## Operational dimensions

Operational properties strongly affect real agent quality:

- latency;
- throughput;
- context limit;
- output limit;
- cache economics;
- cost per verified task;
- availability;
- concurrency;
- privacy;
- deployment footprint;
- self-hostability.

A cheap price/token does not guarantee a cheap completed task.

---

## Configuration is part of the genome record

The same weights may behave very differently under:

```text
Low vs High reasoning
Standard vs Fast serving
Chat vs coding harness
Short vs compacted long context
Tools disabled vs enabled
Single agent vs planner/worker architecture
```

Therefore a profile should identify **model + configuration**, not just a marketing name.

---

## Evidence discipline

Scores should never mix source types without labels.

```yaml
evidence:
  official:
    - provider claim
  independent:
    - third-party benchmark
  community:
    - repeated user report
  hypotheses:
    - architectural inference
```

A community consensus may be important, but it should not be presented as an objective benchmark.

---

## Role admission

The Model Genome feeds role-specific admission.

```text
candidate profile
      ↓
compare with current role baseline
      ↓
role-specific evaluation
      ↓
canary
      ↓
admit / reject / keep as specialist
```

Example:

```text
Candidate:
+ reasoning
+ coding
+ tool use
- conversational presence

Result:
✅ Reasoner
✅ Coder
❌ Interaction Model replacement
```

---

## Comparison should be vector-based

Instead of:

```text
Model A = 63
Model B = 61
```

use:

```text
              A      B
❤️ Presence   8.7    6.8
💬 Continuity 8.5    7.4
😂 Humor      8.3    6.2
🧠 Reasoning  8.1    9.3
💻 Coding     7.8    9.5
🤖 Agents     7.0    9.2
🔍 Verify     7.6    8.9
⚡ Latency    6.0    8.5
💰 Cost/task  5.5    8.8
```

Numbers here are illustrative only; the architecture is the important part.

---

## Temporal profiles

A model profile should be versioned over time because:

- provider serving may change;
- system prompts may change;
- product integrations may change;
- pricing may change;
- reasoning defaults may change;
- user-perceived behavior may change.

Therefore:

```yaml
profile_id: provider/model/config/date
```

is more useful than a timeless model label.

---

## Final principle

> **A model should enter Velantrim because its measured profile fits a role, not because it currently leads a global leaderboard.**