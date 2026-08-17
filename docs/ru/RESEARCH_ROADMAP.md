🌐 **Язык / Language:** [🇬🇧 English](../RESEARCH_ROADMAP.md) · 🇷🇺 **Русский**

# 🗺️ Research Roadmap

## Phase 0 — Сохранить концепцию

- [x] Создать repository
- [x] Зафиксировать core architecture
- [x] Определить Interaction Model
- [x] Зафиксировать anti-degradation principles
- [x] Описать эволюцию моделей
- [x] Определить cognitive routing
- [x] Добавить bilingual documentation architecture
- [x] Зафиксировать полный canonical handoff

---

## Phase 1 — Evaluation до implementation

### ❤️ Interaction benchmark suite

Разработать tests для:

- intent recognition;
- conversational continuity;
- humor;
- emotional calibration;
- explanation adaptation;
- intellectual partnership;
- anti-sycophancy;
- delegation quality;
- memory relevance;
- over-personalization;
- long-dialogue presence;
- creativity/writing character.

### ⚙️ Capability benchmark suite

Отслеживать:

- reasoning;
- coding;
- long-horizon autonomy;
- tool use;
- verification quality;
- effective context use;
- cost/task;
- latency;
- agent-step efficiency;
- failure recovery.

### 🏛️ Behavioral Museum

Создать воспроизводимые behavioral records для исторически важных поколений.

Кандидаты:

- Claude 3 Opus;
- Sonnet 4.5;
- Opus 4.5;
- GPT-4o era;
- early/later Grok Voice;
- selected Gemini generations;
- selected DeepSeek/Kimi/Qwen/Mistral generations;
- selected open local models.

---

## Phase 2 — 🧬 Model Genome

Создать machine-readable schema многомерных профилей моделей.

```yaml
model_profile:
  identity:
    provider: ...
    model: ...
    release_date: ...
    configuration: ...

  human:
    presence: ...
    continuity: ...
    humor: ...
    emotional_calibration: ...
    creativity: ...
    explanation: ...
    anti_sycophancy: ...

  technical:
    reasoning: ...
    coding: ...
    agents: ...
    tools: ...
    verification: ...
    context_effectiveness: ...

  operational:
    latency: ...
    cost: ...
    context: ...
    privacy: ...

  evidence:
    official: ...
    independent: ...
    community: ...
    hypothesis: ...
```

---

## Phase 3 — 🧭 Router prototype

Сначала explicit rules, затем learned routing.

Router должен уметь выбирать:

- local Interaction Model;
- cheap worker;
- strong reasoner;
- coding model;
- research model;
- multimodal model;
- verifier;
- reasoning effort;
- context policy;
- agent topology.

Пример:

```text
simple conversation
→ Interaction only

coding task
→ Coder + tests

research
→ Researcher + evidence verifier

critical architecture
→ Reasoner + independent reviewer

private complex task
→ local preprocessing + sanitized frontier delegation
```

---

## Phase 4 — 💾 Structured Memory

Реализовать typed memory:

- user preferences;
- user beliefs;
- verified facts;
- task state;
- episodic events;
- source provenance;
- confidence;
- supersession.

Ввести Hot / Warm / Cold layers.

### Hot

Active working state.

### Warm

Summaries, decisions, relevant documents, open questions.

### Cold

Full archive, logs, source history, forensic reconstruction.

---

## Phase 5 — 🛡 Anti-Degradation Telemetry

Детектировать:

- context growth;
- repeated tool calls;
- failed verification loops;
- retry inflation;
- goal drift;
- user correction rate;
- summary divergence;
- confidence/evidence mismatch;
- stagnant progress;
- oscillating plans.

Реализовать:

```text
STOP
→ state extraction
→ invariant restore
→ context compaction
→ replan
→ switch model/strategy
→ independent verify
```

---

## Phase 6 — ❤️ Local-first Interaction Model experiment

Проверить, может ли local model обеспечивать:

- stable conversational identity;
- low latency;
- user memory;
- intent routing;
- high-quality explanation;
- humor and emotional calibration;
- semantic handoff;

при делегировании тяжёлой technical work frontier cloud models.

---

## Phase 7 — 🔐 Privacy-preserving delegation

Исследовать:

- local extraction of sensitive fields;
- sanitization;
- structured redaction;
- minimum necessary context;
- encrypted/local memory;
- cloud backend isolation;
- audit of what leaves device.

---

## Phase 8 — 🧬 Joint training / distillation

Training pairs:

- Human → Technical specification;
- Technical → Human interpretation;
- delegation decisions;
- calibrated disagreement;
- anti-sycophancy;
- explanation adaptation;
- memory relevance;
- context-sensitive humor;
- reject/repair backend outputs that violate user constraints.

Potential objective:

```text
final_user_outcome
+ technical_correctness
+ interaction_quality
+ verification_success
+ continuity_preservation
- cost
- latency
- unnecessary_delegation
- privacy_exposure
```

---

## Phase 9 — 🏛 Behavioral Preservation / Regression Lab

Сформировать набор versioned behavioral tests.

Для каждого historically important model:

```text
Dialogue Set
Humor Set
Emotional Calibration Set
Explanation Set
Writing Set
Intellectual Partnership Set
Anti-Sycophancy Set
Long-Conversation Set
```

Новая Human/Interaction Model должна проходить regression comparison.

---

## Phase 10 — 🤖 Multi-agent Capability Mesh

Исследовать topology:

```text
Strategic Brain
      ↓
Planner
      ↓
┌─────┼─────┬─────┐
▼     ▼     ▼     ▼
Coder Research Vision Worker
│     │     │     │
└─────┴─────┼─────┘
            ▼
        Verifier
            ↓
        Integrator
```

Оценивать не только quality, но:

- coordination overhead;
- correlated errors;
- context duplication;
- cost per verified outcome;
- recovery after worker failure.

---

## Phase 11 — 🐤 Model admission / canary system

Любая новая модель:

```text
candidate
  ↓
offline evaluation
  ↓
role-specific scorecard
  ↓
5% canary
  ↓
20%
  ↓
50%
  ↓
production role admission
```

Новая модель может заменить только конкретную роль.

---

## Phase 12 — 🚀 Production-grade Cognitive OS

Долгосрочная цель:

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

Система должна переживать model replacement без потери identity, task continuity и memory semantics.

---

## Open research questions

1. Каков minimum viable размер Interaction Model?
2. Какие conversational qualities находятся в weights, а какие в harness/system prompt?
3. Как воспроизводимо измерять Human Presence?
4. Сколько original context передавать через semantic handoff?
5. Когда cross-vendor review действительно достаточно независим?
6. Как uncertainty должна передаваться между моделями?
7. Может ли local Interaction Model безопасно sanitise tasks для cloud delegation?
8. Как compact long-horizon state без потери invariants?
9. Как обнаружить, что модель становится более уверенной, но не более правильной?
10. Какие historical behaviors стоит сохранять через distillation?
11. Можно ли обучить router выбирать не только model, но и reasoning strategy?
12. Как измерять cost не per token, а per verified completed task?
13. Как не превратить personalization в sycophancy?
14. Как определить границу между useful memory и intrusive memory?
15. Как сохранить stable human-facing identity при смене backend provider?

---

## Research philosophy

Repository должен предпочитать:

- measured behavior over mythology;
- role-specific evaluation over single leaderboards;
- evidence over confidence;
- explicit uncertainty over fabricated certainty;
- modular replacement over vendor lock-in;
- reproducible historical comparisons over nostalgia;
- preserved human interaction quality alongside technical progress.

> **Сначала измерить формы интеллекта, затем строить routing между ними — а не наоборот.**