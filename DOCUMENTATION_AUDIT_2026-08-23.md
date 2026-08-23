# Documentation Audit — 2026-08-23

**Scope:** accuracy/currency (точность и актуальность) and completeness/structure (полнота и структура) of this repository's documentation (`*.md`, README, `docs/`), assessed against a snapshot of the default branch on 2026-08-23. This is a documentation snapshot audit, not a code-quality or security review, and does not cover unmerged branches.

## Overall Health Assessment

**Fair.** The core narrative — the 10 bilingual docs indexed from the README plus `docs/FULL_HANDOFF.md` — is internally coherent, uses a consistent evidence-labeling discipline for speculative claims, and has zero broken internal markdown links or empty/stub files across all 32 files (verified programmatically). However, the set clearly grew in two disconnected waves: a later batch of 6 files — three of which duplicate the "model evolution across AI providers" topic almost paragraph-for-paragraph — was never wired into the README's navigation, uses a different front-matter convention, and isn't fully bilingual. Even within the original "canonical, bilingual" set, the README's explicit promise that "every canonical document is maintained in both languages" is contradicted by at least two doc pairs whose Russian version silently contains entire sections the English version lacks.

## Findings

1. **docs/MODEL_EVOLUTION.md, docs/MODEL_FAMILY_EVOLUTION.md, docs/MODEL_CATALOG.md** | structure | high | Three unresolved, largely-duplicate documents cover the identical topic (model evolution across the same 11 providers, same order) with no cross-reference explaining which supersedes which. | `MODEL_FAMILY_EVOLUTION.md` is dated ("Last research refresh: 2026-08-17") and far more granular, yet the README only links the older, undated, less-detailed `MODEL_EVOLUTION.md`; `MODEL_CATALOG.md` covers the same ground a third time and is linked from neither.

2. **README.md, README.ru.md** | completeness | high | The "Documentation" index (identical table in both languages) links only 10 of the 16 files in `docs/`, leaving 6 undiscoverable from the entry point. | Missing: `COGNITIVE_AI_RESEARCH_MAPPING.md`, `EITI_IMPLEMENTATION_REFERENCE.md`, `GROK_VOICE_EVOLUTION.md`, `MODEL_CATALOG.md`, `MODEL_FAMILY_EVOLUTION.md`, `PERSONAL_AI_TESTIMONY.md`. Two of these have zero inbound links from any file in the repo, in either language.

3. **docs/ANTI_DEGRADATION.md ↔ docs/ru/ANTI_DEGRADATION.md, docs/ARCHITECTURE.md ↔ docs/ru/ARCHITECTURE.md** | accuracy | high | Two "canonical, bilingual" doc pairs have silently diverged: the Russian version carries substantially more content with no note in the English version. | `docs/ru/ANTI_DEGRADATION.md` adds two entire sections absent from English and expands the closing law list from 10 to 15 items; `docs/ru/ARCHITECTURE.md` (332 lines) adds invariants 11-15 and three extra sections vs. the 239-line English version.

4. **docs/MODEL_CATALOG.md ↔ docs/MODEL_FAMILY_EVOLUTION.md** | accuracy | medium | The two docs contradict each other on Meta's current flagship direction. | `MODEL_CATALOG.md` says Meta's current direction is "Muse Spark / Muse Spark 1.1"; `MODEL_FAMILY_EVOLUTION.md` says it's the "Llama 4 Scout/Maverick/Behemoth direction" and never mentions Muse Spark.

5. **docs/EITI_IMPLEMENTATION_REFERENCE.md** | accuracy | medium | The only "current work" pointer in the entire doc set is an open, undated draft PR in a different repository — a stale-by-construction marker. | Line 106: "EITI correctness hardening is tracked in draft PR velantrian/velantrim-eiti#76..." — this is also the sole repo-wide hit for any TODO/draft/WIP-style marker.

6. **docs/MODEL_CATALOG.md, docs/MODEL_FAMILY_EVOLUTION.md, docs/PERSONAL_AI_TESTIMONY.md, docs/GROK_VOICE_EVOLUTION.md, docs/COGNITIVE_AI_RESEARCH_MAPPING.md, docs/EITI_IMPLEMENTATION_REFERENCE.md** | structure | medium | These 6 orphaned docs (finding #2) also share a different front-matter convention than the other 26 files, marking them as a separate, unintegrated authoring batch.

7. **docs/MODEL_CATALOG.md** | accuracy | medium | Repeatedly asserts it reflects the "current"/"snapshot" state but contains no date anywhere, unlike sibling docs which all stamp "Last research refresh: 2026-08-17."

8. **docs/COGNITIVE_AI_RESEARCH_MAPPING.md, docs/EITI_IMPLEMENTATION_REFERENCE.md** | completeness | low | The only 2 of 16 `docs/` files with no Russian counterpart at all, breaking the repo-wide bilingual pattern.

9. **docs/MODEL_ROUTING.md, docs/HUMAN_INTERACTION_MODEL.md, docs/RESEARCH_ROADMAP.md vs docs/ARCHITECTURE.md, docs/ANTI_DEGRADATION.md** | structure | low | Disclosure of the EN/RU content-asymmetry problem (finding #3) is itself inconsistent — some docs point readers to "the expanded Russian version," others with the same underlying issue give no such pointer.

**Not a defect, noted for completeness:** all 82 internal relative markdown links across the 32 files resolve correctly (verified programmatically); no file is empty or a stub; no LICENSE file exists but none of the docs reference one.

---
*Generated by an automated documentation audit (Claude Code).*
