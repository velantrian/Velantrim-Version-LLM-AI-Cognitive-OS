🌐 **Язык / Language:** [🇬🇧 English](../ANTI_DEGRADATION.md) · 🇷🇺 **Русский**

# 🛡️ Anti-Degradation Architecture

## 1. Деградация многомерна

В Velantrim слово **«деградация»** не обозначает один туманный эффект. Это несколько различных классов проблем, которые нужно измерять и устранять независимо.

```text
                    DEGRADATION
                         │
       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
 🧠 Cognitive       💬 Conversational    🔄 Temporal
 reasoning drift     потеря нюанса        context rot
 hallucinations      style flattening     summary drift
 overthinking        sycophancy           memory noise

       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
 🤖 Agent           💾 Memory           🏭 Model/Product
 loops              stale retrieval     behavioral regression
 goal drift         false memory        checkpoint personality shift
 tool misuse        belief/fact mix     provider optimization shift
```

Система должна уметь локализовать каждый класс, не сводя всё к «модель стала хуже».

---

## 2. 🌀 Context rot

Большой context window полезен, но сам по себе не гарантирует эффективного reasoning.

Длинная trajectory накапливает:

- stale plans;
- старые assumptions;
- tool outputs;
- failed branches;
- summaries of summaries;
- duplicated evidence;
- contradictory instructions;
- irrelevant history;
- reasoning traces, которые уже не соответствуют текущему state.

Поэтому:

> **Maximum context ≠ effective context.**

Предпочтительный active context:

```text
Original Objective
+ Current State
+ Relevant Memory
+ Recent Trajectory
+ Required Evidence
```

а не весь transcript.

---

## 3. 🎯 Goal drift

Agent может постепенно начать оптимизировать **не тот objective**, который поставил пользователь.

Защита:

```yaml
task_invariants:
  original_goal: ...
  hard_constraints: [...]
  user_non_goals: [...]
  acceptance_criteria: [...]
  safety_boundaries: [...]
```

Working plan можно менять.

Task invariants должны требовать явного пересмотра, а не молча переписываться внутри очередного reasoning turn.

---

## 4. 🧠 Overthinking

Больше reasoning compute не обязательно означает лучший результат.

```text
простая задача
   ↓
очень высокий reasoning budget
   ↓
лишние гипотезы
   ↓
лишние tools
   ↓
больше context
   ↓
больше возможностей ошибиться
```

Dynamic policy:

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

Если `High` два раза не помог, следующий шаг может быть:

- fresh context;
- другая model family;
- новая decomposition;
- другая reasoning strategy;
- stronger verifier;

а не автоматический `Max`.

---

## 5. ♻️ Agent loops

Сигналы циклической деградации:

- повторные tool calls с одинаковыми аргументами;
- повторные правки одного и того же участка;
- колебание между двумя планами;
- context растёт, а измеримого прогресса нет;
- модель всё чаще оправдывает себя вместо проверки;
- retry count растёт, verification остаётся red;
- одна и та же ошибка переформулируется, но не устраняется.

Рекомендуемая реакция:

```text
loop detected
    ↓
STOP current trajectory
    ↓
extract verified evidence + current state
    ↓
restore invariants
    ↓
compact / fresh context
    ↓
replan
    ↓
possibly switch model family
```

---

## 6. 🧠 Single-model monoculture

Если одна модель:

1. понимает задачу;
2. строит план;
3. пишет решение;
4. проверяет решение;
5. объясняет результат;

то её скрытая исходная ошибка может пройти через всю цепочку.

Предпочтительный паттерн:

```text
Generator A
    ↓
Reviewer B
    ↓
Deterministic checks
    ↓
Integrator C
```

Особенно важна **частичная независимость ошибок** между разными model families и deterministic tools.

---

## 7. 💾 Memory degradation

Проблемы памяти:

- stale information;
- irrelevant retrieval;
- summary drift;
- пользовательское мнение сохранено как objective fact;
- duplicate memories;
- provenance loss;
- confidence inflation;
- отсутствие supersession;
- неясно, какая запись является актуальной.

Пример typed memory:

```yaml
memory:
  type: preference|belief|fact|task_state|episode
  content: ...
  source: ...
  created_at: ...
  confidence: ...
  verified: true|false
  supersedes: ...
```

Ключевое правило:

> **Memory exists ≠ memory should be used.**

Retrieval требует отдельной relevance policy.

---

## 8. 🤝 Sycophancy

Interaction Model нельзя оптимизировать только на approval.

Опасная цепочка:

```text
user satisfaction
      ↓
agreement
      ↓
flattery
      ↓
confirmation of bad assumptions
```

Предпочтительный objective:

```text
truth
+ understanding
+ usefulness
+ tact
+ calibrated disagreement
+ intellectual honesty
- sycophancy
- manipulation
- false intimacy
```

Иногда правильный человеческий ответ — спокойно сказать:

> «Я понимаю твою логику, но здесь вывод, похоже, неверен.»

---

## 9. 🏭 Model-update regression

Новый checkpoint может одновременно улучшить одни оси и ухудшить другие.

Поэтому upgrades должны допускаться **по роли**.

```text
New model:
+ coding +15%
+ tool reliability +10%
- human presence -20%

Decision:
✅ replace Coder
❌ do not replace Interaction Model
```

Это центральный механизм защиты от product-level personality regression.

---

## 10. 🐤 Canary deployment

Новая модель не должна сразу получать 100% задач.

```text
5%
 ↓ evaluate
20%
 ↓ evaluate
50%
 ↓ evaluate
100% only if role-specific evidence is green
```

Отслеживать:

- completion rate;
- verification failures;
- retries;
- cost/task;
- latency;
- context growth;
- user corrections;
- tool failures;
- behavioral changes;
- refusal / premature stop rate;
- semantic-handoff failures.

---

## 11. Automatic degradation detection

Возможная telemetry:

```text
retry_count ↑
context_size ↑
verification_failures ↑
user_corrections ↑
repeated_tool_calls ↑
progress_rate ↓
confidence/evidence mismatch ↑
summary divergence ↑
```

Threshold response:

```text
STOP
 ↓
compact state
 ↓
restore task invariants
 ↓
replan
 ↓
switch strategy/model if needed
 ↓
verify independently
```

---

## 12. Summary provenance

Summary не может становиться неоспоримой истиной.

```yaml
summary:
  content: ...
  source_refs: [...]
  created_by: ...
  confidence: 0.0-1.0
  timestamp: ...
```

При конфликте система должна вернуться к primary evidence.

---

## 13. Behavioral degradation

Отдельный класс — изменение human-facing поведения после обновления модели или harness.

Возможные признаки:

- ответы стали существенно короче без запроса пользователя;
- юмор стал шаблонным или исчез;
- модель чаще уходит в generic empathy;
- creative writing стало менее разнообразным;
- интеллектуальный диалог превратился в checklist;
- возросла sycophancy;
- чрезмерное policy language вытесняет естественную коммуникацию.

Это не означает, что новая модель «хуже вообще». Это означает, что **Interaction role нуждается в собственной evaluation suite**.

---

## 14. Long-horizon degradation

Чем дольше agent работает, тем важнее external state.

```text
trajectory length ↑
     ↓
context pressure ↑
     ↓
summary dependence ↑
     ↓
error propagation risk ↑
```

Защита:

- explicit task state;
- immutable invariants;
- checkpoints;
- verified milestones;
- restartable execution;
- independent review at boundaries;
- bounded autonomy.

---

## 15. Основные anti-degradation законы

1. Хранить original objective вне model context.
2. Critical constraints явные и immutable by default.
3. Memory отделена от transcript.
4. Belief отделено от fact.
5. Interaction quality отделено от technical quality.
6. Generation отделена от verification.
7. Strategy меняется раньше, чем бесконечно растёт compute.
8. Model upgrades допускаются по ролям.
9. Loops обнаруживаются по telemetry.
10. Behavioral baselines сохраняются между поколениями.
11. Summary имеет provenance.
12. Неудачная trajectory должна быть restartable.
13. Система должна уметь признать unresolved state.
14. Пользовательские preferences не должны превращаться в epistemic authority.
15. Чем выше риск задачи, тем выше требование к независимости verifier.

---

## 16. Финальный принцип

> **Система должна оставаться когерентной даже тогда, когда отдельная модель запуталась, изменила поведение, была обновлена или полностью исчезла.**