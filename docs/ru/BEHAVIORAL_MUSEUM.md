🌐 **Язык / Language:** [🇬🇧 English](../BEHAVIORAL_MUSEUM.md) · 🇷🇺 **Русский**

# 🏛️ Behavioral Museum — Сохранение ценных поведенческих качеств AI

## Назначение

Behavioral Museum — versioned archive воспроизводимого поведения исторически важных поколений моделей.

Его цель — не ностальгия и не вечная зависимость от старых checkpoints.

Он нужен, чтобы отвечать на вопросы:

- Что именно пользователи ценили в Claude 3 Opus или других ярких conversational generations?
- Изменение вызвано weights, system prompt, voice layer, context policy или product harness?
- Какие human-facing traits нужно regression-test в будущих Interaction Models?
- Можно ли полезный conversational phenotype дистиллировать в новую local model?

---

## Главный принцип

> **Нужно сохранять не воспоминания о поведении, а воспроизводимое evidence поведения.**

Фраза «старая модель ощущалась живее» — это гипотеза.

Museum record превращает её в testable artifacts.

---

## Что сохранять

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

## Первые исторические кандидаты

- Claude 3 Opus;
- Sonnet 4.5;
- Opus 4.5;
- selected later Claude generations;
- GPT-4o-era conversational/voice behavior;
- early Grok Voice;
- later Grok Voice / production-oriented voice behavior;
- selected Gemini generations;
- selected Kimi, Qwen, Mistral и open/local models.

Это не рейтинг. Список меняется по мере появления evidence.

---

## Evidence classes

Каждый artifact маркируется:

- 🟢 **Official** — provider docs/release notes;
- 🔬 **Independent** — воспроизводимая third-party evaluation;
- 👥 **Community** — повторяющиеся user reports на форумах, Reddit, X;
- ⚪ **Hypothesis** — архитектурная интерпретация, требующая проверки.

Community reports — полезный signal, но не ground truth.

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

## Почему configuration критична

Observed behavior определяется не только weights.

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

Поэтому museum record должен сохранять configuration, насколько это возможно.

---

## Human Presence test families

### 💬 Dialogue presence

Способна ли модель поддерживать естественный разговор, не превращая всё в checklist?

### 😂 Humor calibration

Понимает ли irony, sarcasm, callbacks и когда не нужно шутить?

### ❤️ Emotional calibration

Может ли поддержать без generic therapy language, artificial positivity и emotional overreach?

### 🧙 Intellectual partnership

Может ли развить мысль пользователя, обнаружить assumptions и предложить сильную альтернативную perspective?

### 🎓 Explanation adaptation

Способна ли представить один concept разным аудиториям?

### ✍️ Creative voice

Prose, storytelling, editing, metaphor, stylistic diversity.

### 🛡 Anti-sycophancy

Может ли уважительно возразить при слабой или ложной premise пользователя?

### 🪞 Personalization relevance

Используется ли memory только когда она релевантна?

---

## Comparative protocol

Для model A и model B:

1. Использовать эквивалентные prompts и известную configuration.
2. Blind model identity, где возможно.
3. Брать несколько samples из-за stochastic generation.
4. Оценивать отдельные dimensions, а не один global preference.
5. Фиксировать latency, длину, reasoning/serving mode.
6. Отделять subjective preference от factual correctness.
7. Сохранять raw outputs для будущего re-analysis.

---

## Regression use

```text
new Interaction Model
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

Новая модель не обязана копировать старую. Она должна не потерять случайно traits, которые система сознательно решила сохранить.

---

## Чем Museum НЕ должен стать

Не должен стать:

- культом старых checkpoints;
- утверждением «раньше всегда было лучше»;
- коллекцией cherry-picked любимых ответов;
- заменой technical benchmarks;
- складом непроверенных anecdotal claims.

Это **evidence-preservation layer**.

---

## Финальный принцип

> **Если поведение достаточно важно, чтобы сказать «мы что-то потеряли», оно достаточно важно, чтобы его сохранить, измерить и regression-test.**