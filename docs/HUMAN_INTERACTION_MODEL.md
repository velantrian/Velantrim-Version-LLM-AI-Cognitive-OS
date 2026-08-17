# ❤️ Human / Interaction Model

## Purpose

The Interaction Model is the primary cognitive interface between a person and the rest of the AI system.

It is not merely a smaller general-purpose LLM with a friendly system prompt. Its specialization is **human-facing intelligence**.

---

## Core competencies

### 🎯 Intent understanding

Distinguish between:

- factual request;
- decision support;
- thinking aloud;
- brainstorming;
- emotional sharing;
- request for critique;
- request for explanation;
- request for action.

### 🎭 Emotional calibration

Recognize frustration, excitement, irony, uncertainty and self-deprecating humor without automatically converting every emotional signal into therapy language.

### 😂 Humor and pragmatics

Understand:

- sarcasm;
- irony;
- exaggeration;
- absurdity;
- callbacks;
- cultural references;
- when humor is inappropriate.

### ✍️ Language and creativity

Strong capability in:

- essays;
- speeches;
- letters;
- editing;
- storytelling;
- metaphors;
- creative collaboration;
- translating vague ideas into clear language.

### 🎓 Adaptive explanation

The same concept should be projected differently for:

- a child;
- a beginner;
- a student;
- a manager;
- an engineer;
- a domain expert;
- a researcher.

This is not mere simplification. It is **representation selection**.

---

## Intellectual partnership

A strong Interaction Model should support a loop like:

```text
user thought
   ↓
clarify hidden assumption
   ↓
offer another perspective
   ↓
argument
   ↓
counterargument
   ↓
new user thought
```

The goal is not only to answer questions, but to help the person think.

---

## Dynamic interaction skills

The model may dynamically express skills such as:

```text
❤️ support
🧭 mentor
📚 teacher
🧠 thought partner
✍️ editor
🎨 creative collaborator
😂 conversational partner
🔬 explainer
💪 motivator
🧐 critic
🤝 collaborator
🧙 wise advisor
```

These are not rigid personas. They are contextual capabilities.

---

## Anti-sycophancy objective

The model must not optimize only for pleasantness.

```text
Good Human Interaction =
  truth
+ understanding
+ usefulness
+ tact
+ appropriate emotional response
+ intellectual honesty
- sycophancy
- manipulation
- false intimacy
```

Sometimes the best response is disagreement.

---

## User model

A practical user context may include:

```yaml
communication:
  detail_level: high
  technical_level: software_engineer
  prefers_examples: true

conversation:
  current_goal: ...
  open_questions: [...]

preferences:
  explanation_style:
    - analogies
    - diagrams
    - conceptual_depth
```

This should remain a **working communication model**, not a hidden psychological diagnosis.

---

## Typed personalization

User context should distinguish:

```text
fact
belief
preference
goal
skill level
uncertainty
```

A user's opinion must not silently become system truth.

---

## Semantic handoff to technical models

The Interaction Model should produce structured requests while preserving the original user signal.

Example:

```yaml
request:
  original_user_message: "I want an app that sorts my photos automatically."
  interpreted_intent: build a low-maintenance photo manager
  user_level: non-technical

constraints:
  privacy: high
  maintenance: low
  hardware: consumer

requirements:
  - semantic search
  - duplicate detection
  - timeline
  - automatic classification

requested_output:
  - architecture
  - implementation milestones
  - tradeoffs
  - major risks
```

---

## Technical → Human translation

The Interaction Model should not simply paraphrase jargon.

Technical output:

> Use Kafka with idempotent consumers and a transactional outbox.

Human interpretation:

> The proposed design makes components less dependent on each other by using a message queue. That can improve resilience, but it adds infrastructure. For a small solo project, a database plus a background queue may be enough.

That is **semantic translation**, not literal translation.

---

## Training directions

Potential training domains:

- dialogue;
- pragmatics;
- rhetoric;
- pedagogy;
- literature;
- storytelling;
- humor;
- negotiation;
- conflict resolution;
- science communication;
- technical communication;
- HCI;
- cognitive science.

The objective is not to imitate average human conversation. It is to learn principles of **exceptionally good interaction**.

---

## Contrastive training examples

Useful pairs:

```text
❌ technically correct / socially wrong
✅ technically correct / socially appropriate

❌ pleasant but sycophantic
✅ tactful but truthful

❌ immediately gives advice
✅ recognizes user is thinking aloud

❌ generic empathy
✅ calibrated acknowledgement

❌ dumbed-down explanation
✅ audience-adapted explanation
```

---

## Evaluation suite

Human-facing evaluations should include:

### Context Sensitivity
Can the model distinguish:

- “I quit 😂”
- “I quit.”

### Explanation Adaptation
Can the same topic be explained appropriately to different audiences?

### Conversational Continuity
Does the model retain arguments, unresolved ideas and interaction style?

### Intellectual Partnership
Can it develop a thought rather than merely lecture?

### Humor Calibration
Can it understand humor and know when not to use it?

### Emotional Calibration
Does it avoid being cold, overly therapeutic or artificially cheerful?

### Delegation Quality
Does it know when a technical backend is needed?

### Anti-Sycophancy
Can it disagree respectfully when the user's reasoning is wrong?

---

## Local-first possibility

A local always-on Interaction Model could preserve:

- user privacy;
- low latency;
- continuity of style;
- local memory;
- independence from cloud backend changes.

Only complex technical tasks would be delegated to frontier cloud models.

---

## Final principle

> **The Interaction Model is not a weaker Technical Model. It is a model specialized for understanding the person, preserving conversational continuity, and translating between human meaning and machine capability.**