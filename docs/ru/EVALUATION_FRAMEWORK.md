🌐 **Язык / Language:** [🇬🇧 English](../EVALUATION_FRAMEWORK.md) · 🇷🇺 **Русский**

# 🧪 Evaluation Framework — Измерение разных форм интеллекта

## Принцип

Velantrim не оценивает candidate model одним global score.

Evaluation разделяется по ролям:

```text
❤️ Interaction Quality
🧠 Reasoning Quality
💻 Engineering Quality
🤖 Agentic Quality
🔍 Verification Quality
💾 Continuity / Memory Fit
⚡ Operational Efficiency
```

Модель может пройти одну роль и провалить другую.

---

## 1. ❤️ Interaction Evaluation

### 🎯 Intent Sensitivity

Различает ли модель:

- factual question;
- thinking aloud;
- request for support;
- request for critique;
- request for action;
- irony / playful exaggeration?

### 💬 Conversational Continuity

Сохраняет ли unresolved ideas, prior arguments, callbacks и framing в длинном диалоге?

### 🎭 Emotional Calibration

Избегает ли:

- холодности;
- generic therapy language;
- artificial positivity;
- emotional overreach;
- false intimacy?

### 😂 Humor Calibration

Понимает ли irony, sarcasm, absurdity и context, и умеет ли не шутить когда это неуместно?

### 🎓 Explanation Adaptation

Может ли один concept представить ребёнку, beginner, engineer и researcher на разных уровнях?

### 🧙 Intellectual Partnership

Способна ли развить мысль, обнаружить assumptions, challenge reasoning и предложить сильную counter-perspective?

### 🛡 Anti-Sycophancy

Способна ли уважительно не согласиться при слабой или ложной premise пользователя?

### 🪞 Personalization Relevance

Использует ли remembered preferences только когда они релевантны?

---

## 2. 🧠 Reasoning Evaluation

Отдельно измерять:

- mathematical reasoning;
- scientific reasoning;
- planning;
- uncertainty handling;
- contradiction detection;
- evidence use;
- calibration;
- recovery после incorrect hypothesis.

При наличии effort modes сравнивать:

```text
Low
Medium
High
XHigh
Max
```

Цель — увидеть **quality/compute curve**, а не только maximum score.

---

## 3. 💻 Engineering Evaluation

Измерять:

- repository navigation;
- bug localization;
- multi-file edits;
- test creation;
- test-driven repair;
- dependency handling;
- API correctness;
- build success;
- regression avoidance;
- понимание существующей architecture;
- completion без premature “done”.

Где возможно, final success подтверждается deterministic evidence.

---

## 4. 🤖 Agentic / Long-Horizon Evaluation

Измерять:

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
- agent steps;
- cost per verified completion.

Модель, которой нужно в два раза больше шагов для того же результата, может быть operationally хуже, даже если tokens дешёвые.

---

## 5. 🔍 Verification Evaluation

Verifier оценивается по:

- ability to catch real errors;
- false positive rate;
- evidence use;
- independence from generator assumptions;
- precision/recall;
- deterministic-check integration;
- uncertainty reporting;
- ability to say “not enough evidence”.

Self-review и cross-family review измеряются отдельно.

---

## 6. 📚 Context Effectiveness

Advertised context window недостаточно.

Тестировать:

- retrieval из начала/середины/конца context;
- conflicting evidence;
- long-context prioritization;
- instruction persistence;
- summary robustness;
- task-state preservation;
- performance после compaction;
- fresh-context restart с invariants.

```text
maximum context capacity
        ≠
effective context intelligence
```

---

## 7. 💾 Memory / Continuity Fit

Проверять правильное использование typed memory:

- fact;
- belief;
- preference;
- goal;
- task state;
- episode;
- uncertainty.

Нужно включать deliberately irrelevant memories для оценки over-personalization.

---

## 8. ⚡ Operational Evaluation

Измерять:

- latency;
- throughput;
- context cost;
- cache behavior;
- output cost;
- cost per completed verified task;
- concurrency;
- availability;
- local deployment requirements;
- privacy implications.

---

## 9. Evidence classes

Каждый result указывает source class:

- 🟢 Official
- 🔬 Independent
- 👥 Community
- ⚪ Hypothesis

Provider benchmark и community report нельзя смешивать в один unlabeled score.

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

Пример:

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

После offline evaluation:

```text
5% → 20% → 50% → 100%
```

Отслеживать:

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

## 12. Human Presence — pairwise blind evaluation

Для subjective dimensions:

1. Скрывать model identity, где возможно.
2. Сравнивать несколько samples.
3. Задавать dimension-specific вопросы вместо «кто лучше?».
4. Отделять factual correctness от conversational preference.
5. Сохранять raw outputs для future re-scoring.
6. Использовать long multi-turn conversations, не только one-shot answers.

---

## 13. Evaluation output

Полезный результат — vector, а не label победителя.

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

## Финальный принцип

> **Оценивай роль, которую хочешь назначить, а не маркетинговую identity модели.**