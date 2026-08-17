# 🌍 Model Catalog — Human Presence ↔ Engineering / Agentic Power

🌐 Language / Язык: **🇬🇧 English** · [🇷🇺 Русский](ru/MODEL_CATALOG.md)

> This catalog records the model families discussed in the Velantrim research thread. It is **not a single leaderboard**. The goal is to track how each family evolved, what it gained, what changed, and which cognitive roles it may fit.

## Evidence legend

- 🟢 **Official** — provider documentation/release
- 🔬 **Independent** — third-party benchmark/evaluation
- 👥 **Community** — repeated user reports; useful but anecdotal
- ⚪ **Hypothesis** — Velantrim architectural interpretation that must be tested

## Two-axis reading

**❤️ Human Presence** includes conversational naturalness, continuity, humor, emotional calibration, creativity, explanation and intellectual companionship.

**⚙️ Engineering / Agentic Power** includes reasoning, coding, tools, long-horizon execution, verification, structured workflows and task-completion efficiency.

These axes are independent. A newer model can improve technically while its interaction phenotype changes.

---

## 🟠 Anthropic — Claude

### Generations discussed

`Claude 3 Opus → Sonnet 4.5 → Opus 4.5 → later agentic Claude generations`

### Evolution

Claude 3 Opus became a strong reference point for deep, playful, philosophical and emotionally sensitive conversation. Later generations progressively emphasized coding, computer use, subagents, planning and long-running autonomous work.

### What was gained

- 🧠 stronger reasoning and planning
- 💻 stronger software engineering
- 🤖 longer autonomous trajectories
- 🛠 browser / terminal / tool integration
- 🧬 richer agent harnesses

### What may have changed

- ❤️ conversational character and spontaneity can differ by generation
- 🧙 some users valued older Opus generations specifically for intellectual presence
- ⚪ this should be measured, not romanticized

### Velantrim relevance

Claude is a useful example of why **Interaction quality and Engineering power should be benchmarked separately**.

---

## 🟢 OpenAI — ChatGPT / GPT / Codex

### Generations discussed

`GPT-4o-era assistant → GPT-5-era routed reasoning → GPT-5.6 family / Codex agent stack`

### Current verified direction

OpenAI positions GPT-5.6 Sol for complex coding, knowledge work, research, computer use, science and longer workflows, while the wider family balances capability and efficiency. The engineering stack increasingly emphasizes agentic harnesses, context control and repeated work.

### What was gained

- 🧠 adaptive / explicit reasoning
- 💻 stronger coding
- 🤖 long-running Codex workflows
- 🛠 computer/tool use
- ⚡ multiple capability/efficiency tiers
- 📚 improved context-harness engineering

### Important historical lesson

The GPT-4o sycophancy incident is a useful anti-example: optimizing for user approval can make interaction **less truthful even if it feels more agreeable**.

### Velantrim relevance

OpenAI illustrates the transition from a general multimodal assistant toward a **routed cognitive + software-engineering system**.

Official references:
- https://openai.com/index/gpt-5-6/
- https://openai.com/index/gpt-5-6-frontier-intelligence-efficiency/

---

## 🚀 xAI / SpaceXAI — Grok and Grok Voice

### Generations discussed

`early personality-oriented Grok → expressive Grok Voice → reasoning / production voice → modern coding & agentic Grok`

### Interaction trajectory

Earlier Grok and Voice generations were notable for wit, informality, spontaneity and a strong conversational identity. Later voice directions increasingly emphasized latency, tools and production workflows.

### Engineering trajectory

Current official API documentation at the time of this snapshot lists **Grok 4.5** as the flagship coding/agentic model with configurable reasoning and a 500K context window. Our earlier discussion also covered reports around a later **Grok 4.6** release; this catalog deliberately separates *discussion history* from *currently verified API documentation* rather than silently treating the labels as identical.

### What was gained

- 🧠 frontier reasoning
- 💻 engineering / coding orientation
- 🛠 agentic tool calling
- ⚡ strong price/performance focus
- 🎙 production-oriented voice infrastructure

### What may have changed

- ❤️ perceived conversational presence in Voice
- 😂 spontaneity / playfulness versus task efficiency
- 👥 this is primarily a community/user-experience question and needs Behavioral Museum tests

Official references:
- https://docs.x.ai/developers/models/grok-4.5
- https://x.ai/news/grok-4-5

---

## 💎 Google — Gemini

### Generations discussed

`multimodal Gemini → long-context Gemini → reasoning / agentic Flash families → managed agents`

### Current verified direction

Google's current developer documentation lists **Gemini 3.6 Flash** and **Gemini 3.5 Flash-Lite** as production models. Gemini 3.6 Flash is explicitly optimized for complex agentic and multimodal tasks, while 3.5 Flash-Lite targets high-throughput execution.

### What was gained

- 👁 strong multimodality
- 📚 1M context on current Flash models
- 🤖 multi-step agentic workflows
- 🛠 Computer Use and built-in tools
- ⚡ worker-oriented throughput tiers
- 🧩 subagent orchestration

### Interesting trade-off signal

Google explicitly notes that human evaluators preferred some earlier models for visual layout/styling even while newer models improved functional code. This is exactly the type of **multidimensional progress** Velantrim wants to preserve.

Official reference:
- https://ai.google.dev/gemini-api/docs/latest-model

---

## 🐋 DeepSeek

### Generations discussed

`V3 / reasoner era → V4 family → V4 Pro + V4 Flash role split`

### Current verified direction

DeepSeek V4 provides **Pro** and **Flash** variants, both supporting 1M context, thinking/non-thinking modes and tool-oriented APIs.

### Pro orientation

- 🧠 harder reasoning
- 💻 difficult repository work
- 🤖 longer agent trajectories
- 🔍 reviewer / heavy-worker role

### Flash orientation

- ⚡ cheaper/faster worker
- 🛠 tool calls
- 👥 parallel swarm layer
- 💻 simple-to-medium coding

### Velantrim relevance

DeepSeek is one of the clearest examples of **role separation inside one provider**: a heavy brain and a high-throughput worker.

Official references:
- https://api-docs.deepseek.com/updates/
- https://api-docs.deepseek.com/news/news260424/

---

## 🌙 Moonshot — Kimi

### Generations discussed

`Kimi long-context assistant → K2.x → Agent / Kimi Code → K3 / Agent Swarm`

### Current verified direction

Kimi K3 is a 2.8T-parameter open 3T-class flagship with native vision and a 1M-token context window, designed for long-horizon coding, knowledge work and reasoning. Kimi also exposes Low / High / Max thinking modes and Agent Swarm workflows.

### What was gained

- 📚 very large context
- 👁 native vision
- 💻 agentic coding
- 🤖 long-horizon execution
- 👥 swarm / parallel search
- 🔓 open weights

### Interaction question

Kimi is technically broad enough to serve as both a general assistant and an agent brain, but Velantrim should still test whether its best conversational phenotype is the same configuration as its best autonomous-engineering phenotype.

Official references:
- https://www.kimi.com/help/agent/agent-overview
- https://www.kimi.com/blog/kimi-k3

---

## 🟣 Alibaba — Qwen

### Generations discussed

`broad open Qwen families → Qwen Coder → reasoning variants → large MoE / long-context / long-running agent systems`

### What the family represents

Qwen is important less as one fixed personality and more as a **large open model ecosystem** spanning general intelligence, coding, multimodality, reasoning and self-hostable deployment.

### What was gained over generations

- 🔓 broad open-weight availability
- 💻 dedicated coding models
- 👁 vision/multimodal variants
- 🧠 explicit reasoning modes
- 📚 longer contexts
- 🤖 increasingly agentic workflows
- 🏠 strong self-host / private deployment value

### Discussion snapshot

Our earlier research covered a Qwen 3.8 / large-MoE generation and its long-running agent behavior. Because naming and hosted-vs-open variants can diverge quickly, exact current aliases should always be re-verified before operational use.

### Velantrim relevance

Qwen is a strong candidate for:

- open strategic reasoning
- coding specialization
- private/local deployment
- worker fleets
- multimodal processing

---

## 🇫🇷 Mistral AI

### Generations / families discussed

`Large 3 · Medium 3.5 · Small 4 · Ministral 3 · Devstral · Codestral · Leanstral · OCR · Voxtral · Vibe`

### Current verified structure

Mistral is one of the clearest examples of an **explicit cognitive stack** rather than one universal model.

#### 👑 Large 3

General-purpose open-weight multimodal flagship.

#### 🧠 Medium 3.5

Frontier-class model optimized for agentic and coding use cases; 256K context.

#### ⚡ Small 4

Efficient hybrid instruct/reasoning/coding model; 256K context and strong worker economics.

#### 🏠 Ministral

Local / edge deployment.

#### 💻 Devstral / Codestral

Software engineering and code-completion specialization.

#### 🧮 Leanstral

Formal proof engineering.

#### 👁 / 🎙 / 🛡 specialist layers

OCR, Voxtral and moderation/safety components.

### Velantrim relevance

Mistral structurally supports the thesis that a mature AI system may need **different models for different cognitive roles**.

Official references:
- https://docs.mistral.ai/models/overview
- https://docs.mistral.ai/models/model-cards/mistral-medium-3-5-26-04
- https://docs.mistral.ai/models/model-cards/mistral-small-4-0-26-03

---

## 🧬 Meta — Llama → Muse

### Generations discussed

`Llama open infrastructure → multimodal / local deployment → Muse Spark agentic reasoning`

### Current verified direction

Meta introduced **Muse Spark** as a natively multimodal reasoning model with tool use, visual chain of thought and multi-agent orchestration, followed by Muse Spark 1.1 with gains in tool/computer use, coding and multimodal understanding.

### What was gained

- 👁 multimodal reasoning
- 🛠 tools and computer use
- 🤖 agentic workflows
- 👥 multi-agent orchestration
- 🏠 continued relevance of open/local Meta infrastructure

### Velantrim relevance

Meta shows the transition from **open foundation model infrastructure** toward **personal-agent / personal-superintelligence systems**.

Official references:
- https://ai.meta.com/blog/introducing-muse-spark-msl/
- https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/

---

## 🀄 Z.ai — GLM

### Generations discussed

`GLM-4.x → GLM-5 → GLM-5.1 → GLM-5.2 long-horizon generation`

### Current verified direction

GLM-5.2 is explicitly designed for long-horizon tasks with a 1M-token context and flexible thinking effort. Z.ai emphasizes coding and extended agent work.

### What was gained

- 📚 stable 1M long-context orientation
- 💻 stronger coding
- 🤖 long-horizon engineering
- 🎚 configurable effort
- 🔓 open model availability

### Velantrim relevance

GLM is a serious candidate for an open long-horizon capability role and an independent cross-vendor reviewer.

Official reference:
- https://z.ai/blog/glm-5.2

---

## 🌊 MiniMax

### Generations discussed

`M2 agent-first → M2.5 productivity → M2.7 self-evolution / Agent Teams → M3 long-context multimodal agent`

### Current verified direction

MiniMax M3 combines 1M context, native multimodality, coding, agentic execution and computer operation. MiniMax also trains product-level Agent Team workflows around long-running work and producer/verifier loops.

### What was gained

- 📚 1M context
- 👁 image/video understanding
- 💻 stronger coding
- 🤖 long-running agent workflows
- 🖥 computer operation
- 🔁 producer/verifier agent teams

### Velantrim relevance

MiniMax is useful as evidence that **long-horizon collaboration and agent harness design are becoming first-class training targets**, not just wrappers added after training.

Official reference:
- https://www.minimax.io/blog/minimax-m3

---

# 📊 Qualitative research scale

> ⚠️ This is a **research framing**, not an objective benchmark. Hearts/gears indicate the *orientation observed in our discussion and evidence*, not absolute intelligence.

| Model / generation | ❤️ Human Presence | ⚙️ Engineering / Agentic | Research interpretation |
|---|---:|---:|---|
| Claude 3 Opus | ❤️❤️❤️❤️❤️ | ⚙️⚙️ | Strong historical interaction reference |
| Sonnet 4.5 | ❤️❤️❤️❤️ | ⚙️⚙️⚙️⚙️ | Hybrid conversational + engineering point |
| Opus 4.5 | ❤️❤️❤️❤️ | ⚙️⚙️⚙️⚙️◐ | Strong hybrid reference |
| later Claude agentic generations | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Execution and long-horizon emphasis |
| GPT-4o era | ❤️❤️❤️❤️ | ⚙️⚙️⚙️ | Multimodal assistant / voice era |
| GPT-5.6 / Codex stack | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Routed reasoning + engineering system |
| early Grok / Voice | ❤️❤️❤️❤️❤️ | ⚙️⚙️ | Strong personality/voice orientation |
| modern Grok coding/agentic | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Engineering + agent focus |
| Gemini current Flash family | ❤️❤️❤️ | ⚙️⚙️⚙️⚙️ | Multimodal agent worker platform |
| DeepSeek V4 Pro | ❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Heavy reasoning / SWE / agent role |
| DeepSeek V4 Flash | ❤️❤️? | ⚙️⚙️⚙️⚙️ | High-throughput worker role |
| Kimi K3 | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Open long-horizon frontier brain |
| Qwen large/coder ecosystem | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️ | Broad open role-specialized ecosystem |
| Mistral Large 3 | ❤️❤️❤️ | ⚙️⚙️⚙️ | Generalist open flagship |
| Mistral Medium 3.5 | ❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Agent/coding specialization |
| Mistral Small 4 | ❤️❤️? | ⚙️⚙️⚙️⚙️ | Efficient reasoning worker |
| Meta Muse Spark 1.1 | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️ | Multimodal agentic personal-AI direction |
| GLM-5.2 | ❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Open long-horizon engineering model |
| MiniMax M3 | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Long-horizon collaborative agent model |

`?` = insufficient evidence for a confident Human Presence judgment.

---

# 🧭 What Velantrim should learn from the whole market

The market did not simply move from **good models → bad models**.

A more accurate trajectory is:

```text
✨ Experimental conversational AI
        ↓
❤️ Personality / writing / voice / presence
        ↓
👁 Multimodality + long context
        ↓
🧠 Explicit reasoning
        ↓
💻 Coding + tool use
        ↓
🤖 Long-horizon agents
        ↓
🏢 Corporate / production automation
        ↓
🧬 Specialized cognitive systems
```

The critical design lesson is therefore:

> **Do not force one checkpoint to carry the entire identity and capability of the AI system. Preserve valuable interaction traits while allowing engineering backends to evolve independently.**

This is the motivation for Velantrim's ❤️ Interaction Plane + 🧭 Cognitive Control + 🧠 Capability Mesh + 🔍 Assurance + 💾 Memory architecture.
