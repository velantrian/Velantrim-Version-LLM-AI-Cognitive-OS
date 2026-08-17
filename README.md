# 🚀 Velantrim Version LLM (AI) — Cognitive OS 💫

<div align="center">

🌐 **Language / Язык:** 🇬🇧 **English** · [🇷🇺 Русский](README.ru.md)

**❤️ Human Interaction · 🧭 Cognitive Routing · 🧠 Capability Models · 🔍 Assurance · 💾 Persistent Memory**

</div>

> **LLM = replaceable cognitive processor.**  
> **Cognitive OS = persistent intelligence.**

Velantrim Version LLM (AI) explores a modular cognitive architecture in which **human-facing interaction intelligence** and **machine-facing technical intelligence** do not have to live inside one universal checkpoint. They cooperate through explicit routing, structured memory, independent verification and semantic handoff protocols.

The project is motivated by a simple observation: **model progress is multidimensional**. A new generation can become dramatically stronger at reasoning, coding, tool use, multimodality and long-horizon agency while also changing its conversational character, creative voice, humor, spontaneity, emotional calibration or explanation style. That change is not automatically a regression; often it reflects a different optimization target.

Velantrim Cognitive OS is designed so progress in one dimension does not have to erase valuable qualities in another.

---

## ⚡ Core idea

Instead of forcing one universal model to be simultaneously the best:

- ❤️ human companion and conversational partner;
- 🎭 socially calibrated communicator;
- 😂 humorist and contextual conversationalist;
- ✍️ writer, editor and creative collaborator;
- 🎓 adaptive teacher and explainer;
- 🧠 strategic reasoner;
- 💻 coding agent;
- 🔎 researcher;
- 🤖 autonomous operator;
- 🛠 tool/computer user;
- 🔍 verifier;
- 💾 memory keeper;

Velantrim separates these responsibilities into cooperating cognitive planes.

```text
                         👤 USER
                            │
                            ▼
                 ❤️ Interaction Plane
                            │
                 intent · context · meaning
                            │
                            ▼
                 🧭 Cognitive Control
                            │
           ┌────────────────┼────────────────┐
           ▼                ▼                ▼
       🧠 Reasoner       💻 Coder       🔎 Researcher
           │                │                │
           ├────────────────┼────────────────┤
           ▼                ▼                ▼
       👁 Vision         🛠 Tools        🧬 Specialist
           │
           └────────────────┬────────────────┘
                            ▼
                     🔍 Assurance
                            │
                            ▼
                 ❤️ Human Interpretation
                            │
                            ▼
                         👤 USER

               ═════════════════════════
                   💾 Memory Plane
               user · task · episodes
               facts · provenance · state
               ═════════════════════════
```

---

## 🧬 The five planes

| Plane | Main question | Responsibility |
|---|---|---|
| ❤️ **Interaction** | What does the person mean, and how should this be communicated? | Intent, dialogue, explanation, humor, creativity, adaptation, semantic handoff |
| 🧭 **Cognitive Control** | Who should think, and how? | Model routing, reasoning effort, serving mode, tools, context policy, latency, privacy, cost |
| 🧠 **Capability** | How do we solve the task? | Reasoning, coding, research, vision, documents, agents, specialists |
| 🔍 **Assurance** | Can we trust the result? | Tests, evidence, deterministic checks, adversarial review, cross-model verification |
| 💾 **Memory** | What must persist beyond one model call? | User model, task state, provenance, Hot/Warm/Cold memory, verified facts |

---

## ❤️ Interaction Model

The Interaction Model is **not** a smaller technical model with a system prompt saying “be friendly”. Its specialization is the human-facing side of intelligence:

- understanding intent and conversational pragmatics;
- distinguishing a factual question from thinking aloud;
- emotional calibration without turning every emotion into therapy;
- humor, irony, callbacks and timing;
- adapting explanation depth to the person;
- intellectual partnership and constructive disagreement;
- writing, storytelling, editing and metaphor;
- translating human intent into machine-oriented specifications;
- translating technical output back into useful human meaning.

Its objective must not be “make the user happy”, because that can reward sycophancy.

```text
Good Human Interaction =
  truthfulness
+ intent understanding
+ usefulness
+ tact
+ explanatory quality
+ social calibration
+ intellectual honesty
+ appropriate disagreement
- sycophancy
- manipulation
- false intimacy
- over-personalization
```

---

## 🧠 Capability Models

Capability models are optimized for machine-facing work:

- complex reasoning and mathematics;
- coding and debugging;
- research and document analysis;
- tool and computer use;
- planning and structured outputs;
- long-horizon agent workflows;
- APIs, databases and simulations;
- specialist or verification-oriented work.

They may be larger, slower, more expensive and less conversational. That is acceptable: they are **compute engines**, not necessarily the identity of the system.

---

## 🧭 Cognitive routing

The router should choose more than a model name.

```text
TASK
 │
 ├─ model role?
 ├─ model family?
 ├─ reasoning effort?
 ├─ serving mode?
 ├─ reasoning / agent strategy?
 ├─ context strategy?
 ├─ tools?
 ├─ verifier?
 ├─ privacy boundary?
 └─ cost / latency budget?
```

A useful default effort ladder is:

```text
trivial  → Low
routine  → Medium
complex  → High
critical → XHigh
extreme  → Max
```

But repeated failure should not automatically mean “more tokens”. The system may instead switch model family, start with fresh context, change reasoning strategy, decompose the task differently or invoke an independent verifier.

---

## 🔍 Assurance instead of self-trust

A model that creates a solution should not be the only judge of its correctness.

```text
Model A creates
      ↓
Model B attacks
      ↓
deterministic tests
      ↓
Model C integrates
```

Assurance can include compilers, tests, static analysis, formal verification, source-backed factual checks, database constraints, policy checks and independent cross-family reviewers.

> ❤️ Interaction asks: **Does this answer fit the human?**  
> 🔍 Assurance asks: **Is this answer trustworthy?**

---

## 💾 Persistent memory and anti-degradation

Long context is not durable memory.

```text
🔥 HOT  → active working context
🌤 WARM → decisions, summaries, relevant documents
❄️ COLD → full archive / forensic history
```

The active model should ideally receive:

```text
Original Objective
+ Current State
+ Relevant Memory
+ Recent Trajectory
+ Needed Evidence
```

Important task invariants must exist outside transient model context:

```yaml
task_invariants:
  original_goal: ...
  hard_constraints: [...]
  user_non_goals: [...]
  acceptance_criteria: [...]
  safety_boundaries: [...]
```

This helps resist:

- 🌀 context rot;
- 🎯 goal drift;
- ♻️ agent loops;
- 🧠 self-confirming errors;
- 💾 memory contamination;
- 🤝 sycophancy;
- 🏭 model-update regression.

---

## 🕰️ Model evolution: from conversational experiments to agentic systems

A major research question is how AI systems evolved from early “wow, it talks” products into production-grade cognitive workers.

```text
✨ conversational novelty
        ↓
💬 character / writing / chat
        ↓
👁 voice + multimodality + long context
        ↓
🧠 explicit reasoning
        ↓
💻 coding + tool use
        ↓
🤖 long-horizon agents
        ↓
🏢 production / enterprise automation
```

This is not automatically “better” or “worse”. It is often a change in optimization target.

Velantrim therefore tracks at least two independent families of qualities:

- ❤️ **Human Presence** — conversation, personality, humor, creativity, emotional calibration, explanation, intellectual companionship;
- ⚙️ **Engineering / Agentic Power** — reasoning, coding, tools, reliability, autonomy, long-horizon execution, cost/task.

Families discussed in this research include Anthropic Claude, OpenAI GPT/Codex, xAI Grok/Grok Voice, Google Gemini, DeepSeek, Kimi, Qwen, Mistral, Meta/Llama and newer agent-oriented families, GLM, MiniMax and emerging open/proprietary systems.

---

## 🏛️ Behavioral Museum

A future system should not discard successful behavioral traits just because a checkpoint is superseded.

The **Behavioral Museum** preserves reproducible examples of:

- 💬 representative dialogue;
- 😂 humor, irony and callbacks;
- ❤️ emotional calibration;
- 🧙 deep intellectual conversation;
- 🎓 explanations;
- ✍️ creative writing;
- 🧪 behavioral evaluations;
- ⚙️ model/system configuration;
- 📊 human-preference comparisons.

The goal is not to run old models forever. The goal is to preserve measurable traits so they can be reproduced, distilled or used as regression tests.

---

## 🧬 Model Genome

Models should be evaluated as multidimensional profiles rather than one leaderboard score.

```yaml
model_profile:
  human:
    interaction_presence: ...
    conversational_continuity: ...
    humor_and_playfulness: ...
    emotional_calibration: ...
    creativity_and_writing: ...
    explanation_quality: ...

  technical:
    reasoning: ...
    coding: ...
    agentic_long_horizon: ...
    tool_use: ...
    verification: ...
    context_effectiveness: ...

  operational:
    latency: ...
    cost_per_verified_task: ...
    privacy: ...

  evidence:
    official: ...
    independent: ...
    community: ...
    hypothesis: ...
```

A new model should be admitted **by role**, not globally.

> Example: `+15% coding, −20% Interaction Presence` → ✅ new **Coder**, ❌ not automatically the new **Human Interface**.

---

## 🔐 Local-first direction

A particularly important architecture is a local Interaction Model with selective cloud delegation:

```text
                    DEVICE
                       │
             ❤️ Interaction Model
                       │
                 private memory
                       │
          ┌────────────┴────────────┐
          │                         │
   local conversation         sanitized task
                                    │
                                    ▼
                              ☁️ Frontier AI
                                    │
                                    ▼
                              raw solution
                                    │
                                    ▼
                           ❤️ local model
                                    │
                                    ▼
                                  USER
```

This can reduce latency, preserve interaction continuity, improve privacy and make cloud capability providers replaceable.

---

## 📚 Documentation / Документация

Every canonical document is maintained in both languages with a language switch at the top.

| Topic | 🇬🇧 English | 🇷🇺 Русский |
|---|---|---|
| 🧬 Architecture | [ARCHITECTURE.md](docs/ARCHITECTURE.md) | [ARCHITECTURE.md](docs/ru/ARCHITECTURE.md) |
| 📜 Full canonical handoff | [FULL_HANDOFF.md](docs/FULL_HANDOFF.md) | [FULL_HANDOFF.md](docs/ru/FULL_HANDOFF.md) |
| 🕰️ Model evolution | [MODEL_EVOLUTION.md](docs/MODEL_EVOLUTION.md) | [MODEL_EVOLUTION.md](docs/ru/MODEL_EVOLUTION.md) |
| 🛡️ Anti-degradation | [ANTI_DEGRADATION.md](docs/ANTI_DEGRADATION.md) | [ANTI_DEGRADATION.md](docs/ru/ANTI_DEGRADATION.md) |
| ❤️ Human / Interaction Model | [HUMAN_INTERACTION_MODEL.md](docs/HUMAN_INTERACTION_MODEL.md) | [HUMAN_INTERACTION_MODEL.md](docs/ru/HUMAN_INTERACTION_MODEL.md) |
| 🧭 Cognitive routing | [MODEL_ROUTING.md](docs/MODEL_ROUTING.md) | [MODEL_ROUTING.md](docs/ru/MODEL_ROUTING.md) |
| 🏛️ Behavioral Museum | [BEHAVIORAL_MUSEUM.md](docs/BEHAVIORAL_MUSEUM.md) | [BEHAVIORAL_MUSEUM.md](docs/ru/BEHAVIORAL_MUSEUM.md) |
| 🧬 Model Genome | [MODEL_GENOME.md](docs/MODEL_GENOME.md) | [MODEL_GENOME.md](docs/ru/MODEL_GENOME.md) |
| 🧪 Evaluation framework | [EVALUATION_FRAMEWORK.md](docs/EVALUATION_FRAMEWORK.md) | [EVALUATION_FRAMEWORK.md](docs/ru/EVALUATION_FRAMEWORK.md) |
| 🗺️ Research roadmap | [RESEARCH_ROADMAP.md](docs/RESEARCH_ROADMAP.md) | [RESEARCH_ROADMAP.md](docs/ru/RESEARCH_ROADMAP.md) |

---

## 🧭 Research status

This repository currently represents a **research architecture and design direction**, not a claim of completed production implementation.

Core research questions include:

1. How should Human Presence be measured independently of technical intelligence?
2. Which traits from earlier model generations are worth preserving?
3. How can Interaction Models delegate without becoming lossy semantic codecs?
4. How should routing combine quality, reasoning effort, cost, privacy and latency?
5. How independent must a verifier be from the generating model?
6. How should memory distinguish facts, beliefs, preferences and uncertain hypotheses?
7. How can the system detect degradation during long-running trajectories?
8. Can Interaction and Capability models be jointly trained through outcome-level rewards?
9. How should historical model behavior be preserved as reproducible evidence rather than nostalgia?
10. How can a stable human-facing identity survive repeated backend replacement?

---

## 🌟 Design principle

> **Do not fight model degradation by searching for an eternal perfect model. Build the system so that a model may degrade, fail, age or be replaced — while the continuity of intelligence, memory, human interaction and control survives.**

### 🚀 Velantrim

A research direction toward persistent, modular, human-centered cognitive systems.