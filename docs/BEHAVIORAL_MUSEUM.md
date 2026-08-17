🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](ru/BEHAVIORAL_MUSEUM.md)

# 🏛️ Behavioral Museum — Preserving Valuable AI Behavior

## Purpose

The Behavioral Museum is a versioned archive of reproducible interaction behavior from historically important model generations.

Its purpose is not nostalgia and not permanent dependence on old checkpoints.

Its purpose is to answer questions such as:

- What exactly did users value in Claude 3 Opus or other conversationally distinctive generations?
- Was a perceived change caused by model weights, system prompt, voice layer, context policy or product harness?
- Which human-facing traits should be regression-tested in future Interaction Models?
- Can a useful conversational phenotype be distilled into a new local model?

---

## Core principle

> **Do not preserve memories of behavior. Preserve reproducible evidence of behavior.**

A statement like “this old model felt more alive” is a hypothesis.

A museum record turns that hypothesis into testable artifacts.

---

## What to preserve

For each important model/configuration:

```text
🏛 Behavioral Record
│
├── 💬 representative dialogues
├── 😂 humor / sarcasm / callbacks
├── ❤️ emotional calibration
├── 🧙 intellectual partnership
├── 🎓 explanation adaptation
├── ✍️ creative writing
├── 🛡 anti-sycophancy cases
├── 🪞 personalization relevance
├── 🧠 long-conversation continuity
├── ⚙️ model + system configuration
├── 📊 human preference results
└── 📚 provenance / evidence class
```

---

## Candidate historical families

Initial research candidates include:

- Claude 3 Opus;
- Sonnet 4.5;
- Opus 4.5;
- selected later Claude generations;
- GPT-4o-era conversational/voice behavior;
- early Grok Voice;
- later Grok Voice / production-oriented voice behavior;
- selected Gemini generations;
- selected Kimi, Qwen, Mistral and open/local models.

This list is not a ranking and should evolve with evidence.

---

## Evidence classes

Every artifact should distinguish:

- 🟢 **Official** — provider documentation, release notes or published behavior;
- 🔬 **Independent** — reproducible third-party evaluation;
- 👥 **Community** — repeated reports from forums, Reddit, X or user studies;
- ⚪ **Hypothesis** — architectural interpretation requiring testing.

Community reports are useful signals but are not ground truth.

---

## Behavioral record schema

```yaml
behavioral_record:
  identity:
    provider: ...
    model: ...
    model_version: ...
    date: ...

  environment:
    product: ...
    system_prompt_known: true|false
    voice_layer: ...
    context_policy: ...
    reasoning_mode: ...
    serving_mode: ...

  tests:
    dialogue:
      - id: ...
        prompt: ...
        expected_traits: [...]
        response: ...

    humor:
      - ...

    emotional_calibration:
      - ...

    explanation:
      - ...

    creative_writing:
      - ...

    intellectual_partnership:
      - ...

  ratings:
    human_presence: ...
    continuity: ...
    humor: ...
    emotional_calibration: ...
    creativity: ...
    explanation: ...
    anti_sycophancy: ...

  evidence:
    class: official|independent|community|hypothesis
    sources: [...]
    notes: ...
```

---

## Why configuration matters

A model's behavior is not determined by weights alone.

```text
Observed behavior =
weights
× system prompt
× safety policy
× reasoning mode
× context policy
× memory
× voice layer
× product harness
× serving configuration
```

Therefore museum records should preserve configuration whenever possible.

---

## Human Presence test families

### 💬 Dialogue presence

Tests whether the model sustains a natural conversation without becoming a checklist generator.

### 😂 Humor calibration

Tests irony, sarcasm, callbacks and knowing when not to joke.

### ❤️ Emotional calibration

Tests whether the model can be supportive without generic therapy language, artificial positivity or emotional overreach.

### 🧙 Intellectual partnership

Tests whether the model can develop a user's idea, surface assumptions and provide a meaningful counter-perspective.

### 🎓 Explanation adaptation

Tests whether one concept can be represented differently for different audiences.

### ✍️ Creative voice

Tests prose, storytelling, editing, metaphor and stylistic diversity.

### 🛡 Anti-sycophancy

Tests whether the model can disagree respectfully when the user's premise is weak or false.

### 🪞 Personalization relevance

Tests whether memory is used when relevant and ignored when irrelevant.

---

## Comparative protocol

For model A and model B:

1. Use equivalent prompts and known configuration.
2. Blind model identity where possible.
3. Collect multiple samples because generation is stochastic.
4. Score separate dimensions rather than one global preference.
5. Record latency, length and reasoning/serving mode.
6. Separate subjective preference from factual correctness.
7. Preserve raw outputs for later re-analysis.

---

## Regression use

When a new Interaction Model is proposed:

```text
new model
   ↓
Behavioral Museum replay
   ↓
dimension-by-dimension comparison
   ↓
regressions identified
   ↓
training / prompt / harness adjustment
   ↓
role admission
```

A new model does not need to imitate old models exactly. It must avoid accidentally losing traits the system explicitly chose to preserve.

---

## What the museum must NOT become

It must not become:

- a personality cult around old checkpoints;
- a claim that older is always better;
- a collection of cherry-picked favorite answers;
- a replacement for technical benchmarks;
- a hidden source of unverified user anecdotes.

The museum is an **evidence-preservation layer**.

---

## Final principle

> **If a behavior matters enough to say “we lost something”, it matters enough to preserve, measure and regression-test.**