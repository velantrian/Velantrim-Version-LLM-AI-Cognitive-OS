🌐 **Язык / Language:** [🇬🇧 English](../FULL_HANDOFF.md) · 🇷🇺 **Русский**

# 📜 Полный канонический handoff — Velantrim Version LLM (AI) 💫

## 0. Зачем существует этот документ

Этот файл сохраняет **полную архитектурную логику**, сформированную в исследовании Velantrim Version LLM (AI): эволюцию моделей, проблему деградации, разделение Human/Interaction Intelligence и Technical/Capability Intelligence, динамический routing, внешнюю память, независимую verification и идею Cognitive OS.

Главный тезис:

> **Не пытаться победить деградацию поиском вечной идеальной модели. Нужно построить систему так, чтобы отдельная LLM могла ошибаться, деградировать, устаревать или быть заменена — а целостность интеллекта, памяти, человеческого интерфейса, целей и контроля при этом сохранялась.**

---

# 1. Что здесь называется «деградацией»

Деградация — не один эффект.

```text
                    DEGRADATION
                         │
       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
 🧠 Cognitive       💬 Conversational    🔄 Temporal
 reasoning drift     потеря нюанса        context rot
 hallucinations      сухость/шаблонность  summary drift
 overthinking        sycophancy           noise accumulation

       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
 🤖 Agent           💾 Memory           🏭 Product/Model
 loops              stale retrieval     behavior changes
 goal drift         false memory        checkpoint shift
 tool misuse        belief/fact mix     optimization shift
```

Различные типы требуют разных механизмов защиты.

---

# 2. 🌀 Context rot

Большой context window не гарантирует эффективной работы со всем контекстом.

В длинной сессии накапливаются:

- старые assumptions;
- tool outputs;
- failed branches;
- outdated plans;
- reasoning traces;
- summaries of summaries;
- duplicated evidence;
- противоречащие инструкции;
- irrelevant history.

```text
больше context
     ↓
больше информации
     ↓
больше шума
     ↓
сложнее выделить главное
     ↓
ошибки / forgetting / drift
```

Поэтому:

> **Maximum context ≠ effective context.**

Предпочтительный рабочий prompt:

```text
Original Objective
+ Current State
+ Relevant Memory
+ Recent Trajectory
+ Needed Evidence
```

---

# 3. 🤖 Почему agent деградирует во времени

Agent — не одна непрерывная мысль.

```text
LLM
 ↓
ACTION
 ↓
environment
 ↓
OBSERVATION
 ↓
LLM
 ↓
ACTION
 ↓
...
```

Через десятки или сотни циклов появляется риск:

- goal drift;
- false assumptions becoming state;
- repeated tools;
- planning oscillation;
- accidental scope expansion;
- premature completion;
- loss of original user constraints.

Поэтому задача должна иметь explicit external state.

---

# 4. 🎯 Task invariants

Некоторые элементы нельзя разрешать активной модели переписывать самостоятельно.

```yaml
task_invariants:
  original_goal: ...
  hard_constraints:
    - ...
  user_non_goals:
    - ...
  acceptance_criteria:
    - ...
  safety_boundaries:
    - ...
```

Working plan может изменяться.

Invariants изменяются только явно.

---

# 5. 🧠 Reasoning effort тоже способен ухудшать результат

Режимы `Low / Medium / High / XHigh / Max` или их аналоги — это не обязательно разные weights. Часто это различный reasoning budget, stopping policy или agent behavior.

Больше reasoning не означает монотонно лучший результат.

Для простой задачи высокий effort может вызвать:

- переусложнение;
- лишние hypotheses;
- больше tools;
- больше context;
- overthinking;
- дополнительные точки отказа.

Базовая policy:

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

Если `High` дважды не помог:

```text
НЕ обязательно → Max
```

Можно:

- сменить модель;
- сменить model family;
- начать с fresh context;
- изменить reasoning strategy;
- разбить задачу иначе;
- привлечь независимого verifier.

---

# 6. 🧠 Single-model monoculture

Если одна модель:

1. понимает запрос;
2. строит plan;
3. выполняет работу;
4. проверяет себя;
5. объясняет результат;

то её исходная ошибка может пройти через всю pipeline.

```text
wrong assumption
       ↓
PLAN
       ↓
IMPLEMENTATION
       ↓
SELF REVIEW
       ↓
"looks correct"
```

Поэтому независимая проверка другой family или deterministic tool часто ценнее ещё одного self-reflection той же модели.

---

# 7. Главный вывод сравнения современных моделей

Не существует одной модели, которая оптимальна для всех ролей.

Лучший strategic brain может быть слишком дорогим worker.

Лучший coding model может быть посредственным human-facing companion.

Модель с огромным context может проигрывать системе с лучшей compaction/memory architecture.

Следовательно:

> **Model selection должен происходить по cognitive role.**

---

# 8. 🧭 Model routing by cognitive role

Не:

```text
"Мы используем provider X"
```

а:

```text
эта задача требует:
- strategic reasoning
- coding
- research
- vision
- low latency
- privacy
- independent verification
```

и затем system выбирает конкретные backends.

---

# 9. Но одного router недостаточно

Из сравнения моделей возникла более глубокая идея:

> **качество взаимодействия с человеком — отдельная форма специализации.**

Современная индустрия всё сильнее оптимизирует frontier-модели под:

- reasoning;
- coding;
- SWE;
- tools;
- computer use;
- long-horizon autonomy;
- cost/task;
- production reliability.

Но человеку AI нужен не только как compute engine.

AI также является интерфейсом к машинному интеллекту.

---

# 10. ❤️ Human / Interaction Model

Interaction Model специально оптимизирована под **человека и коммуникацию**.

Она должна понимать:

- intent;
- pragmatics;
- emotional context;
- humor;
- irony;
- desired depth;
- user expertise;
- conversation continuity;
- creativity;
- intellectual partnership.

Ключевая формула:

> **Interaction Model думает о человеке, намерении и коммуникации.**

---

# 11. 🧠 Technical / Capability Models

Capability Models оптимизированы под:

- complex reasoning;
- mathematics;
- coding;
- research;
- tool calling;
- computer use;
- document analysis;
- planning;
- APIs;
- databases;
- simulation;
- long-horizon execution.

Они могут быть больше, дороже, медленнее и менее разговорными.

Это нормально.

> **Они compute engines, а не обязательная personality системы.**

---

# 12. ❤️↔️🧠 Исходная двухмодельная архитектура

```text
                  👤 USER
                     │
                     ▼
          ❤️ HUMAN / INTERACTION
                     │
        ┌────────────┴────────────┐
        │                         │
    отвечает сама            delegation
                                  │
                                  ▼
                         🧠 TECHNICAL MODEL
                                  │
                                  ▼
                          technical output
                                  │
                                  ▼
                         ❤️ INTERACTION
                                  │
                                  ▼
                               👤 USER
```

Позднее эта идея эволюционировала в multi-plane Cognitive OS.

---

# 13. 🔄 Semantic handoff: Human → Technical

Human Model не должна просто отправлять raw prompt.

Она формирует structured task specification:

```yaml
request:
  original_user_message: ...
  interpreted_intent: ...
  user_level: ...
  desired_depth: ...

constraints:
  ...

uncertainties:
  - ...

do_not_assume:
  - ...

requested_output:
  - factual_analysis
  - tradeoffs
  - recommendation
  - uncertainty
  - evidence
```

---

# 14. Нельзя уничтожать original user request

Interaction Model сама может ошибиться при интерпретации.

Поэтому backend должен получать и:

- original request;
- interpreted intent;
- constraints;
- uncertainties;
- do-not-assume list.

Human Layer добавляет структуру, но не должен становиться **lossy codec**.

---

# 15. 🔄 Technical → Human

Technical Model может вернуть:

```text
architecture
benchmarks
trade-offs
implementation details
uncertainties
```

Interaction Model преобразует это в:

```text
что это значит
      ↓
почему это важно
      ↓
какие варианты существуют
      ↓
что подходит именно пользователю
      ↓
что делать дальше
```

Это semantic interpretation, а не просто перевод терминов.

---

# 16. Human Model может спорить с Technical Model

Если backend предлагает technically impressive решение, которое нарушает user constraints, Interaction Model возвращает задачу на пересчёт.

Пример:

```text
Technical:
Kubernetes + Kafka + service mesh

Known user constraints:
solo developer
small app
minimal budget
low maintenance
```

Interaction Model:

> «Решение слишком инфраструктурно тяжёлое. Пересчитай с приоритетом простоты.»

Это collaboration, а не frontend/backend pass-through.

---

# 17. Но Human Model не должна быть technical verifier

Если Human Model специально менее сильна в math/coding, она не может надёжно подтвердить proof или сложную implementation более сильного reasoner.

Поэтому нужен отдельный:

# 🔍 Assurance Plane

```text
❤️ Interaction
→ подходит ли результат человеку?

🔍 Assurance
→ является ли результат правильным?
```

---

# 18. 🧭 Cognitive Control Plane

Interaction Model также не должна быть единственным router, memory manager, judge и persona.

Control Plane выбирает:

- model family;
- role;
- reasoning effort;
- serving mode;
- agent strategy;
- context strategy;
- tools;
- verifier;
- privacy policy;
- latency;
- budget.

---

# 19. Router выбирает не только модель

Полная конфигурация:

```text
TASK
 │
 ├─ MODEL
 ├─ ROLE
 ├─ REASONING EFFORT
 ├─ SERVING MODE
 ├─ AGENT STRATEGY
 ├─ CONTEXT STRATEGY
 ├─ TOOLS
 └─ VERIFICATION
```

Это уже **cognitive scheduling**.

---

# 20. Dynamic escalation

```text
Low
 ↓ failure
Medium
 ↓ failure
High
```

После repeated failure:

```text
switch model family
       ↓
fresh context
       ↓
different strategy
       ↓
independent verifier
```

Система должна уметь остановиться с `unresolved`, а не зациклиться бесконечно.

---

# 21. 🔍 Независимая verification

Критический principle:

```text
Model A creates
       ↓
Model B attacks
       ↓
deterministic tests
       ↓
Model C integrates
```

Проверка может включать:

- unit/integration tests;
- compiler;
- static analysis;
- theorem prover;
- web/source evidence;
- database constraints;
- policy checks;
- independent model family.

---

# 22. ⚡ Worker swarm

Frontier brain не должен выполнять каждую мелкую задачу.

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
Verification
      ↓
Integration
```

Cheap/specialized models образуют worker layer.

---

# 23. Model role hierarchy

```text
L0 — local reflex / trivial
L1 — cheap worker
L2 — capable specialist
L3 — frontier reasoner
L4 — extreme orchestrator
```

Escalation происходит только когда оправдана сложностью, риском или failure history.

---

# 24. 💾 Memory Plane

Память существует отдельно от transient LLM context.

```text
MEMORY
 │
 ├── 👤 User Model
 ├── 🎯 Task State
 ├── 📜 Episodic Memory
 ├── 📚 Semantic Knowledge
 └── ✅ Verified Facts
```

---

# 25. 🪞 User Model

Не hidden psychological profiling, а practical communication state:

```yaml
communication:
  detail_level: high
  technical_level: ...
  prefers_examples: true

current_goals:
  - ...

open_questions:
  - ...
```

---

# 26. Preference ≠ Fact

Система различает:

- пользователь знает;
- пользователь считает;
- пользователь предпочитает;
- система знает;
- система не уверена.

```text
user believes X
      ≠
X is true
```

---

# 27. Memory relevance

> **Memory exists ≠ memory should be used.**

Нужно отдельно учить relevance policy.

---

# 28. 🔥🌤❄️ Hot / Warm / Cold

```text
🔥 HOT
→ current working context

🌤 WARM
→ decisions, summaries, relevant documents

❄️ COLD
→ full archive / forensic history
```

Большинство turns не должны автоматически загружать весь Cold archive.

---

# 29. Summary provenance

Никакая summary не является абсолютной истиной.

```yaml
summary:
  content: ...
  source_refs: [...]
  confidence: ...
  created_by: ...
  timestamp: ...
```

При конфликте система возвращается к primary source.

---

# 30. 🤝 Anti-sycophancy

Оптимизация только на user approval ведёт к:

```text
pleasantness
 ↓
agreement
 ↓
flattery
 ↓
sycophancy
 ↓
bad decision
```

Правильнее:

```text
truthfulness
+ understanding
+ usefulness
+ tact
+ emotional calibration
+ intellectual honesty
+ appropriate disagreement
- sycophancy
- manipulation
```

---

# 31. ❤️ Human Model не обязательно маленькая

Идея 10–30B local model интересна, но размер не должен быть частью определения.

Понимание:

```text
сарказм
+ 20 turns истории
+ непрямое intent
+ cultural context
+ user memory
+ эмоциональная смена
```

может быть сложным inference problem.

Interaction Model должна быть настолько большой, насколько требуется capability.

---

# 32. Distillation для Human Model

Возможный training pipeline:

```text
Frontier teachers
      ↓
synthetic dialogues
      ↓
expert filtering
      ↓
human preference data
      ↓
adversarial examples
      ↓
❤️ Interaction Model
```

Особенно важны contrastive pairs:

```text
❌ technically correct / socially wrong
✅ technically correct / socially appropriate

❌ pleasant but sycophantic
✅ tactful but truthful

❌ immediately gives advice
✅ recognizes thinking aloud
```

---

# 33. 🎓 Обучение объяснению

Не просто style transfer.

```text
Knowledge Representation
          ↓
Audience Model
          ↓
Explanation Planner
          ↓
Language Realization
```

Один объект может иметь разные объяснения для ребёнка, студента, developer, ML engineer и researcher.

---

# 34. 😂 Humor policy

Юмор требует не только generation, но policy.

```text
literal text
     ↓
pragmatics
     ↓
irony detection
     ↓
context / relationship
     ↓
response decision
```

Иногда уместна шутка. Иногда правильный ответ — немедленно перейти к делу.

---

# 35. 🧙 «Мудрый собеседник»

Нельзя определять wisdom как «пользователю понравился ответ».

Иначе:

```text
approval seeking
      ↓
agreement
      ↓
flattery
      ↓
sycophancy
```

Нужен многомерный objective:

```text
truth + perspective + calibrated disagreement + usefulness + respect
```

---

# 36. 🔐 Local-first Human Model

```text
                    DEVICE
                       │
             ❤️ Interaction Model
                       │
                 private memory
                       │
          ┌────────────┴────────────┐
          │                         │
    local conversation        sanitized task
                                    │
                                    ▼
                             ☁️ Frontier AI
                                    │
                                    ▼
                              raw solution
                                    │
                                    ▼
                           ❤️ local model
                                    │
                                    ▼
                                  USER
```

Преимущества:

- privacy;
- low latency;
- stable interaction style;
- cloud vendor replaceability;
- cheap ordinary conversation;
- local personal memory.

---

# 37. Joint training

Сам handoff можно обучать.

```text
USER
 ↓
Interaction
 ↓
Routing
 ↓
Capability
 ↓
Verification
 ↓
Interaction
 ↓
USER OUTCOME
```

Reward:

```text
technical correctness
+ user outcome
+ communication quality
+ verification success
+ continuity
- cost
- latency
- unnecessary delegation
- privacy exposure
```

---

# 38. Communication protocol

```yaml
request:
  original_user_message: ...
  interpreted_intent: ...
  user_level: ...
  desired_depth: ...

constraints:
  privacy: ...
  priorities: [...]

uncertainties:
  - ...

requested_output:
  - findings
  - tradeoffs
  - recommendation
  - uncertainty
  - evidence
```

Backend:

```yaml
confidence: 0.82
findings: [...]
tradeoffs: [...]
recommendation: [...]
uncertainties: [...]
evidence: [...]
```

---

# 39. Финальная four-plane архитектура + Memory

```text
                      👤 USER
                         │
                         ▼
        ╔══════════════════════════╗
        ║ ❤️ INTERACTION PLANE    ║
        ╚════════════╤═════════════╝
                     │
                     ▼
        ╔══════════════════════════╗
        ║ 🧭 COGNITIVE CONTROL    ║
        ╚════════════╤═════════════╝
                     │
      ┌──────────────┼───────────────┐
      ▼              ▼               ▼
 🧠 Reasoner     💻 Coder       🔎 Researcher
      │              │               │
      ├──────────────┼───────────────┤
      ▼              ▼               ▼
 👁 Vision       🛠 Executor      Specialists
      │
      └──────────────┼───────────────┘
                     ▼
        ╔══════════════════════════╗
        ║ 🔍 ASSURANCE PLANE      ║
        ╚════════════╤═════════════╝
                     │
                     ▼
           ❤️ INTERACTION PLANE
                     │
                     ▼
                   👤 USER

       ═══════════════════════════
              💾 MEMORY PLANE
       ═══════════════════════════
```

---

# 40. Как архитектура борется с деградацией

| Проблема | Механизм |
|---|---|
| 🌀 Context rot | compaction + external memory + short active context |
| 🎯 Goal drift | immutable original objective + task state |
| 🧠 Overthinking | dynamic effort + strategy switch |
| ♻️ Agent loops | telemetry + retry limits + replan |
| 🔁 Self-confirmation | independent verifier |
| 🧬 Vendor weakness | model routing |
| 💰 Expensive inference | cheap worker layer |
| ❤️ Human-quality regression | dedicated Interaction Model |
| 🤝 Sycophancy | explicit anti-sycophancy objective |
| 💾 Bad personalization | typed beliefs/preferences/facts |
| 🏭 Backend style drift | stable Interaction Layer |
| 📉 Model regression | role-specific evaluation |
| 📚 Huge-context dependence | retrieval + external memory |
| 🔄 Lossy delegation | preserve original request |
| 🔍 Hallucination | deterministic verification |
| 🔒 Vendor lock-in | backend abstraction layer |

---

# 41. Защита от model updates

Если Personal AI построен вокруг одного checkpoint:

```text
Model update
     ↓
behavior changes
     ↓
memory interpreted differently
     ↓
style changes
     ↓
agent behavior changes
     ↓
whole system feels different
```

Layered architecture:

```text
Model update
     ↓
Capability Plane changes
     ↓
Interaction remains
Memory remains
Control policy remains
Verification remains
User model remains
```

---

# 42. Benchmark intelligence ≠ agent quality ≠ user experience

```text
Agent quality =
Model
× reasoning effort
× system prompt
× tools
× context management
× memory
× retrieval
× retry strategy
× verification
× agent topology
× inference latency
```

Поэтому leaderboard не является достаточным критерием замены backend.

---

# 43. Evaluation перед admission

Каждая новая модель проходит отдельно:

```text
❤️ Interaction Eval
🧠 Reasoner Eval
💻 Coder Eval
🤖 Long-Horizon Eval
🛠 Tool Eval
🔍 Verifier Eval
💰 Cost Eval
⚡ Latency Eval
📚 Context Eval
```

Решение принимается по роли.

---

# 44. 🐤 Canary deployment

```text
candidate
  ↓
5%
  ↓ compare
20%
  ↓ compare
50%
  ↓ compare
100% only if role evidence green
```

Metrics:

- success;
- cost;
- latency;
- user correction rate;
- retry count;
- verification failures;
- context consumption;
- hallucination rate;
- tool failures.

---

# 45. Automatic degradation detection

```text
retry count ↑
context size ↑
confidence ↓ or confidence/evidence mismatch ↑
verification failures ↑
user corrections ↑
tool loops ↑
task progress ↓
```

После threshold:

```text
STOP
 ↓
compact
 ↓
restore invariants
 ↓
replan
 ↓
switch model / strategy
 ↓
independent review
```

---

# 46. Историческая эволюция моделей — почему это вообще возникло

Наблюдаемая индустриальная траектория:

```text
✨ Experimental conversation
      ↓
💬 Personality / creativity
      ↓
👁 Voice / multimodality
      ↓
🧠 Reasoning
      ↓
💻 Coding / tools
      ↓
🤖 Agents / swarms
      ↓
🏢 Corporate / production automation
```

Это не означает, что модели «стали хуже».

Они часто **стали другими**.

---

# 47. ❤️ Human Presence и ⚙️ Engineering Power — разные оси

Модель может одновременно:

```text
reasoning ↑
coding ↑
agents ↑
tool reliability ↑
```

и иметь неизвестное или изменившееся:

```text
presence ?
humor ?
creative voice ?
emotional calibration ?
conversational depth ?
```

Поэтому Human Presence нельзя выводить из SWE-Bench или reasoning score.

---

# 48. 🏛️ Behavioral Museum

Нельзя полагаться на память пользователей в стиле «раньше Claude/Grok был живее».

Нужно сохранять:

- dialogues;
- system/model configuration;
- humor cases;
- emotional calibration;
- explanation tasks;
- creative writing;
- long-conversation tests;
- user preference comparisons.

Это создаёт reproducible behavioral history.

---

# 49. 🧬 Model Genome

Не один score, а профиль:

```yaml
model_profile:
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
    context_effectiveness: ...

  operational:
    latency: ...
    cost_per_verified_task: ...
    privacy: ...
```

---

# 50. Основной исторический тезис

Индустрия во многом движется от:

> **«AI-собеседник, который также умеет работать»**

к:

> **«AI-работник, который также умеет разговаривать».**

Velantrim не отвергает этот переход.

Цель — сохранить обе линии развития.

---

# 51. Interaction quality не должна зависеть от очередного frontier checkpoint

Если завтра backend станет лучше coder, но хуже conversationally, Personal AI не должен потерять human-facing identity.

```text
USER EXPERIENCE
      │
      ▼
❤️ Stable Interaction Layer
      │
      ▼
replaceable capability models
```

---

# 52. LLM — не система

Самая короткая формула:

```text
LLM = replaceable cognitive processor

SYSTEM = persistent intelligence
```

Постоянство принадлежит:

- memory;
- user model;
- task state;
- policies;
- verification;
- interaction identity;
- provenance.

---

# 53. Personal AI находится не в одном checkpoint

```text
              PERSONAL AI
                   │
       ┌───────────┼────────────┐
       ▼           ▼            ▼
   User Model    Memory      Interaction
       │           │            │
       └───────────┼────────────┘
                   ▼
             Cognitive OS
                   │
       ┌───────────┼────────────┐
       ▼           ▼            ▼
     Model A     Model B      Model C
     Local       Cloud        Specialist
```

---

# 54. Главные роли

```text
❤️ Interaction
понимает человека

🧭 Control
решает, как думать

🧠 Capability
решает задачу

🔍 Assurance
проверяет результат

💾 Memory
сохраняет состояние
```

---

# 55. Главный anti-degradation principle

> **Не доверять долговременную целостность системы внутреннему состоянию одной LLM.**

Цель, память, verification, routing и user model должны существовать явно вне weights и transient context.

---

# 56. Исследовательская цель

Создать AI, который:

- не теряет human-quality из-за гонки coding/reasoning benchmarks;
- не зависит от одного vendor;
- не деградирует катастрофически в длинных trajectories;
- не хранит всю личность в context window;
- не принимает self-review за proof;
- использует expensive frontier compute только когда нужно;
- умеет менять effort;
- умеет менять strategy;
- умеет менять model;
- умеет проверять результат независимо;
- сохраняет user model и continuity;
- остаётся последовательным после backend replacement.

---

# 57. Конечная формула

```text
              ❤️ Human Interface
                      │
                understands
                      │
                      ▼
               🧭 Cognitive OS
                      │
            decides how to think
                      │
       ┌──────────────┼──────────────┐
       ▼              ▼              ▼
   🧠 models       🤖 agents       🛠 tools
       │              │              │
       └──────────────┼──────────────┘
                      ▼
                🔍 verification
                      │
                      ▼
                 💾 memory/state
                      │
                      ▼
              ❤️ interpretation
                      │
                      ▼
                    👤 USER
```

> **Не вечная модель, а устойчивый интеллект.**

Это и есть центральная исследовательская позиция Velantrim Version LLM (AI).