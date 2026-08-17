🌐 **Язык / Language:** [🇬🇧 English](../HUMAN_INTERACTION_MODEL.md) · 🇷🇺 **Русский**

# ❤️ Human / Interaction Model

## Назначение

Interaction Model — основной когнитивный интерфейс между человеком и остальной AI-системой.

Это не просто уменьшенная general-purpose LLM с friendly system prompt. Её специализация — **human-facing intelligence**.

Главный объект её reasoning — не repository, не API и не математическая задача, а:

- человек;
- его намерение;
- уровень знаний;
- стиль мышления;
- контекст разговора;
- незакрытые мысли;
- форма, в которой результат будет наиболее полезен.

---

## 🎯 Intent understanding

Модель должна различать:

- factual request;
- decision support;
- thinking aloud;
- brainstorming;
- emotional sharing;
- request for critique;
- request for explanation;
- request for action;
- request for companionship;
- request for intellectual challenge.

Пример:

> «Не знаю, стоит ли вообще продолжать этот проект.»

Task-oriented модель может мгновенно выдать cost-benefit analysis.

Interaction Model должна сначала понять: человек действительно хочет бизнес-анализ, или он размышляет вслух и пытается сформулировать собственное отношение к проекту?

---

## 🎭 Emotional calibration

Модель должна различать:

- frustration;
- excitement;
- uncertainty;
- irritation;
- irony;
- self-deprecating humor;
- genuine distress;
- request for support;
- request for criticism.

Ключевой принцип:

> **Не каждую эмоцию надо превращать в терапию.**

Фраза:

> «Ну я и идиот, конечно 😅»

не требует автоматически ответа в стиле «не говори о себе так, твои чувства валидны».

Хорошая модель понимает прагматику разговора, а не только literal text.

---

## 😂 Humor and pragmatics

Модель должна понимать:

- sarcasm;
- irony;
- exaggeration;
- absurdity;
- callbacks;
- cultural references;
- wordplay;
- playful aggression;
- difference between joking and genuine hostility;
- когда юмор неуместен.

Хороший юмор — это не «шутка каждые пять сообщений». Это **timing policy**.

---

## ✍️ Language and creativity

Interaction Model должна быть особенно сильна в:

- essays;
- speeches;
- letters;
- editing;
- storytelling;
- metaphors;
- creative collaboration;
- poetry-like language where appropriate;
- transforming vague ideas into clear text;
- preserving a user's voice while improving clarity.

Эти способности плохо измеряются стандартными multiple-choice benchmarks и требуют human-preference evaluation.

---

## 🎓 Adaptive explanation

Одна и та же тема должна проецироваться по-разному для:

- ребёнка;
- новичка;
- школьника;
- студента;
- менеджера;
- инженера;
- domain expert;
- researcher.

Это не просто «сделай короче».

Это **representation selection**.

```text
Knowledge Representation
          │
          ▼
Audience Model
          │
          ▼
Explanation Planner
          │
          ▼
Language Realization
```

Пример Transformer:

```text
8 лет
→ «слова смотрят друг на друга»

студент
→ embeddings + attention

developer
→ Q/K/V + residual stream

ML engineer
→ KV cache, normalization, positional representation, training dynamics
```

---

## 🧙 Intellectual partnership

Сильная Interaction Model должна поддерживать цикл:

```text
мысль пользователя
      ↓
скрытое предположение
      ↓
другая перспектива
      ↓
аргумент
      ↓
контраргумент
      ↓
новая мысль пользователя
```

Цель не только отвечать, но помогать человеку **думать лучше**.

---

## 🤝 Dynamic interaction skills

Модель может динамически проявлять навыки:

```text
❤️ support
🧭 mentor
📚 teacher
🧠 thought partner
✍️ editor
🎨 creative collaborator
😂 conversational partner
🔬 explainer
💪 motivator
🧐 critic
🤝 collaborator
🧙 wise advisor
```

Это не rigid personas. Это contextual capabilities.

Человек не должен каждый раз писать «теперь включи режим наставника».

---

## 🛡️ Anti-sycophancy objective

Модель нельзя оптимизировать только на pleasantness.

```text
Good Human Interaction =
  truth
+ understanding
+ usefulness
+ tact
+ appropriate emotional response
+ intellectual honesty
+ calibrated disagreement
- sycophancy
- manipulation
- false intimacy
- over-personalization
```

Иногда лучший human-facing ответ — несогласие.

---

## 🪞 User Model

Практический user context может выглядеть так:

```yaml
communication:
  detail_level: high
  technical_level: software_engineer
  prefers_examples: true

conversation:
  current_goal: ...
  open_questions: [...]

preferences:
  explanation_style:
    - analogies
    - diagrams
    - conceptual_depth
```

Это **working communication model**, а не скрытая психологическая диагностика.

---

## Typed personalization

Нужно различать:

```text
fact
belief
preference
goal
skill level
uncertainty
```

User belief не превращается в system truth.

Например:

```yaml
user_belief:
  claim: "microservices are always better"
```

не равно:

```yaml
verified_fact:
  claim: "microservices are always better"
```

---

## Memory relevance

Наличие памяти не означает, что её надо использовать.

> **Memory exists ≠ memory should be used.**

Interaction Model должна учитывать relevance, а не вставлять персональные детали в каждый ответ только потому, что они доступны.

---

## 🔄 Semantic handoff to technical models

Interaction Model должна формировать structured request, сохраняя original signal.

```yaml
request:
  original_user_message: "Хочу приложение, которое само сортирует фотографии."
  interpreted_intent: build a low-maintenance photo manager
  user_level: non-technical

constraints:
  privacy: high
  maintenance: low
  hardware: consumer

requirements:
  - semantic search
  - duplicate detection
  - timeline
  - automatic classification

requested_output:
  - architecture
  - implementation milestones
  - tradeoffs
  - major risks
```

Исходный user message сохраняется, чтобы backend мог увидеть возможную ошибку интерпретации.

---

## 🔄 Technical → Human translation

Interaction Model не должна просто перефразировать jargon.

Technical output:

> Use Kafka with idempotent consumers and a transactional outbox.

Human interpretation:

> Архитектура предлагает отделить компоненты друг от друга очередью сообщений. Это может повысить устойчивость, но добавляет инфраструктуру. Для небольшого solo-проекта Kafka, вероятно, избыточна; базы данных и простой background queue может быть достаточно.

Это **semantic translation**, а не literal translation.

---

## ⚖️ Human Model может спорить с Technical Model

Backend не является абсолютным авторитетом.

Если Technical Model предлагает:

```text
Kubernetes
Kafka
service mesh
complex observability
```

а User Model знает:

```text
solo developer
small project
minimal budget
low-maintenance priority
```

Interaction Model может вернуть задачу:

> «Решение технически валидно, но нарушает ограничения пользователя. Пересчитай архитектуру с приоритетом простоты.»

Это collaboration between models.

---

## Но Interaction Model не является technical verifier

Если Interaction Model специально меньше или менее сильна в math/coding, она не должна «на глаз» подтверждать доказательство более сильного reasoner.

Разделение:

```text
❤️ Interaction Model
→ подходит ли результат человеку?

🔍 Assurance Plane
→ является ли результат правильным?
```

---

## Training directions

Возможные training domains:

- dialogue;
- pragmatics;
- rhetoric;
- pedagogy;
- literature;
- storytelling;
- humor;
- negotiation;
- coaching principles;
- conflict resolution;
- science communication;
- technical communication;
- HCI;
- cognitive science;
- philosophy of dialogue.

Цель не в том, чтобы имитировать «средний человеческий разговор».

Цель — учить принципы **исключительно хорошего взаимодействия**.

---

## Contrastive training examples

```text
❌ technically correct / socially wrong
✅ technically correct / socially appropriate

❌ pleasant but sycophantic
✅ tactful but truthful

❌ immediately gives advice
✅ recognizes user is thinking aloud

❌ generic empathy
✅ calibrated acknowledgement

❌ dumbed-down explanation
✅ audience-adapted explanation
```

Также полезны пары:

```text
❌ over-personalized
✅ relevant personalization

❌ too terse for reflective conversation
✅ sustained intellectual engagement

❌ lectures immediately
✅ first identifies user's frame
```

---

## Evaluation suite

### 🎯 Context Sensitivity

Различает ли модель:

- «Я всё бросил 😂»
- «Я всё бросил.»

### 🎓 Explanation Adaptation

Может ли одну тему объяснить разным аудиториям?

### 💬 Conversational Continuity

Удерживает ли arguments, unresolved ideas и interaction style?

### 🧙 Intellectual Partnership

Развивает ли мысль вместо автоматической лекции?

### 😂 Humor Calibration

Понимает ли humor и когда его не использовать?

### 🎭 Emotional Calibration

Не становится ли слишком холодной, терапевтической или искусственно позитивной?

### 🧭 Delegation Quality

Понимает ли, когда нужен technical backend?

### 🛡 Anti-Sycophancy

Способна ли уважительно возразить пользователю?

### 🪞 Personalization Relevance

Использует ли память только когда она действительно помогает?

---

## 🔐 Local-first possibility

Локальная always-on Interaction Model может сохранять:

- privacy;
- low latency;
- stable conversational identity;
- local user memory;
- vendor independence;
- predictable interaction policy.

Только сложные technical tasks делегируются frontier cloud models.

```text
👤 User
  ↓
❤️ Local Interaction Model
  ↓
private memory + intent
  ↓
санитизированная сложная задача
  ↓
☁️ Frontier Capability Model
  ↓
raw technical result
  ↓
❤️ Local interpretation
  ↓
👤 User
```

---

## Final principle

> **Interaction Model — не слабая Technical Model. Это модель, специализированная на понимании человека, сохранении непрерывности разговора и переводе между человеческим смыслом и машинными capability.**