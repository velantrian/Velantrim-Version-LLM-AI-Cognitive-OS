# 🧠 Evidence-Use Contract

```text
Статус: COGNITIVE-OS ARCHITECTURAL CONTRACT
Runtime authorization: NONE
Implementation mandate: NONE
Новый модуль: НЕТ
Дата: 2026-08-31
```

## Зачем нужен этот контракт

Этот контракт фиксирует substrate-neutral различие между информацией, которая существует где-то в cognitive pipeline, и информацией, про которую система вправе утверждать, что она действительно поддержала ответ или решение.

Он не вводит новый memory system, reasoning module, attribution engine или runtime authority. Он задаёт правило того, как Cognitive OS должен описывать движение evidence через уже существующие компоненты.

## Базовое различие

```text
RETRIEVED
≠ SERIALIZED
≠ TRANSMITTED
≠ USED
≠ ANSWER-SUPPORTING
≠ DECISION-AUTHORIZING
```

Эти состояния нельзя молча сливать друг с другом.

### Retrieved
Объект был возвращён memory/retrieval/search/context-selection процессом. Это доказывает только его доступность на этой стадии.

### Serialized
Объект или его representation реально попали в context payload для downstream cognitive processor.

`RETRIEVED ≠ SERIALIZED`, потому что между ними могут быть filtering, compression, formatting, budgeting или representation loss.

### Transmitted
Serialized item пережил provider/transport packing и реально был отправлен downstream processor.

`SERIALIZED ≠ TRANSMITTED`, потому что могут вмешаться truncation, provider limits, transport policy, privacy filtering или другие egress transformations.

### Used
Downstream reasoning process материально опирался на этот объект. Одно присутствие в prompt не доказывает use.

### Answer-supporting
Есть достаточное evidence, чтобы связать часть итогового ответа с этим объектом. Это сильнее, чем availability, prompt presence, attention-like salience или post-hoc plausibility.

### Decision-authorizing
Объекту разрешено влиять на действие или решение согласно authority rules owning domain. Даже реально поддерживающее ответ evidence не получает decision authority автоматически.

## Архитектурные инварианты

```text
CONTEXT PRESENT ≠ CONTEXT USED
RETRIEVED EVIDENCE ≠ EVIDENCE USED
EVIDENCE USED ≠ EVIDENCE DECISIVE
TRACE OF AVAILABLE EVIDENCE ≠ TRACE OF ACTUAL REASONING SUPPORT
ANSWER SUPPORT ≠ DECISION AUTHORITY
```

Следовательно:

1. Trace не должен называть объект answer support только потому, что он был retrieved или available.
2. Context builder не должен считать omitted content нерелевантным только потому, что он не был serialized.
3. Provider-side truncation/transformation нельзя считать эквивалентом доставки исходного context в неизменном виде.
4. Получение evidence моделью не доказывает, что evidence повлияло на ответ.
5. Attribution claims требуют собственного evidential basis.
6. Если actual use не установлен, правильный статус — `NOT_ESTABLISHED`, а не inferred support.
7. Decision authority остаётся отдельной owner-controlled boundary.

## Минимальная stage vocabulary

При необходимости implementation может различать:

```text
R = retrieved item identifiers
S = serialized item identifiers
T = transmitted item identifiers
U = demonstrably used / answer-supporting item identifiers
```

Контракт не требует, чтобы каждая реализация физически хранила именно эти четыре множества. Он требует не считать их автоматически равными.

```text
R != necessarily S
S != necessarily T
T != necessarily U
```

## Связь с существующими planes

### 💾 Memory Plane
Memory может хранить typed facts, provenance, summaries, source references и task state. Retrieval из памяти — только начало downstream evidence path. Сам факт выдачи информации не даёт Memory Plane reasoning attribution или decision authority.

### 🧭 Cognitive Control Plane
Cognitive Control может выбирать context policy, provider, model и budget. Эти решения влияют на то, что переживёт путь от retrieval до transmitted context. Context policy поэтому является частью epistemic behavior, а не только token-budget optimization.

### 🧠 Capability Plane
Модель может получить evidence и всё равно проигнорировать, неверно понять или перекрыть его другим знанием.

### 🔍 Assurance Plane
Assurance может проверять, сохранилось ли важное evidence в pipeline и остаётся ли ответ обоснованным при controlled removal, substitution или conflicting evidence. Этот контракт не канонизирует конкретный attribution method.

## Research boundary

Само различие достаточно зрелое, чтобы быть architectural invariant.

Оставшаяся research-проблема уже уже:

```text
HOW DO WE RELIABLY ESTABLISH U?
```

Кандидаты: bounded counterfactual removal, perturbation, discriminating fixtures и task-specific attribution checks. Ни один из них здесь не объявляется универсальным механизмом.

## Anti-overclaim rule

```text
FOUND SOMEWHERE IN THE PIPELINE
≠
PROVEN TO HAVE SUPPORTED THE ANSWER
```

Если система знает только, что item был retrieved, serialized или transmitted, она должна заявлять именно эту стадию.

## Boundary

```text
NEW MODULE: NO
NEW MEMORY ORGAN: NO
NEW AUTHORITY ROOT: NO
RUNTIME CHANGE: NOT AUTHORIZED BY THIS DOCUMENT
```
