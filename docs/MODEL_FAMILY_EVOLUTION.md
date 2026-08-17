# 🧬 Model Family Evolution — From Conversational AI to Cognitive/Agent Systems

🌐 Language / Язык: **🇬🇧 English** · [🇷🇺 Русский](ru/MODEL_FAMILY_EVOLUTION.md)

> This document tracks **families and generations**, not only today's flagship models. The central research question is: *what did each generation gain, what interaction qualities changed, and how did the industry's optimization target move from chat/personality toward reasoning, coding, tools, agents and production reliability?*

## ⚠️ Evidence discipline

- 🟢 **Official** — provider release/docs/system card.
- 🔬 **Independent** — reproducible third-party evaluation.
- 👥 **Community** — recurring user reports; useful but not proof.
- ⚪ **Velantrim hypothesis** — architectural interpretation requiring tests.
- `?` means insufficient evidence, **not poor quality**.

The ❤️ Human Presence and ⚙️ Engineering/Agentic axes are deliberately separate. Newer ≠ universally better; older ≠ universally more human.

---

## 🗺️ Industry-level trajectory

```text
✨ Chat / personality / wow effect
        ↓
👁 multimodality + 🎙 realtime voice
        ↓
📚 long context
        ↓
🧠 explicit thinking / reasoning
        ↓
💻 coding specialization
        ↓
🛠 reliable tool use + computer use
        ↓
🤖 long-horizon agents
        ↓
👥 subagents / swarms / verifier loops
        ↓
🏢 production, enterprise, cost-per-task, reliability
        ↓
❤️↔️🧠 Velantrim thesis:
preserve Interaction Intelligence while Capability Intelligence keeps scaling
```

---

# 🟠 Anthropic — Claude

### Evolution line
`Claude 2 → Claude 3 Haiku/Sonnet/Opus → 3.5 Sonnet → 3.7 Sonnet → Claude 4 Sonnet/Opus → Sonnet 4.5 / Opus 4.5 → Opus/Sonnet 4.6–4.8 → Sonnet 5-era`

Claude 3 Opus became an important historical reference for nuanced, philosophical, playful and emotionally sensitive dialogue. Later generations increasingly emphasized reasoning, coding, computer use, subagents and long autonomous work. This is a prime example of why **capability growth and interaction phenotype must be measured separately**.

---

# 🟢 OpenAI — GPT / ChatGPT / o-series / Codex

### Evolution line
`GPT-3.5 chat → GPT-4 → GPT-4 Turbo → GPT-4o multimodal/voice → o-series reasoning → GPT-5 routed reasoning → GPT-5.x professional work → Codex agent stack`

Early ChatGPT made conversational AI mainstream. GPT-4o pushed realtime multimodality and Voice. The o-series made test-time reasoning a first-class axis. GPT-5-era systems increasingly route between fast and deeper reasoning. Codex evolves from code generation toward **agentic software engineering** and longer tasks.

The GPT-4o sycophancy rollback is a critical interaction lesson: **more agreeable ≠ more human or better**. Truthfulness, tact and calibrated disagreement must be separate objectives.

---

# 🚀 xAI / SpaceXAI — Grok + Grok Voice

### Evolution line
`early Grok personality → Grok 2/3 reasoning → Grok 4/4.1 agent tools → expressive Grok Voice → Voice Think Fast 1.0 → Voice Think Fast 2.0 → Grok 4.5 flagship`

Early Grok differentiated through personality, informality and wit. **Early Grok Voice is an especially important Interaction reference:** users later described its baseline as longer-form, emotionally expressive, spontaneous and strongly human-present.

**Think Fast 1.0 (Apr 23, 2026)** was the first explicit reasoning/production revolution for Voice: realtime reasoning without added latency, complex multi-step workflows, high-volume tool calling, support/sales/booking, and real Starlink deployment. During May, recurring community reports described a coincident shift toward faster, colder, flatter or customer-service-like behavior and reduced emotional character. This is a correlation signal, not proven checkpoint causality.

**Think Fast 2.0 (Jul 29, 2026; `grok-voice-latest` → 2.0 from Aug 5)** continued the speech-to-speech/agentic line and strengthened speed-oriented performance. During the rollout window, independent users reported sharply shorter default answers and reduced conversational depth. Importantly, a prominent short-answer thread dates to Jul 19, before the public 2.0 API release. Velantrim therefore does not attribute the change to the 2.0 checkpoint alone: routing, system prompts, token policy or product configuration may also be involved.

```text
🎙️ expressive Voice
❤️ presence · 💬 depth · 😂 spontaneity
            ↓
⚡ Think Fast 1.0
🧠 reasoning · 🛠 tools · 📞 workflows
            ↓
⚡⚡ Think Fast 2.0 / rollout era
⚡ lower latency · 🤖 stronger voice-agent direction
+ 👥 short-answer / reduced-depth reports
            ↓
🏢 production Voice Agent
```

This is one of the strongest examples of **a model technically improving while its Interaction phenotype may change**.

➡️ **[Detailed case study: 🎙️ GROK_VOICE_EVOLUTION.md](GROK_VOICE_EVOLUTION.md)** — chronology, gains/regressions table, evidence discipline and Behavioral Museum protocol.

---

# 💎 Google — Gemini

### Evolution line
`Gemini 1.x multimodal → Gemini 1.5 long context → Gemini 2.x/Flash → Gemini 2.5 Pro/Flash thinking → Gemini 3.x/3.6 Flash agentic production line`

Gemini illustrates **multimodal assistant → huge-context model → reasoning substrate → multimodal agent worker platform**. Multimodality and huge context became foundations; thinking and Flash later made reasoning and high-throughput execution production primitives.

---

# 🐋 DeepSeek

### Evolution line
`V2/V2.5 → V3 → R1 reasoning → V3.2 thinking/non-thinking → V4 Pro + V4 Flash`

DeepSeek first differentiated through efficiency/open accessibility, then R1 through reasoning. V3.x brought thinking/non-thinking closer together; V4 formalizes a role split: **Pro = heavy brain**, **Flash = fast worker**. This directly supports role-based routing.

---

# 🌙 Moonshot AI — Kimi

### Evolution line
`long-context Kimi → Kimi-VL / Dev / Researcher → K2 → K2 Thinking → K2.5 → Agent Swarm → K2.6 → K3`

Kimi began with long-context identity. Context then evolved from “more tokens” into a workspace for coding and agents. K2 Thinking strengthened reasoning and multi-step tools; K2.5/2.6 unified multimodality, dialogue, thinking and agents; Agent Swarm formalized parallel execution; K3 scales the line to an open 3T-class model with native vision and 1M context.

---

# 🟣 Alibaba — Qwen

### Evolution line
`Qwen/Qwen1.5 → Qwen2 → Qwen2.5 + Coder → QwQ reasoning → Qwen3 hybrid thinking → Qwen3-Coder → Coder-Next → Qwen3-Max-Thinking`

Qwen evolved from a broad open-weight family into a **specialized open cognitive ecosystem**. Qwen2.5-Coder strengthened code; QwQ/Qwen3 reasoning; Qwen3-Coder agentic coding/browser/tools; Coder-Next scales agentic training signals and executable-environment RL; Max-Thinking combines large-scale RL, test-time scaling and adaptive tools.

---

# 🇫🇷 Mistral AI

### Evolution line
`Mistral 7B / Mixtral → Small/Medium/Large → Large 2.x → Small 3.x / Medium 3.x → Devstral + Magistral + specialists → Large 3 / Medium 3.5 / Small 4 / Ministral 3 / Vibe`

Mistral is especially relevant to Velantrim because the company increasingly builds a **portfolio of cognitive roles** rather than one universal checkpoint: Large generalist; Medium frontier/cost-efficient enterprise; Small efficient worker; Devstral SWE agents; Magistral reasoning; Ministral local/edge; OCR/Voxtral perception/voice; Small Creative explicitly preserves creative writing and character interaction.

---

# 🧬 Meta — Llama

### Evolution line
`LLaMA research foundation → Llama 2 assistant/open → Llama 3/3.1/3.2 ecosystem → Llama 4 Scout/Maverick/Behemoth direction`

Meta matters not only for chat quality but for **open infrastructure + local/self-hosted intelligence**. Llama 4 moves toward native multimodal MoE; Scout toward extreme context; Maverick toward efficient multimodal intelligence; Behemoth toward a teacher-model approach.

For Velantrim this supports a core idea: **the LLM can be a replaceable cognitive processor while the system remains persistent**.

---

# 🀄 Z.ai — GLM

### Evolution line
`GLM-4.x → GLM-4.5 / Air → GLM-5.x long-horizon generations`

GLM-4.5 was explicitly built for agent-oriented applications across code, reasoning, tools, browsing and software engineering. Air demonstrates heavy/efficient tiering; later generations continue toward long-horizon engineering.

---

# 🌊 MiniMax

### Evolution line
`dialogue/role-play heritage → M2 agent-first → M2.1 coding → M2.5 productivity → M2.7 self-evolution + Agent Teams → M3 line`

MiniMax is notable because it does **not fully collapse Human and Agent directions**. M2-her remains a dialogue/role-play branch with emotional expression while M2/M2.5 develop code/tools/productivity and M2.7 develops Agent Teams/self-evolution. This closely resembles the Velantrim thesis.

---

# 📊 Evolution matrix

| Family | Earlier identity | Transition | Current direction | ❤️ Preserve | ⚙️ Agentic trajectory |
|---|---|---|---|---|---|
| Claude | deep conversational intelligence | reasoning + coding | long-horizon agents | very important | ⬆⬆⬆ |
| GPT/ChatGPT | universal chat | multimodal + reasoning | professional/Codex agents | very important | ⬆⬆⬆ |
| Grok | personality/wit | expressive Voice → Think Fast reasoning | production voice/tools/agents | **presence, depth, personality** | ⬆⬆⬆ |
| Gemini | multimodal assistant | huge context + thinking | multimodal agents | important | ⬆⬆⬆ |
| DeepSeek | efficient/open | R1 reasoning | Pro/Flash roles | under-measured | ⬆⬆⬆ |
| Kimi | long-context assistant | coding + thinking | swarm/long-horizon | under-measured | ⬆⬆⬆ |
| Qwen | broad open family | coder + reasoning | agent-trained ecosystem | under-measured | ⬆⬆⬆ |
| Mistral | efficient open | Small/Medium/Large | specialist cognitive stack | explicitly preservable | ⬆⬆⬆ |
| Llama | open research | assistant ecosystem | multimodal/local infrastructure | under-measured | ⬆⬆ |
| GLM | general/open | code/reasoning | long-horizon agents | under-measured | ⬆⬆⬆ |
| MiniMax | dialogue/role-play | agent-first | agent teams/productivity | separate branch | ⬆⬆⬆ |

---

# ❤️↔️⚙️ Core conclusion

The history is **not simply “models became less human.”** A more defensible description is:

> **The optimization target expanded and shifted.**

The industry moved from proving that machines could converse convincingly toward proving that AI can **reason, code, operate tools and computers, coordinate agents, finish long tasks, and deliver reliable work at production cost**.

That is genuine progress. But qualities absent from engineering benchmarks can drift unnoticed.

```text
                 MODEL EVOLUTION
                       │
          ┌────────────┴────────────┐
          ▼                         ▼
 ❤️ Interaction Intelligence    🧠 Capability Intelligence
 presence                       reasoning
 dialogue                       coding
 humor                          tools
 explanation                    agents
 creativity                     verification
 continuity                     execution
          │                         │
          └────────────┬────────────┘
                       ▼
               🧭 Cognitive Router
                       │
                       ▼
               💾 Persistent System
```

## Architectural rule

**A new model earns a role; it does not automatically inherit every role of the previous model.**

If a new model improves coding by 20% but regresses on conversational continuity, it becomes the new **Coder**, not automatically the new **Human Interface**.

Last research refresh: **2026-08-17**.
