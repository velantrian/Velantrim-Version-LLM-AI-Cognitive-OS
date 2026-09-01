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
- property graph, RDF, relational representation или иной relationship / relation substrate;
- embeddings, lexical search, graph traversal или другой retrieval method;
- Python или другой implementation language;
- local, cloud или distributed execution;
- текущие agent frameworks, providers и hardware.

Современная технология может быть хорошим способом реализации архитектурной функции. Это не делает её определением самой функции.

```text
TECHNOLOGY ≠ ARCHITECTURE
IMPLEMENTATION PROFILE ≠ COGNITIVE LAW
TECHNOLOGY CHANGE ≠ AUTOMATIC ARCHITECTURE CHANGE
SUBSTRATE-NEUTRAL ≠ UNCHANGEABLE
IMPLEMENTED ≠ WIRED ≠ ENABLED ≠ PRODUCTION AUTHORITY
MODEL OUTPUT ≠ CANON
```

## Substrate Replacement Test

Для любого architecture-level утверждения нужно спросить:

> Если заменить текущую LLM, graph technology, database, retrieval method, programming language, provider или hardware, останется ли утверждение осмысленным когнитивным требованием?

- **YES** → кандидат на архитектурный инвариант, различие или контракт.
- **NO** → скорее всего implementation profile, technology-specific constraint или experiment.

Это классификационная эвристика, а не доказательство универсального закона. Тест не означает, что архитектура неизменна. Новое evidence может оправдать пересмотр архитектурного утверждения. Смысл в том, что одна лишь смена implementation technology не должна незаметно переопределять cognition.

## Связь с CLOS и слоями экосистемы

Velantrim Cognitive Life OS (CLOS) — research-first, substrate-neutral blueprint, который исследует, что когнитивная система должна сохранять независимо от конкретной реализации.

Этот репозиторий Cognitive OS — implementation-oriented research surface для текущей model-era реализации, policy, routing, interaction, assurance и memory patterns. Поэтому примеры LLM/model/provider здесь являются **current implementation profiles**, а не фундаментом, который определяет CLOS.

Связь намеренно слоистая, а не прямая цепочка authority:

```text
1. SUBSTRATE-NEUTRAL COGNITIVE BLUEPRINT
   функции · различия · состояния · переходы · uncertainty · revision · authority
   → CLOS как research blueprint

2. SEMANTIC / COMPOSITION OBLIGATIONS
   project-local инварианты смысла, истории, provenance, declared loss и non-escalation
   → Native Kernel + Mentaury-Kernel в пределах их собственных scope

3. ECOSYSTEM / POLICY COMPOSITION
   ownership, границы взаимодействия и system-level orientation
   → Ecosystem Map + System OS

4. CURRENT IMPLEMENTATION / RESEARCH PROFILES
   models · stores · graphs · retrieval · tools · providers · runtimes
   → текущие owning projects + этот Cognitive OS research surface
```

```text
CLOS ФОРМУЛИРУЕТ / ИССЛЕДУЕТ, КАКИЕ РАЗЛИЧИЯ ДОЛЖНЫ ОСТАВАТЬСЯ ОСМЫСЛЕННЫМИ
        ≠ BINDING IMPLEMENTATION AUTHORITY
CURRENT OWNERS РЕШАЮТ, КАК ИХ ДОМЕН РЕАЛИЗОВАН
```

## Граница authority

Этот документ не переносит ownership и не создаёт runtime authority.

```text
CLOS RESULT ≠ OWNER ADOPTION
RESEARCH ≠ CANON
RESEARCH ≠ IMPLEMENTATION AUTHORIZATION
IMPLEMENTATION ≠ WIRING
WIRED ≠ ENABLED
ENABLED ≠ PRODUCTION AUTHORITY
CURRENT TECHNOLOGY ≠ ARCHITECTURAL AUTHORITY
```

Project-local owners остаются authoritative в своих доменах и для собственного implementation state.