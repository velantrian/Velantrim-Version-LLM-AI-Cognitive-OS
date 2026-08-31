# 🧠 Cognitive Evidence-Use Contract

```text
Status: ARCHITECTURAL INVARIANT / COGNITIVE CONTRACT
Runtime authorization: NONE
Implementation mandate: NONE
New module: NO
New memory organ: NO
Date: 2026-08-31
```

## Purpose

This contract defines a substrate-neutral distinction for Velantrim Cognitive OS: information being found, represented, serialized or transmitted does not by itself establish that the active reasoner actually used that information, that it supported the final answer, or that it is permitted to authorize a downstream decision.

The contract belongs at the Cognitive OS level because it constrains how context, memory, reasoning and assurance may describe their relationship without requiring any particular model, provider, retriever or memory backend.

## Core distinction

```text
RETRIEVED
≠ SERIALIZED
≠ TRANSMITTED
≠ USED
≠ ANSWER-SUPPORTING
≠ DECISION-AUTHORIZING
```

Equivalent guardrails:

```text
CONTEXT PRESENT ≠ CONTEXT USED
RETRIEVED EVIDENCE ≠ EVIDENCE USED
AVAILABLE EVIDENCE ≠ REASONING SUPPORT
TRACE OF AVAILABLE EVIDENCE ≠ TRACE OF ACTUAL SUPPORT
ANSWER SUPPORT ≠ DECISION AUTHORITY
```

## Operational meaning

A system may know that an item was retrieved without knowing that it was serialized into the model-facing context.

A system may know that an item was serialized without knowing that provider-specific packing or truncation transmitted it intact.

A system may know that an item was transmitted without knowing that the model used it.

A system may know that an item was used without knowing that it materially supported the final conclusion.

A system may know that an item supported an answer without that item being permitted to control a decision or action. Decision authority remains an owner-controlled boundary.

Therefore later stages must not silently promote evidence from an earlier stage into a stronger attribution or authority status.

## Minimum stage vocabulary

When an implementation chooses to expose attribution state, the following conceptual sets are useful:

```text
R = retrieved items
S = serialized items
T = transmitted items
U = demonstrably used items
A = demonstrably answer-supporting items
```

The architectural rule is not that every implementation must materialize these exact sets. The rule is:

```text
R MUST NOT BE ASSUMED TO EQUAL S
S MUST NOT BE ASSUMED TO EQUAL T
T MUST NOT BE ASSUMED TO EQUAL U
U MUST NOT BE ASSUMED TO EQUAL A
```

Decision authorization is deliberately not represented as another membership set here. It is a separate policy and authority gate owned by the relevant domain.

If a stage is not measured, its status should remain unknown / not established rather than being inferred from an earlier stage.

## Relationship to existing planes

### 💾 Memory Plane

Memory/retrieval may establish that information was available or selected. It does not establish reasoning use.

### 🧭 Cognitive Control Plane

Context assembly and routing may decide what should be sent to a reasoner. They do not establish that the reasoner relied on it.

### 🧠 Capability Plane

A model may receive evidence and still ignore, misunderstand or override it.

### 🔍 Assurance Plane

Assurance may verify whether attribution claims are justified. It must not treat mere retrieval or prompt presence as proof of semantic support, and it must not turn answer support into decision authority.

## Trace semantics

A reasoning trace, receipt or audit record must distinguish what it can actually prove.

If a trace records all retrieved fact IDs, the safe semantic interpretation is:

```text
FACTS AVAILABLE TO THE ANSWER PATH
```

not automatically:

```text
FACTS THAT SUPPORTED THE ANSWER
```

The stronger wording requires an additional attribution contract or measurement.

## Lossy context boundary

Context packing, compression, summarization, provider limits and truncation can create additional loss after retrieval.

Therefore:

```text
RETRIEVED ≠ ACTUALLY PRESENT AFTER PACKING
```

and a truncation marker, warning or receipt may make loss visible without proving which omitted item would have changed the answer.

## What this contract does not claim

This document does not claim that:

- a universal causal-attribution algorithm already exists;
- attention weights prove semantic use;
- model self-report proves what evidence was used;
- every answer needs per-fact causal attribution;
- every system must persist full chain-of-thought;
- a new attribution service or memory subsystem is required;
- answer-supporting evidence automatically has decision authority.

Those are implementation, research or owner-policy questions.

## Research boundary

The architectural distinction is considered stable enough to keep as a Cognitive OS invariant.

The unresolved research problem is narrower:

```text
HOW DO WE RELIABLY ESTABLISH U AND A?
```

That is: how do we establish actual semantic use, and separately how do we establish that an item materially supported the answer?

Possible research methods include bounded counterfactual removal, perturbation, discriminating fixtures and task-specific attribution checks. None is promoted here as a universal mechanism.

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

DO NOT CLAIM DECISION AUTHORITY
FROM ANSWER SUPPORT ALONE.
```

This is an epistemic reporting contract, not a new runtime authority.
