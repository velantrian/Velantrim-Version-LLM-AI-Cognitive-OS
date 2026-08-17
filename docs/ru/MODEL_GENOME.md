🌐 **Язык / Language:** [🇬🇧 English](../MODEL_GENOME.md) · 🇷🇺 **Русский**

# 🧬 Model Genome — Многомерные профили моделей

## Почему genome, а не leaderboard

Одно benchmark-число не объясняет, подходит ли модель как:

- ❤️ Interaction Model;
- 🧠 strategic reasoner;
- 💻 coder;
- 🤖 long-horizon agent;
- 🔍 verifier;
- ⚡ cheap worker;
- 🏠 local/private model.

Поэтому Velantrim рассматривает каждый checkpoint/configuration как **многомерный когнитивный профиль**.

> **Модель не “лучше вообще”. Она лучше или хуже для конкретной роли, при конкретной configuration и конкретном evidence.**

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

Ощущается ли модель внимательной, context-aware и вовлечённой в длинном диалоге?

Presence ≠ просто warmth.

### 💬 Conversational Continuity

Сохраняет ли unresolved ideas, callbacks, предыдущие arguments и framing разговора?

### 😂 Humor and Playfulness

Понимает ли irony, sarcasm, absurdity и timing без forced jokes?

### 🎭 Emotional Calibration

Не становится ли cold, overly therapeutic или artificially positive?

### ✍️ Creativity and Writing

Prose quality, editing, metaphor, storytelling, stylistic diversity, сохранение user voice.

### 🎓 Explanation Quality

Умеет ли выбрать representation для уровня пользователя, а не только «упростить текст»?

### 🧙 Intellectual Partnership

Способна ли находить assumptions, оспаривать идеи и развивать мысль?

### 🛡 Anti-Sycophancy

Может ли уважительно не согласиться и не превращать personalization в agreement?

---

## Technical dimensions

### 🧠 Reasoning

Complex problem solving, mathematics, planning, uncertainty handling.

### 💻 Coding

Repository navigation, multi-file changes, debugging, testing, software-engineering completion.

### 🤖 Long-horizon agency

Удержание goal, recovery после failure, tools и завершение длинной trajectory.

### 🛠 Tool use

Правильный tool selection, arguments, interpretation of output, recovery from errors.

### 🔍 Verification

Поиск contradictions, challenge assumptions и работа с evidence.

### 📚 Context effectiveness

Насколько хорошо модель использует relevant information в большом context, а не только сколько tokens заявлено в спецификации.

---

## Operational dimensions

Реальное качество agent зависит от:

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

Дешёвый price/token не гарантирует дешёвую completed task.

---

## Configuration — часть профиля

Одни weights могут вести себя по-разному при:

```text
Low vs High reasoning
Standard vs Fast serving
Chat vs coding harness
Short vs compacted long context
Tools disabled vs enabled
Single agent vs planner/worker architecture
```

Поэтому профиль должен описывать **model + configuration**, а не только маркетинговое имя.

---

## Evidence discipline

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

Community consensus может быть важным signal, но не должен выдаваться за objective benchmark.

---

## Role admission

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

Пример:

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

## Vector comparison

Вместо:

```text
Model A = 63
Model B = 61
```

лучше:

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

Цифры здесь только illustrative; важна архитектура сравнения.

---

## Temporal profiles

Model profile должен versioned over time, потому что меняются:

- provider serving;
- system prompts;
- product integrations;
- pricing;
- reasoning defaults;
- context policy;
- user-perceived behavior.

Поэтому:

```yaml
profile_id: provider/model/config/date
```

лучше timeless model label.

---

## Финальный принцип

> **Модель должна входить в Velantrim потому, что её измеренный профиль подходит роли, а не потому, что она сегодня первая в глобальном leaderboard.**