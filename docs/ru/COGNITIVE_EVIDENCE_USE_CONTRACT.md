# 🧠 Cognitive Evidence-Use Contract

```text
Статус: ARCHITECTURAL INVARIANT / COGNITIVE CONTRACT
Runtime authorization: NONE
Implementation mandate: NONE
Новый модуль: НЕТ
Новый memory-орган: НЕТ
Дата: 2026-08-31
```

## Зачем нужен этот контракт

Этот контракт фиксирует substrate-neutral различие для Velantrim Cognitive OS: тот факт, что информация была найдена, представлена, сериализована или передана модели, сам по себе не доказывает, что активный reasoner действительно её использовал или что именно она поддержала итоговый ответ.

Контракт относится к уровню Cognitive OS, потому что задаёт правило для связи context, memory, reasoning и assurance, не навязывая конкретную модель, provider, retriever или memory backend.

## Базовое различие

```text
RETRIEVED
≠ SERIALIZED
≠ TRANSMITTED
≠ USED
≠ ANSWER-SUPPORTING
```

Эквивалентные guardrails:

```text
CONTEXT PRESENT ≠ CONTEXT USED
RETRIEVED EVIDENCE ≠ EVIDENCE USED
AVAILABLE EVIDENCE ≠ REASONING SUPPORT
TRACE OF AVAILABLE EVIDENCE ≠ TRACE OF ACTUAL SUPPORT
```

## Практический смысл

Система может знать, что объект был retrieved, но не знать, попал ли он в model-facing context.

Система может знать, что объект был serialized, но не знать, пережил ли он provider-specific packing или truncation.

Система может знать, что объект был transmitted, но не знать, использовала ли его модель.

Система может знать, что объект был использован, но не знать, был ли он материально значим для итогового вывода.

Поэтому следующий этап не должен молча повышать статус evidence только потому, что предыдущий этап был пройден.

## Минимальная vocabulary для provenance

Если implementation хочет показывать attribution state, полезно различать:

```text
R = retrieved items
S = serialized items
T = transmitted items
U = demonstrably used / answer-supporting items
```

Архитектурное требование не в том, что каждая реализация обязана хранить именно эти четыре множества. Требование в другом:

```text
R MUST NOT BE ASSUMED TO EQUAL S
S MUST NOT BE ASSUMED TO EQUAL T
T MUST NOT BE ASSUMED TO EQUAL U
```

Если стадия не измерялась, её статус должен оставаться unknown / not established, а не выводиться автоматически из предыдущей стадии.

## Связь с существующими planes

### 💾 Memory Plane

Memory/retrieval может доказать availability или selection информации, но не reasoning use.

### 🧭 Cognitive Control Plane

Context assembly и routing могут решить, что следует передать reasoner, но не доказывают, что reasoner на это опирался.

### 🧠 Capability Plane

Модель может получить evidence и всё равно проигнорировать, неверно понять или перекрыть его другим знанием.

### 🔍 Assurance Plane

Assurance должен проверять, оправдано ли attribution-утверждение, и не считать retrieval или наличие в prompt доказательством semantic support.

## Семантика trace

Reasoning trace, receipt или audit record должен называться в соответствии с тем, что он реально может доказать.

Если trace содержит все retrieved fact IDs, безопасная семантика:

```text
FACTS AVAILABLE TO THE ANSWER PATH
```

а не автоматически:

```text
FACTS THAT SUPPORTED THE ANSWER
```

Для более сильного утверждения нужен дополнительный attribution contract или measurement.

## Lossy context boundary

Context packing, compression, summarization, provider limits и truncation могут создать дополнительную потерю уже после retrieval.

Поэтому:

```text
RETRIEVED ≠ ACTUALLY PRESENT AFTER PACKING
```

Truncation marker, warning или receipt могут сделать потерю видимой, но сами по себе не доказывают, какой именно пропущенный факт изменил бы ответ.

## Чего этот контракт не утверждает

Документ не утверждает, что:

- уже существует универсальный causal-attribution algorithm;
- attention weights доказывают semantic use;
- self-report модели доказывает, что именно она использовала;
- каждому ответу нужен causal attribution по каждому факту;
- нужно сохранять полный chain-of-thought;
- требуется новый attribution service или memory subsystem.

Это implementation и research questions.

## Research boundary

Само различие достаточно зрелое, чтобы жить как Cognitive OS invariant.

Оставшаяся research-проблема уже уже:

```text
HOW DO WE RELIABLY ESTABLISH U?
```

Кандидаты для исследования: bounded counterfactual removal, perturbation, discriminating fixtures и task-specific attribution checks. Ни один из них здесь не объявляется универсальным механизмом.

## Anti-overclaim rule

```text
IF ONLY RETRIEVAL IS OBSERVED,
CLAIM RETRIEVAL.

IF ONLY SERIALIZATION IS OBSERVED,
CLAIM SERIALIZATION.

IF ONLY TRANSMISSION IS OBSERVED,
CLAIM TRANSMISSION.

DO NOT CLAIM SEMANTIC USE OR ANSWER SUPPORT
WITHOUT ADDITIONAL EVIDENCE.
```

Это epistemic reporting contract, а не новый runtime authority.