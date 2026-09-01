🌐 **Язык / Language:** [🇬🇧 English](../SUBSTRATE_NEUTRAL_BOUNDARY.md) · 🇷🇺 **Русский**

# ⚗️ Граница технологически нейтральной архитектуры

## Зачем это нужно

Velantrim отделяет **когнитивную архитектуру** от технологий, которыми она реализуется сегодня.

Архитектура описывает устойчивые когнитивные функции, различия, переходы состояний, правила пересмотра, работу с неопределённостью и границы полномочий. Она не определяется конкретной LLM, graph-реализацией, базой данных, vector index, языком программирования, provider, agent framework или поколением hardware.

```text
COGNITIVE FUNCTION
        ↓
ARCHITECTURAL REQUIREMENT
        ↓
DISTINCTIONS / STATE / TRANSITIONS / CONSTRAINTS
        ↓
VALIDATION QUESTION
        ↓
ONLY THEN: IMPLEMENTATION OPTIONS
```

## Архитектура и implementation profile

Примеры архитектурных различий:

- source ≠ representation;
- claim ≠ evidence;
- evidence ≠ belief;
- retrieval ≠ semantic use;
- semantic use ≠ answer support;
- capability ≠ permission;
- memory ≠ authority;
- UNKNOWN ≠ false;
- simulated ≠ executed;
- revision должна сохранять релевантную историю и различие current/historical.

Примеры заменяемых implementation choices:

- LLM или другой cognitive processor;
- SQLite, PostgreSQL, файлы или другой durable store;
- property graph, RDF, relational representation или иной relational substrate;
- embeddings, lexical search, graph traversal или другой retrieval method;
- Python или другой implementation language;
- local, cloud или distributed execution;
- текущие agent frameworks, providers и hardware.

Современная технология может быть хорошим способом реализации архитектурной функции. Это не делает её определением самой функции.

```text
TECHNOLOGY ≠ ARCHITECTURE
IMPLEMENTATION PROFILE ≠ COGNITIVE LAW
TECHNOLOGY CHANGE ≠ AUTOMATIC ARCHITECTURE CHANGE
```

## Substrate Replacement Test

Для любого architecture-level утверждения нужно спросить:

> Если заменить текущую LLM, graph technology, database, retrieval method, programming language, provider или hardware, останется ли утверждение осмысленным когнитивным требованием?

- **YES** → кандидат на архитектурный инвариант, различие или контракт.
- **NO** → скорее всего implementation profile, technology-specific constraint или experiment.

Этот тест не означает, что архитектура неизменна. Новое evidence может оправдать её пересмотр. Смысл в том, что одна лишь смена implementation technology не должна незаметно переопределять cognition.

## Связь с CLOS

Velantrim Cognitive Life OS (CLOS) — research-first, substrate-neutral blueprint, который исследует, что когнитивная система должна сохранять независимо от конкретной реализации.

Этот репозиторий Cognitive OS — implementation-oriented research surface для текущей model-era реализации, policy, routing, interaction, assurance и memory patterns. Поэтому примеры LLM/model/provider здесь являются **current implementation profiles**, а не фундаментом, который ограничивает CLOS.

```text
CLOS / substrate-neutral blueprint
        ↓ задаёт смысл и необходимые различия
Cognitive OS / current research + policy surface
        ↓ исследует способы реализации
current models · stores · graphs · retrieval · tools · runtimes
```

## Граница authority

Этот документ не переносит ownership и не создаёт runtime authority.

```text
CLOS RESULT ≠ OWNER ADOPTION
RESEARCH ≠ IMPLEMENTATION AUTHORIZATION
IMPLEMENTATION ≠ RUNTIME AUTHORIZATION
CURRENT TECHNOLOGY ≠ ARCHITECTURAL AUTHORITY
```

Project-local owners остаются authoritative в своих доменах и для собственного implementation state.