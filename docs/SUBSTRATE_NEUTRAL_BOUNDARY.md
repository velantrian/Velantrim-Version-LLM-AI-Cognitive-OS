🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](ru/SUBSTRATE_NEUTRAL_BOUNDARY.md)

# ⚗️ Substrate-Neutral Architecture Boundary

## Purpose

Velantrim distinguishes the **cognitive architecture** from the technologies currently used to realize it.

The architecture describes durable cognitive functions, distinctions, state transitions, revision obligations, uncertainty handling and authority boundaries. It is not defined by any particular LLM, graph implementation, database, vector index, programming language, provider, agent framework or hardware generation.

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

## Architecture vs implementation profile

Examples of architecture-level concerns:

- source ≠ representation;
- claim ≠ evidence;
- evidence ≠ belief;
- retrieval ≠ semantic use;
- semantic use ≠ answer support;
- capability ≠ permission;
- memory ≠ authority;
- UNKNOWN ≠ false;
- simulated ≠ executed;
- revision must preserve relevant history and currentness distinctions.

Examples of replaceable implementation choices:

- LLM or other cognitive processor;
- SQLite, PostgreSQL, files or another durable store;
- property graph, RDF, relational representation or another relationship substrate;
- embeddings, lexical search, graph traversal or another retrieval method;
- Python or another implementation language;
- local, cloud or distributed execution;
- current agent frameworks, providers and hardware.

A current technology may be a useful implementation of an architectural function. It does not thereby become the definition of that function.

```text
TECHNOLOGY ≠ ARCHITECTURE
IMPLEMENTATION PROFILE ≠ COGNITIVE LAW
TECHNOLOGY CHANGE ≠ AUTOMATIC ARCHITECTURE CHANGE
SUBSTRATE-NEUTRAL ≠ UNCHANGEABLE
IMPLEMENTED ≠ WIRED ≠ ENABLED ≠ PRODUCTION AUTHORITY
MODEL OUTPUT ≠ CANON
```

## Substrate Replacement Test

For an architecture-level statement, ask:

> If the current LLM, graph technology, database, retrieval method, programming language, provider or hardware were replaced, would the statement still describe a meaningful cognitive requirement?

- **YES** → candidate architectural invariant, distinction or contract.
- **NO** → probably an implementation profile, technology-specific constraint or experiment.

This is a classification heuristic, not proof of a universal law. It does not mean the architecture is immutable. New evidence can justify revising an architectural claim. The point is that implementation churn alone must not silently redefine cognition.

## Relationship to CLOS and ecosystem layers

Velantrim Cognitive Life OS (CLOS) is the research-first, substrate-neutral blueprint that asks what a cognitive system must preserve independently of a particular implementation.

This Cognitive OS repository is an implementation-oriented research surface for current model-era realization, policy, routing, interaction, assurance and memory patterns. Its LLM/model/provider examples are therefore **current implementation profiles**, not foundations that define CLOS.

The relationship is intentionally layered rather than a direct authority chain:

```text
1. SUBSTRATE-NEUTRAL COGNITIVE BLUEPRINT
   functions · distinctions · states · transitions · uncertainty · revision · authority
   → CLOS as research blueprint

2. SEMANTIC / COMPOSITION OBLIGATIONS
   project-local invariants of meaning, history, provenance, declared loss and non-escalation
   → Native Kernel + Mentaury-Kernel within their own scopes

3. ECOSYSTEM / POLICY COMPOSITION
   ownership, interaction boundaries and system-level orientation
   → Ecosystem Map + System OS

4. CURRENT IMPLEMENTATION / RESEARCH PROFILES
   models · stores · graphs · retrieval · tools · providers · runtimes
   → current owning projects + this Cognitive OS research surface
```

```text
CLOS STATES / ASKS WHAT DISTINCTIONS MUST REMAIN MEANINGFUL
        ≠ BINDING IMPLEMENTATION AUTHORITY
CURRENT OWNERS DECIDE HOW THEIR DOMAIN IS REALIZED
```

## Authority boundary

This document does not transfer ownership or runtime authority.

```text
CLOS RESULT ≠ OWNER ADOPTION
RESEARCH ≠ CANON
RESEARCH ≠ IMPLEMENTATION AUTHORIZATION
IMPLEMENTATION ≠ WIRING
WIRED ≠ ENABLED
ENABLED ≠ PRODUCTION AUTHORITY
CURRENT TECHNOLOGY ≠ ARCHITECTURAL AUTHORITY
```

Project-local owners remain authoritative for their own domains and implementation state.