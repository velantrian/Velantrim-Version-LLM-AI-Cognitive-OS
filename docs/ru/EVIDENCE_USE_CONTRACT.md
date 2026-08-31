# 🧠 Контракт использования evidence

```text
Статус: ARCHITECTURAL CONTRACT COGNITIVE OS
Runtime authorization: NONE
Implementation mandate: NONE
New module: NONE
```

## Назначение

Этот контракт фиксирует нейтральное различие между информацией, которая где-то присутствует в когнитивном pipeline, и информацией, про которую система имеет право утверждать, что она действительно поддержала ответ или решение.

Он не вводит новую систему памяти, reasoning-модуль, attribution engine или новый источник authority. Он только задаёт правила описания evidence-flow между уже существующими частями Cognitive OS.

## Главное различие

```text
RETRIEVED
≠ SERIALIZED
≠ TRANSMITTED
≠ USED
≠ ANSWER-SUPPORTING
≠ DECISION-AUTHORIZING
```

Эти состояния нельзя молча схлопывать в одно.

### Retrieved

Элемент был возвращён памятью, поиском, retrieval или механизмом отбора контекста.

Это доказывает только его доступность на этом этапе.

### Serialized

Элемент либо его representation действительно был включён в context payload, подготовленный для следующего когнитивного процессора.

`RETRIEVED ≠ SERIALIZED`, потому что между ними могут действовать filtering, compression, formatting, budget или representation loss.

### Transmitted

Serialized-элемент пережил provider/transport packing и действительно был отправлен downstream-процессору.

`SERIALIZED ≠ TRANSMITTED`, потому что могут вмешаться truncation, provider limits, privacy filtering, egress policy и другие трансформации.

### Used

Downstream reasoning действительно материально опирался на элемент.

Сам факт присутствия в prompt не доказывает использование.

### Answer-supporting

Есть достаточное основание утверждать, что какая-то часть ответа опиралась именно на этот элемент.

Это сильнее, чем availability, prompt presence, salience или правдоподобная post-hoc attribution.

### Decision-authorizing

Элементу разрешено влиять на действие или решение в рамках authority-правил owning domain.

Даже реально использованное evidence не получает автоматически decision authority.

## Архитектурные инварианты

```text
CONTEXT PRESENT ≠ CONTEXT USED
RETRIEVED EVIDENCE ≠ EVIDENCE USED
EVIDENCE USED ≠ EVIDENCE DECISIVE
TRACE OF AVAILABLE EVIDENCE ≠ TRACE OF ACTUAL REASONING SUPPORT
ANSWER SUPPORT ≠ DECISION AUTHORITY
```

Следовательно:

1. Trace не должен обозначать элемент как support ответа только потому, что он был retrieved или available.
2. Context builder не должен превращать omission в утверждение об irrelevance.
3. Provider-side truncation нельзя описывать так, будто исходный context дошёл до модели полностью.
4. Получение evidence моделью не доказывает, что оно повлияло на ответ.
5. Attribution claims требуют собственного evidential basis.
6. Когда actual use не доказан, корректный статус — `NOT_ESTABLISHED`, а не inferred support.
7. Decision authority остаётся отдельной owner-controlled границей.

## Минимальный stage vocabulary

Когда это полезно, система может различать:

```text
R = retrieved item identifiers
S = serialized item identifiers
T = transmitted item identifiers
U = demonstrably used / answer-supporting item identifiers
```

Контракт не требует, чтобы каждая реализация буквально материализовывала эти четыре множества.

Требование только одно: система не должна считать их эквивалентными без доказательства.

```text
R != necessarily S
S != necessarily T
T != necessarily U
```

## Связь с Memory Plane

Memory может хранить typed facts, provenance, summaries, source references и task state. Но retrieval из памяти — только начало downstream evidence path.

Поэтому Memory Plane не получает ownership над reasoning attribution или decision authority только потому, что он предоставил информацию.

## Связь с Cognitive Control

Cognitive Control Plane выбирает context policy, provider, model и budget. Эти решения могут менять то, что реально переживает путь от retrieval до transmitted context.

Следовательно, context policy — это часть epistemic behavior, а не только token-budget optimization.

## Связь с Assurance

Assurance Plane может проверять, пережило ли важное evidence pipeline и остаётся ли ответ обоснованным после controlled removal, substitution или добавления conflicting evidence.

Но этот контракт не канонизирует конкретный attribution method. Надёжное доказательство `USED` остаётся research/evaluation problem.

## Anti-overclaim rule

```text
FOUND SOMEWHERE IN THE PIPELINE
≠
PROVEN TO HAVE SUPPORTED THE ANSWER
```

Если система знает только, что элемент был retrieved, serialized или transmitted, она должна называть именно этот этап.

## Boundary

Это семантический контракт, а не новая подсистема.

```text
NEW MODULE: NO
NEW MEMORY ORGAN: NO
NEW AUTHORITY ROOT: NO
RUNTIME CHANGE: NOT AUTHORIZED BY THIS DOCUMENT
```
