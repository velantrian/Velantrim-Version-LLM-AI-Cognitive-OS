# 🚀 Velantrim Version LLM (AI) — Cognitive OS 💫

<div align="center">

🌐 **Язык / Language:** [🇬🇧 English](README.md) · 🇷🇺 **Русский**

**❤️ Human Interaction · 🧭 Cognitive Routing · 🧠 Capability Models · 🔍 Assurance · 💾 Persistent Memory**

</div>

> **LLM = заменяемый когнитивный процессор.**  
> **Cognitive OS = постоянный интеллект системы.**

Velantrim Version LLM (AI) исследует модульную когнитивную архитектуру, в которой **интеллект взаимодействия с человеком** и **технический машинный интеллект** не обязаны находиться внутри одного универсального checkpoint. Они сотрудничают через явный routing, структурированную память, независимую verification и semantic handoff.

Проект основан на простом наблюдении: **прогресс моделей многомерен**. Новое поколение может стать гораздо сильнее в reasoning, coding, tool use, multimodality и long-horizon agency, но одновременно изменить характер разговора, творческий стиль, юмор, спонтанность, эмоциональную калибровку или способ объяснения. Это не обязательно деградация — часто это смена целей оптимизации.

Velantrim Cognitive OS проектируется так, чтобы прогресс в одной области не требовал уничтожения полезных качеств в другой.

---

## ⚡ Главная идея

Вместо попытки заставить одну универсальную модель одновременно быть лучшим:

- ❤️ человеческим собеседником и companion;
- 🎭 социально калиброванным коммуникатором;
- 😂 собеседником с юмором и чувством контекста;
- ✍️ писателем, редактором и творческим партнёром;
- 🎓 адаптивным учителем и объясняющим;
- 🧠 стратегическим reasoner;
- 💻 coding-agent;
- 🔎 исследователем;
- 🤖 автономным оператором;
- 🛠 пользователем инструментов и компьютера;
- 🔍 verifier;
- 💾 хранителем памяти;

Velantrim разделяет эти обязанности между взаимодействующими когнитивными плоскостями.

```text
                         👤 USER
                            │
                            ▼
                 ❤️ Interaction Plane
                            │
                 intent · context · meaning
                            │
                            ▼
                 🧭 Cognitive Control
                            │
           ┌────────────────┼────────────────┐
           ▼                ▼                ▼
       🧠 Reasoner       💻 Coder       🔎 Researcher
           │                │                │
           ├────────────────┼────────────────┤
           ▼                ▼                ▼
       👁 Vision         🛠 Tools        🧬 Specialist
           │
           └────────────────┬────────────────┘
                            ▼
                     🔍 Assurance
                            │
                            ▼
                 ❤️ Human Interpretation
                            │
                            ▼
                         👤 USER

               ═════════════════════════
                   💾 Memory Plane
               user · task · episodes
               facts · provenance · state
               ═════════════════════════
```

---

## 🧬 Пять плоскостей

| Плоскость | Главный вопрос | Ответственность |
|---|---|---|
| ❤️ **Interaction** | Что человек на самом деле имеет в виду и как лучше это ему представить? | Intent, dialogue, explanation, humor, creativity, adaptation, semantic handoff |
| 🧭 **Cognitive Control** | Кто должен думать и как? | Model routing, reasoning effort, serving mode, tools, context policy, latency, privacy, cost |
| 🧠 **Capability** | Как решить задачу? | Reasoning, coding, research, vision, documents, agents, specialists |
| 🔍 **Assurance** | Можно ли доверять результату? | Tests, evidence, deterministic checks, adversarial review, cross-model verification |
| 💾 **Memory** | Что должно сохраняться между вызовами моделей? | User model, task state, provenance, Hot/Warm/Cold memory, verified facts |

---

## ❤️ Interaction Model

Interaction Model — это **не** уменьшенная technical model с system prompt «будь дружелюбным». Её специализация — человеческая сторона интеллекта:

- понимание намерения и прагматики разговора;
- различение фактического вопроса и размышления вслух;
- эмоциональная калибровка без превращения каждой эмоции в терапию;
- юмор, ирония, callbacks и чувство момента;
- адаптация глубины объяснения к конкретному человеку;
- интеллектуальное партнёрство и корректное несогласие;
- письмо, storytelling, редактирование и метафоры;
- преобразование человеческого намерения в machine-oriented specification;
- преобразование технического результата обратно в полезный человеческий смысл.

Её objective не должен быть просто «сделать пользователя довольным», потому что это может поощрять sycophancy.

```text
Good Human Interaction =
  truthfulness
+ intent understanding
+ usefulness
+ tact
+ explanatory quality
+ social calibration
+ intellectual honesty
+ appropriate disagreement
- sycophancy
- manipulation
- false intimacy
- over-personalization
```

---

## 🧠 Capability Models

Capability-модели оптимизированы под работу с машинными задачами:

- сложное reasoning и математика;
- coding и debugging;
- research и document analysis;
- tool use и computer use;
- planning и structured outputs;
- long-horizon agent workflows;
- APIs, databases и simulations;
- specialist и verification-oriented задачи.

Они могут быть крупнее, медленнее, дороже и менее разговорными. Это нормально: они являются **compute engines**, а не обязательно личностью системы.

---

## 🧭 Cognitive routing

Router должен выбирать не только имя модели.

```text
TASK
 │
 ├─ model role?
 ├─ model family?
 ├─ reasoning effort?
 ├─ serving mode?
 ├─ reasoning / agent strategy?
 ├─ context strategy?
 ├─ tools?
 ├─ verifier?
 ├─ privacy boundary?
 └─ cost / latency budget?
```

Полезная базовая лестница reasoning effort:

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

Но повторная ошибка не должна автоматически означать «дать больше токенов». Система может сменить model family, начать с fresh context, выбрать другую reasoning strategy, иначе декомпозировать задачу или привлечь независимого verifier.

---

## 🔍 Assurance вместо самодоверия

Модель, которая создала решение, не должна быть единственным судьёй собственной корректности.

```text
Model A creates
      ↓
Model B attacks
      ↓
deterministic tests
      ↓
Model C integrates
```

Assurance может включать compilers, tests, static analysis, formal verification, source-backed factual checks, database constraints, policy checks и независимых reviewers из другой model family.

> ❤️ Interaction спрашивает: **Подходит ли этот ответ человеку?**  
> 🔍 Assurance спрашивает: **Можно ли считать этот ответ достоверным?**

---

## 💾 Persistent Memory и anti-degradation

Большой context window — не то же самое, что долговременная память.

```text
🔥 HOT  → активный рабочий контекст
🌤 WARM → решения, summaries, relevant documents
❄️ COLD → полный архив / forensic history
```

Активная модель в идеале получает:

```text
Original Objective
+ Current State
+ Relevant Memory
+ Recent Trajectory
+ Needed Evidence
```

Критические invariants задачи должны существовать вне transient model context:

```yaml
task_invariants:
  original_goal: ...
  hard_constraints: [...]
  user_non_goals: [...]
  acceptance_criteria: [...]
  safety_boundaries: [...]
```

Это помогает бороться с:

- 🌀 context rot;
- 🎯 goal drift;
- ♻️ agent loops;
- 🧠 self-confirming errors;
- 💾 memory contamination;
- 🤝 sycophancy;
- 🏭 model-update regression.

---

## 🕰️ Эволюция моделей: от разговорных экспериментов к agentic systems

Один из ключевых исследовательских вопросов — как AI перешёл от продуктов типа «вау, он разговаривает» к production-grade cognitive workers.

```text
✨ conversational novelty
        ↓
💬 character / writing / chat
        ↓
👁 voice + multimodality + long context
        ↓
🧠 explicit reasoning
        ↓
💻 coding + tool use
        ↓
🤖 long-horizon agents
        ↓
🏢 production / enterprise automation
```

Это не автоматически «лучше» или «хуже». Часто это просто смена optimization target.

Поэтому Velantrim отслеживает как минимум две независимые группы качеств:

- ❤️ **Human Presence** — разговор, характер, юмор, творчество, эмоциональная калибровка, объяснение, интеллектуальное companionship;
- ⚙️ **Engineering / Agentic Power** — reasoning, coding, tools, reliability, autonomy, long-horizon execution, cost/task.

В исследовании рассматриваются Anthropic Claude, OpenAI GPT/Codex, xAI Grok/Grok Voice, Google Gemini, DeepSeek, Kimi, Qwen, Mistral, Meta/Llama и новые agent-oriented семьи, GLM, MiniMax и другие emerging open/proprietary systems.

---

## 🏛️ Behavioral Museum

Будущая система не должна выбрасывать удачные поведенческие качества только потому, что checkpoint устарел.

**Behavioral Museum** сохраняет воспроизводимые примеры:

- 💬 репрезентативных диалогов;
- 😂 юмора, иронии и callbacks;
- ❤️ emotional calibration;
- 🧙 глубоких интеллектуальных бесед;
- 🎓 объяснений;
- ✍️ creative writing;
- 🧪 behavioral evaluations;
- ⚙️ model/system configuration;
- 📊 human-preference comparisons.

Цель не в том, чтобы вечно запускать старые модели. Цель — сохранить измеримые traits, чтобы их можно было воспроизводить, дистиллировать или использовать как regression tests.

---

## 🧬 Model Genome

Модели нужно оценивать как многомерные профили, а не как одно число в leaderboard.

```yaml
model_profile:
  human:
    interaction_presence: ...
    conversational_continuity: ...
    humor_and_playfulness: ...
    emotional_calibration: ...
    creativity_and_writing: ...
    explanation_quality: ...

  technical:
    reasoning: ...
    coding: ...
    agentic_long_horizon: ...
    tool_use: ...
    verification: ...
    context_effectiveness: ...

  operational:
    latency: ...
    cost_per_verified_task: ...
    privacy: ...

  evidence:
    official: ...
    independent: ...
    community: ...
    hypothesis: ...
```

Новая модель должна допускаться **по роли**, а не глобально.

> Пример: `+15% coding, −20% Interaction Presence` → ✅ новый **Coder**, ❌ не автоматически новый **Human Interface**.

---

## 🔐 Local-first направление

Особенно важная архитектура — локальная Interaction Model с выборочной cloud delegation:

```text
                    DEVICE
                       │
             ❤️ Interaction Model
                       │
                 private memory
                       │
          ┌────────────┴────────────┐
          │                         │
   local conversation         sanitized task
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

Это может снизить latency, сохранить стабильность взаимодействия, повысить privacy и сделать cloud capability providers заменяемыми.

---

## 📚 Документация / Documentation

Каждый канонический документ поддерживается на двух языках и содержит переключатель языка сверху.

| Тема | 🇷🇺 Русский | 🇬🇧 English |
|---|---|---|
| 🧬 Архитектура | [ARCHITECTURE.md](docs/ru/ARCHITECTURE.md) | [ARCHITECTURE.md](docs/ARCHITECTURE.md) |
| 📜 Полный канонический handoff | [FULL_HANDOFF.md](docs/ru/FULL_HANDOFF.md) | [FULL_HANDOFF.md](docs/FULL_HANDOFF.md) |
| 🕰️ Эволюция моделей | [MODEL_EVOLUTION.md](docs/ru/MODEL_EVOLUTION.md) | [MODEL_EVOLUTION.md](docs/MODEL_EVOLUTION.md) |
| 🛡️ Anti-degradation | [ANTI_DEGRADATION.md](docs/ru/ANTI_DEGRADATION.md) | [ANTI_DEGRADATION.md](docs/ANTI_DEGRADATION.md) |
| ❤️ Human / Interaction Model | [HUMAN_INTERACTION_MODEL.md](docs/ru/HUMAN_INTERACTION_MODEL.md) | [HUMAN_INTERACTION_MODEL.md](docs/HUMAN_INTERACTION_MODEL.md) |
| 🧭 Cognitive routing | [MODEL_ROUTING.md](docs/ru/MODEL_ROUTING.md) | [MODEL_ROUTING.md](docs/MODEL_ROUTING.md) |
| 🏛️ Behavioral Museum | [BEHAVIORAL_MUSEUM.md](docs/ru/BEHAVIORAL_MUSEUM.md) | [BEHAVIORAL_MUSEUM.md](docs/BEHAVIORAL_MUSEUM.md) |
| 🧬 Model Genome | [MODEL_GENOME.md](docs/ru/MODEL_GENOME.md) | [MODEL_GENOME.md](docs/MODEL_GENOME.md) |
| 🧪 Evaluation framework | [EVALUATION_FRAMEWORK.md](docs/ru/EVALUATION_FRAMEWORK.md) | [EVALUATION_FRAMEWORK.md](docs/EVALUATION_FRAMEWORK.md) |
| 🗺️ Research roadmap | [RESEARCH_ROADMAP.md](docs/ru/RESEARCH_ROADMAP.md) | [RESEARCH_ROADMAP.md](docs/RESEARCH_ROADMAP.md) |

---

## 🧭 Статус исследования

Сейчас репозиторий представляет **research architecture и design direction**, а не утверждение о завершённой production implementation.

Ключевые исследовательские вопросы:

1. Как измерять Human Presence независимо от technical intelligence?
2. Какие traits старых поколений моделей стоит сохранять?
3. Как Interaction Model должна делегировать задачи, не превращаясь в lossy semantic codec?
4. Как router должен сочетать качество, reasoning effort, cost, privacy и latency?
5. Насколько verifier должен быть независим от generating model?
6. Как память должна различать facts, beliefs, preferences и uncertain hypotheses?
7. Как обнаруживать degradation в длинных agent trajectories?
8. Можно ли совместно обучать Interaction и Capability models через outcome-level reward?
9. Как сохранять историческое поведение моделей как воспроизводимое evidence, а не как ностальгию?
10. Как стабильный человеческий интерфейс может пережить многократную замену backend-моделей?

---

## 🌟 Главный принцип

> **Не пытаться победить деградацию поиском вечной идеальной модели. Построить систему так, чтобы отдельная модель могла деградировать, ошибаться, устаревать или быть заменена — а непрерывность интеллекта, памяти, человеческого интерфейса и контроля сохранялась.**

### 🚀 Velantrim

Исследовательское направление к постоянным, модульным и ориентированным на человека когнитивным системам.