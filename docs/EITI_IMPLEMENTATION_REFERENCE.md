# EITI as an Implementation Reference for Cognitive OS Research

> Status: research/reference documentation. This file does not claim that Cognitive OS is implemented as a single runtime.

## Purpose

Velantrim EITI is a user-facing local-first Exo-Cortex application and rapid experimentation surface. Several mechanisms discussed in Cognitive OS research already have concrete implementation evidence inside EITI.

This makes EITI useful as a **prototype/reference client**, not as proof that the full Cognitive OS architecture is complete.

```text
EITI implementation evidence
        ↓
research signal / prototype reference
        ↓
Cognitive OS hypothesis + evaluation
        ↓
future owning runtime implementation
```

## EITI mechanisms with concrete evidence

| Capability area | EITI evidence | Cognitive OS research relevance |
|---|---|---|
| MOSC | `data/mosc_default_v1.json` in `velantrian/velantrim-eiti` | lexical/semantic routing and context activation research |
| Ranking / salience | `velantrim_core/tests_js/ranking.test.js`, `salience.test.js` | attention and retrieval-priority research |
| DAAD / decay | `velantrim_core/tests_js/decay.test.js` | memory accessibility/freshness dynamics |
| Local learning analysis | `velantrim_core/tests_js/apply_analysis.test.js` | adaptive-policy research; requires proposal/shadow boundaries before broader reuse |
| Cross-provider context | `velantrim_core/e2e/cross_ai_context.spec.js` | model replacement and provider-independence research |
| Full-context assembly | `velantrim_core/tests_js/full_ctx.test.js` | context strategy baseline/fallback research |

## Human capability interpretation

These mechanisms together suggest a practical direction beyond a stateless chatbot:

- remember across model/provider changes;
- activate related information rather than rely only on literal similarity;
- change retrieval priority over time;
- personalize associations and task routing;
- preserve user-facing continuity while underlying models remain replaceable.

The research question is not whether the mechanisms have cognitive names. The question is whether they measurably improve useful behavior compared with simpler baselines.

## Architectural placement

### Interaction Plane

EITI remains a strong reference for user-facing interaction, local context, switching providers and continuity UX.

### Cognitive Control Plane

Candidate research inputs from EITI include:
- MOSC routing support;
- bounded intent-pattern helpers;
- adaptive retrieval-policy proposals;
- attention/salience/novelty signals;
- fallback/full-context policy.

The control plane coordinates strategy; it does not become an owner of trusted memory, identity or objective truth.

### Memory Plane

EITI demonstrates persistent local memory mechanics, but Cognitive OS should preserve separation among:
- retrieval relevance;
- association strength;
- salience;
- freshness;
- epistemic confidence;
- evidence/provenance;
- authority/admission.

A useful invariant is:

```text
association strength != truth
salience != evidence
forgetting/decay != epistemic revision
```

### Assurance Plane

EITI implementation evidence should be treated as an input to evaluation, not as self-certification. Every candidate mechanism should be benchmarked against a simpler baseline and checked for regressions, authority violations and feedback loops.

## Relationship to Titan and other projects

- **Titan** owns orchestration experiments, shadow evaluation, retrieval composition and benchmarks.
- **Crystal** owns trusted evidence/memory admission and provenance; EITI signals do not write trusted state automatically.
- **Native Kernel** may capture durable substrate-neutral invariants, not EITI implementation details.
- **Mentaury Soul** owns beliefs/identity/relationships/commitments.
- **Mentaury Kernel** owns cross-domain composition contracts and conformance.
- **Continuum** can research long-term recovery and process continuity under runtime/model replacement.

## Promotion criterion

An EITI mechanism should become part of a broader Cognitive OS implementation only when:

1. the owning runtime/domain is identified;
2. the intended human capability is explicit;
3. the mechanism has a measurable advantage over a simple baseline;
4. negative/adversarial tests cover feedback loops and semantic conflation;
5. runtime authority is bounded by the owning domain;
6. the feature is independently implemented and observed outside the EITI prototype where required.

## Current related work

EITI correctness hardening is tracked in draft PR `velantrian/velantrim-eiti#76`, which makes JSON Schema failures blocking and adds regression coverage. This is a correctness improvement in EITI; it does not itself change Cognitive OS research status.
