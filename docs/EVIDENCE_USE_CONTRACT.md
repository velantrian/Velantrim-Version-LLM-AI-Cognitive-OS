# 🧠 Evidence-Use Contract

```text
Status: COGNITIVE-OS ARCHITECTURAL CONTRACT
Runtime authorization: NONE
Implementation mandate: NONE
New module: NONE
Date: 2026-08-31
```

## Purpose

This contract defines a substrate-neutral distinction between information that exists somewhere in the cognitive pipeline and information that can legitimately be claimed to have supported an answer or decision.

It does not introduce a new memory system, reasoning module, attribution engine, or runtime authority. It constrains how Cognitive OS describes evidence flow across existing components.

## Core distinction

```text
RETRIEVED
≠ SERIALIZED
≠ TRANSMITTED
≠ USED
≠ ANSWER-SUPPORTING
≠ DECISION-AUTHORIZING
```

These states must not be silently collapsed.

### Retrieved
The item was returned by a memory, retrieval, search, or context-selection process. This proves availability at that stage only.

### Serialized
The item, or a representation of it, was actually included in the context payload prepared for a downstream cognitive processor.

`RETRIEVED ≠ SERIALIZED` because filtering, compression, formatting, budgeting, or representation loss may intervene.

### Transmitted
The serialized item survived provider- or transport-specific packing and was actually sent to the downstream processor.

`SERIALIZED ≠ TRANSMITTED` because truncation, provider limits, transport policy, privacy filtering, or other egress transformations may intervene.

### Used
The downstream reasoning process materially relied on the item. Mere prompt presence does not establish use.

### Answer-supporting
There is sufficient evidence to attribute some part of the produced answer to the item. This is stronger than availability, prompt presence, attention-like salience, or post-hoc plausibility.

### Decision-authorizing
The item is permitted to influence an action or decision under the owning domain's authority rules. Even evidence that genuinely supports an answer does not automatically gain decision authority.

## Architectural invariants

```text
CONTEXT PRESENT ≠ CONTEXT USED
RETRIEVED EVIDENCE ≠ EVIDENCE USED
EVIDENCE USED ≠ EVIDENCE DECISIVE
TRACE OF AVAILABLE EVIDENCE ≠ TRACE OF ACTUAL REASONING SUPPORT
ANSWER SUPPORT ≠ DECISION AUTHORITY
```

Therefore:

1. A trace must not label an item as answer support merely because it was retrieved or available.
2. A context builder must not imply that omitted content was irrelevant merely because it was not serialized.
3. Provider-side truncation or transformation must not be treated as if the original context reached the model intact.
4. A model receiving evidence does not prove that the evidence affected its answer.
5. Attribution claims require their own evidential basis.
6. When actual use cannot be established, the correct status is `NOT_ESTABLISHED`, not inferred support.
7. Decision authority remains a separate owner-controlled boundary.

## Minimal stage vocabulary

A system may record these stages explicitly when useful:

```text
R = retrieved item identifiers
S = serialized item identifiers
T = transmitted item identifiers
U = demonstrably used item identifiers
A = demonstrably answer-supporting item identifiers
```

The contract does not require every implementation to materialize these exact sets. It requires only that the system not falsely treat them as equivalent.

```text
R != necessarily S
S != necessarily T
T != necessarily U
U != necessarily A
```

## Relationship to existing planes

### 💾 Memory Plane
Memory may preserve typed facts, provenance, summaries, source references and task state. Retrieval from that memory is only the beginning of a downstream evidence path. The Memory Plane therefore owns neither reasoning attribution nor decision authority merely because it supplied the information.

### 🧭 Cognitive Control Plane
The Cognitive Control Plane may choose context policies, providers, models and budgets. Those choices can alter what survives from retrieval into transmitted context. Context policy is therefore part of epistemic behavior, not merely a token-budget optimization.

### 🧠 Capability Plane
A model may receive evidence and still ignore, misunderstand or override it.

### 🔍 Assurance Plane
The Assurance Plane may test whether important evidence survived the pipeline and whether an answer remains justified under controlled removals, substitutions or conflicting evidence. No particular attribution method is canonized by this contract.

## Research boundary

The distinction itself is stable enough to be an architectural invariant.

The unresolved research problem is narrower:

```text
HOW DO WE RELIABLY ESTABLISH U AND A?
```

Candidate methods include bounded counterfactual removal, perturbation, discriminating fixtures and task-specific attribution checks. None is promoted here as a universal mechanism.

## Anti-overclaim rule

```text
FOUND SOMEWHERE IN THE PIPELINE
≠
PROVEN TO HAVE SUPPORTED THE ANSWER
```

If the system only knows that an item was retrieved, serialized or transmitted, it should report exactly that stage.

## Boundary

```text
NEW MODULE: NO
NEW MEMORY ORGAN: NO
NEW AUTHORITY ROOT: NO
RUNTIME CHANGE: NOT AUTHORIZED BY THIS DOCUMENT
```
