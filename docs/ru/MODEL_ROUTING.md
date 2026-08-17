🌐 **Язык / Language:** [🇬🇧 English](../MODEL_ROUTING.md) · 🇷🇺 **Русский**

# 🧭 Cognitive Routing

## Цель

Cognitive routing отвечает на вопрос:

> **Кто должен думать, насколько глубоко, какими инструментами, при каком budget и с какой проверкой?**

Router не должен просто выбирать provider. Он конфигурирует **полный cognitive execution path**.

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

Дополнительно он может учитывать:

- uncertainty;
- task criticality;
- required independence;
- modality;
- data sensitivity;
- previous failures;
- expected trajectory length;
- availability of deterministic verification.

---

## Role taxonomy

```text
L0 — local reflex / trivial task
L1 — cheap worker
L2 — capable specialist
L3 — frontier reasoner
L4 — extreme orchestrator
```

Frontier model не должна использоваться для каждого простого действия.

---

## Пример routing decision

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

## 🎚 Dynamic effort

Reasoning effort адаптивен:

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

Важно: `High → Max` не должен быть единственным escalation path.

```text
High fails twice
    ↓
choose among:
- fresh context
- new model family
- different reasoning strategy
- stronger verifier
- better decomposition
- human escalation
```

Больше reasoning tokens иногда только увеличивают overthinking и context pressure.

---

## Strategy routing

Возможные стратегии:

- Direct;
- internal Chain-of-Thought-like reasoning;
- ReAct;
- Plan → Execute;
- Reflection;
- Debate;
- Tree/Graph search;
- Multi-agent decomposition;
- Generate → Test → Repair;
- Research → Evidence → Synthesis.

Нет одной стратегии, которая оптимальна для всех задач.

---

## 💰 Cost-aware routing

Оптимизировать нужно **стоимость завершённой проверенной задачи**, а не только price/token.

```text
effective_cost =
  inference_cost
+ tool_cost
+ retry_cost
+ verifier_cost
+ failure_cost
+ human_recovery_cost
```

Дешёвая модель, которая делает 100 agent steps, может стоить больше сильной модели, которая решает задачу за 20.

---

## 🔍 Independence-aware routing

Для критических задач verification должна быть достаточно независимой.

```text
Generator: family A
Reviewer: family B
Verifier: compiler/tests
Integrator: family C or deterministic rule
```

Независимость — не бинарное свойство. Router должен учитывать:

- одинаковый provider?
- одинаковое семейство?
- одинаковый checkpoint?
- одинаковый system prompt/harness?
- одинаковые sources?
- есть ли deterministic evidence?

---

## 🔐 Privacy-aware routing

```text
private / trivial
   → local model

private / complex
   → local preprocessing + sanitized delegation

non-sensitive / complex
   → frontier cloud model
```

Router должен минимизировать unnecessary disclosure.

---

## ⚡ Latency-aware routing

Interactive tasks могут предпочитать:

- fast serving;
- smaller models;
- shallow effort;
- streaming;
- local inference.

Background tasks могут предпочитать:

- higher effort;
- multiple reviewers;
- long trajectories;
- slower but stronger models.

Таким образом, `Fast` и `High reasoning` — разные dimensions. Fast может быть serving policy, а High — reasoning budget.

---

## 🧠 Context-aware routing

Router должен выбирать не только модель, но и **context policy**.

Варианты:

```text
full_recent_context
compact_state
retrieval_only
fresh_context_with_invariants
long_context_research
```

Если trajectory деградирует, fresh context с restored task invariants может быть ценнее ещё 100K старого transcript.

---

## 🤖 Agent topology routing

Для некоторых задач полезен один агент.

Для других:

```text
Strategic Brain
      ↓
  decomposition
      ↓
┌─────┼─────┐
▼     ▼     ▼
W1    W2    W3
│     │     │
└─────┼─────┘
      ▼
Verifier
      ↓
Integrator
```

Router может выбирать:

- single agent;
- parallel workers;
- planner/executor;
- generator/reviewer;
- adversarial pair;
- hierarchical swarm.

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

Система должна предпочитать explicit `unresolved` бесконечному autonomous loop.

---

## Model routing by cognitive role

Вместо:

```text
"We use Claude"
```

или:

```text
"We use GPT"
```

архитектура думает так:

```text
эта задача требует:
- strategic reasoning
- repository coding
- low latency
- private data
- independent review
```

и затем выбирает соответствующие компоненты.

---

## Future learned router

Learned router может оптимизироваться по outcome:

```text
reward =
  task_success
+ verification_success
+ user_fit
+ continuity_preserved
- cost
- latency
- unnecessary_delegation
- privacy_exposure
- repeated_failures
```

Долгосрочная цель — **cognitive scheduling**, а не static model selection.

---

## Финальный принцип

> **Router должен выбирать не “какая LLM сейчас моднее”, а какую когнитивную конфигурацию требует конкретная задача.**