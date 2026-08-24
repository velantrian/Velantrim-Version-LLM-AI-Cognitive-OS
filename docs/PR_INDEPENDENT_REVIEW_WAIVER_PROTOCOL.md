# Cross-Project PR Independent-Review Waiver Protocol

**Status:** governance guidance · docs only · no runtime authority  
**Applies to:** Velantrim repositories unless a stricter local rule exists

## Purpose

Define one honest, reusable format for closing a bounded pull request when an external independent reviewer is unavailable or the repository owner explicitly chooses not to wait for one.

Core invariant:

```text
self-review != independent review
```

A PR may still be closed without an external reviewer only through an explicit **owner governance waiver**. The record must never claim that independent review occurred.

## Required closure record

Before removing Draft or merging, record:

1. repository and PR number;
2. exact HEAD SHA;
3. expected tree SHA when available;
4. exact BASE/main SHA;
5. bounded PR scope;
6. exact-head CI evidence;
7. author-side / self-audit result, including known P0/P1 status;
8. explicit owner statement that the independent-review requirement is waived **for this PR only**;
9. explicit statement that `governance waiver != independent approval`;
10. all authority boundaries that remain closed after merge;
11. expected-head merge protection so head drift fails closed where supported;
12. post-merge read-back of PR state, merge commit/tree/parents and canonical authority state;
13. statement that a later independent post-merge audit remains permitted.

## Canonical owner-waiver wording

> **Owner waiver — independent review requirement waived for this bounded PR**
>
> The repository owner explicitly authorizes closure of this bounded PR without waiting for an external independent reviewer.
>
> This is a **governance waiver**, not a claim that independent review occurred.
>
> Closure basis:
> - exact-head CI status recorded;
> - bounded adversarial self-audit completed;
> - no unresolved blocking P0/P1 defect is known at closure;
> - scope remains within the stated PR boundary.
>
> This waiver applies **only to this PR** and does not silently authorize any later gate, runtime, deployment, Evidence, Canon, Pilot, production, or other authority expansion unless that authority is explicitly part of the PR and separately approved.
>
> A later independent post-merge audit remains permitted. Any material finding must be handled as a new bounded remediation/review event; it must not be retroactively represented as having been independently approved at merge time.

## Recommended merge-commit wording

```text
Owner-waived closure. Independent review did not occur; exact-head CI and bounded self-audit found no blocking P0/P1 defect. No authority beyond this PR scope is created.
```

## When the waiver is allowed

Use this pattern only when all of the following are true:

- the owner explicitly accepts the waiver;
- the PR scope is understood and bounded;
- required CI for the exact head is known;
- there is no unresolved blocking P0/P1 finding;
- no local protocol explicitly forbids owner-waived closure for this gate;
- the waiver does not pretend to satisfy an independent-review requirement that is itself an authority prerequisite in the owning protocol.

## When the waiver must NOT be used

Do not use this protocol to conceal or bypass:

- failed required CI;
- unresolved P0/P1 findings;
- head or tree drift;
- ambiguous PR scope;
- a failed independent review;
- a protocol that explicitly requires an independent approver as a semantic or authority condition;
- production, Canon, Evidence, Pilot, runtime-thaw, deployment, or other authority-changing decisions that have their own stricter admission rules.

In those cases the gate remains blocked until its owning protocol is satisfied.

## Post-merge audit

A later independent reviewer may audit the merged PR against the exact historical head/tree and merge commit.

If the reviewer finds a material issue:

```text
post-merge finding
-> new bounded remediation
-> fresh review of the remediation
-> no retroactive rewrite of historical review status
```

The historical record must continue to say that the original PR was merged under an owner waiver, not independent approval.

## Cross-project applicability

This protocol is intended as common guidance for Velantrim projects including:

- Velantrim Exo-Cortex Crystal;
- Velantrim Exo-Cortex Titan;
- Velantrim Native Kernel;
- Velantrim Mentaury Soul;
- Velantrim Continuum;
- related Velantrim repositories and governance surfaces.

A stricter local project rule always wins.

## Non-conflation invariants

```text
self-review != independent review
owner waiver != independent approval
green CI != semantic approval
merge != authority expansion
post-merge audit != retroactive approval
waiver for one PR != waiver for future PRs
```
