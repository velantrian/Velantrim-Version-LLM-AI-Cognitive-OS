# 🧬 Эволюция семейств моделей — от разговорного AI к когнитивным и агентным системам

🌐 Язык / Language: [🇬🇧 English](../MODEL_FAMILY_EVOLUTION.md) · **🇷🇺 Русский**

> Здесь отслеживаются **семейства и поколения**, а не только сегодняшние флагманы. Главный вопрос: *что каждое поколение приобрело, какие качества взаимодействия изменились и как индустрия смещала оптимизацию от разговора/характера к reasoning, coding, tools, agents и production reliability?*

## ⚠️ Дисциплина доказательств

- 🟢 **Official** — документация, релиз или system card производителя.
- 🔬 **Independent** — воспроизводимая сторонняя оценка.
- 👥 **Community** — повторяющиеся пользовательские наблюдения; сигнал, но не доказательство.
- ⚪ **Гипотеза Velantrim** — архитектурная интерпретация, которую необходимо тестировать.
- `?` означает нехватку данных, **а не низкое качество**.

Оси ❤️ Human Presence и ⚙️ Engineering/Agentic намеренно независимы. Новее ≠ лучше во всём; старее ≠ автоматически человечнее.

---

## 🗺️ Общая траектория индустрии

```text
✨ Chat / personality / wow-effect
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
🏢 production / enterprise / cost-per-task / reliability
        ↓
❤️↔️🧠 тезис Velantrim:
сохранять Interaction Intelligence,
пока Capability Intelligence продолжает расти
```

---

# 🟠 Anthropic — Claude

### Линия
`Claude 2 → Claude 3 Haiku/Sonnet/Opus → 3.5 Sonnet → 3.7 Sonnet → Claude 4 Sonnet/Opus → Sonnet 4.5 / Opus 4.5 → Opus/Sonnet 4.6–4.8 → Sonnet 5-era`

Claude 3 Opus — важный исторический эталон тонкого, философского, игривого и эмоционально чувствительного общения. Затем семейство всё сильнее двигалось в reasoning, coding, computer use, subagents и длительную автономную работу. Это один из лучших примеров того, почему **рост capability и изменение interaction phenotype надо измерять раздельно**.

---

# 🟢 OpenAI — GPT / ChatGPT / o-series / Codex

### Линия
`GPT-3.5 chat → GPT-4 → GPT-4 Turbo → GPT-4o multimodal/voice → o-series reasoning → GPT-5 routed reasoning → GPT-5.x professional work → Codex agent stack`

Ранний ChatGPT сделал массовым разговорный интерфейс. GPT-4o усилил realtime multimodality и Voice. o-series сделал test-time reasoning отдельной осью. GPT-5-era развивает routing между быстрым и глубоким мышлением. Codex эволюционирует от генерации кода к **agentic software engineering** и длинным задачам.

Критический урок GPT-4o: rollback из-за sycophancy показывает, что **приятнее ≠ человечнее и лучше**. Truthfulness, tact и calibrated disagreement должны быть отдельными целями.

---

# 🚀 xAI / SpaceXAI — Grok + Grok Voice

### Линия
`early Grok personality → Grok 2/3 reasoning → Grok 4/4.1 agent tools → expressive Grok Voice → Voice Think Fast 1.0 → Voice Think Fast 2.0 → Grok 4.5 flagship`

Ранний Grok выделялся характером, неформальностью и юмором. Ранний Voice — выразительным присутствием. Более поздние поколения усилили reasoning/coding, а Grok 4.1 Fast + Agent Tools и Voice Think Fast явно двинулись в production tool-calling, low latency, support/sales/enterprise workflows.

Вопрос Velantrim: **исчезла ли часть presence или просто поменялся default behavior?** Это надо проверять Behavioral Museum, а не решать по воспоминаниям.

---

# 💎 Google — Gemini

### Линия
`Gemini 1.x multimodal → Gemini 1.5 long context → Gemini 2.x/Flash → Gemini 2.5 Pro/Flash thinking → Gemini 3.x/3.6 Flash agentic production line`

Gemini прошёл путь **multimodal assistant → huge-context model → reasoning substrate → multimodal agent worker platform**. Multimodality и большой контекст стали фундаментом, затем thinking и Flash-линия сделали reasoning и high-throughput execution основными production-режимами.

---

# 🐋 DeepSeek

### Линия
`V2/V2.5 → V3 → R1 reasoning → V3.2 thinking/non-thinking → V4 Pro + V4 Flash`

DeepSeek сначала резко выделился эффективностью и открытостью, затем R1 — reasoning. V3.x сблизил thinking/non-thinking, а V4 формализует role split: **Pro = тяжёлый мозг**, **Flash = быстрый worker**. Это прямое подтверждение role-based routing.

---

# 🌙 Moonshot AI — Kimi

### Линия
`long-context Kimi → Kimi-VL / Dev / Researcher → K2 → K2 Thinking → K2.5 → Agent Swarm → K2.6 → K3`

Kimi начинал с идентичности long-context assistant. Затем контекст превратился из «много токенов» в рабочую среду для coding/agents. K2 Thinking усилил reasoning и multi-step tools; K2.5/2.6 объединили multimodality, dialogue, thinking и agents; Agent Swarm формализовал параллельную работу; K3 масштабирует эту линию до open 3T-class, native vision и 1M context.

---

# 🟣 Alibaba — Qwen

### Линия
`Qwen/Qwen1.5 → Qwen2 → Qwen2.5 + Coder → QwQ reasoning → Qwen3 hybrid thinking → Qwen3-Coder → Coder-Next → Qwen3-Max-Thinking`

Qwen эволюционировал из широкой open-weight семьи в **специализированную открытую когнитивную экосистему**. Qwen2.5-Coder усилил код; QwQ/Qwen3 — reasoning; Qwen3-Coder — agentic coding/browser/tool use; Coder-Next масштабирует agentic training signals и обучение в executable environments; Max-Thinking соединяет масштабный RL, test-time scaling и adaptive tools.

---

# 🇫🇷 Mistral AI

### Линия
`Mistral 7B / Mixtral → Small/Medium/Large → Large 2.x → Small 3.x / Medium 3.x → Devstral + Magistral + specialists → Large 3 / Medium 3.5 / Small 4 / Ministral 3 / Vibe`

Mistral особенно важен для Velantrim: вместо одного «всего умеющего» checkpoint компания фактически строит **портфель ролей**. Large — generalist; Medium — frontier/cost-efficient enterprise; Small — efficient worker; Devstral — SWE agents; Magistral — reasoning; Ministral — local/edge; OCR/Voxtral — perception/voice; Small Creative — отдельное сохранение creative writing и character interaction.

Это один из самых чистых примеров специализации когнитивного стека.

---

# 🧬 Meta — Llama

### Линия
`LLaMA research foundation → Llama 2 assistant/open → Llama 3/3.1/3.2 ecosystem → Llama 4 Scout/Maverick/Behemoth direction`

Meta важна не только качеством конкретного чата, а стратегией **open infrastructure + local/self-hosted intelligence**. Llama 4 переводит семейство к native multimodal MoE; Scout — к экстремально длинному контексту, Maverick — к эффективной multimodal intelligence, Behemoth — к teacher-model подходу.

Для Velantrim это база идеи: **LLM может быть заменяемым cognitive processor, а система — постоянной**.

---

# 🀄 Z.ai — GLM

### Линия
`GLM-4.x → GLM-4.5 / Air → GLM-5.x long-horizon generations`

GLM-4.5 уже официально проектировался для agent-oriented applications: code, reasoning, tool invocation, browsing, software engineering. Air показывает tiering тяжёлой и эффективной модели. Поздняя линия продолжает движение к long-horizon engineering.

---

# 🌊 MiniMax

### Линия
`dialogue/role-play heritage → M2 agent-first → M2.1 coding → M2.5 productivity → M2.7 self-evolution + Agent Teams → M3 line`

MiniMax особенно интересен тем, что **не полностью смешивает Human и Agent направления**. M2-her остаётся отдельной dialogue/role-play моделью с emotional expression, тогда как M2/M2.5 развивают code/tools/productivity, а M2.7 — Agent Teams и self-evolution. Это почти готовый пример архитектурного тезиса Velantrim.

---

# 📊 Матрица эволюции

| Семейство | Ранняя идентичность | Переход | Современное направление | ❤️ Что важно сохранить | ⚙️ Agentic trajectory |
|---|---|---|---|---|---|
| Claude | глубокий собеседник | reasoning + coding | long-horizon agents | очень важно | ⬆⬆⬆ |
| GPT/ChatGPT | универсальный чат | multimodal + reasoning | professional/Codex agents | очень важно | ⬆⬆⬆ |
| Grok | характер/юмор | reasoning + voice | production voice/tools/agents | очень важно | ⬆⬆⬆ |
| Gemini | multimodal assistant | huge context + thinking | multimodal agents | важно | ⬆⬆⬆ |
| DeepSeek | efficient/open | R1 reasoning | Pro/Flash roles | мало измерено | ⬆⬆⬆ |
| Kimi | long-context assistant | coding + thinking | swarm/long-horizon | мало измерено | ⬆⬆⬆ |
| Qwen | broad open family | coder + reasoning | agent-trained ecosystem | мало измерено | ⬆⬆⬆ |
| Mistral | efficient open | Small/Medium/Large | specialist cognitive stack | явно можно сохранить | ⬆⬆⬆ |
| Llama | open research | assistant ecosystem | multimodal/local infrastructure | мало измерено | ⬆⬆ |
| GLM | general/open | code/reasoning | long-horizon agents | мало измерено | ⬆⬆⬆ |
| MiniMax | dialogue/role-play | agent-first | agent teams/productivity | отдельная ветка | ⬆⬆⬆ |

---

# ❤️↔️⚙️ Главный вывод

История **не сводится к «модели стали менее человечными»**. Более точная формулировка:

> **Изменился и расширился объект оптимизации.**

Раньше индустрия доказывала, что машина способна убедительно разговаривать. Теперь она доказывает, что AI способен **рассуждать, программировать, использовать инструменты и компьютер, координировать агентов, завершать многочасовые задачи и выдавать надёжный результат с приемлемой стоимостью**.

Это реальный прогресс. Но качества, которые не входят в engineering benchmarks, могут незаметно дрейфовать.

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

## Архитектурный закон

**Новая модель получает роль — она не наследует автоматически все роли предыдущей модели.**

Если новая модель стала на 20% лучше в coding, но хуже держит conversational continuity, она становится новым **Coder**, а не автоматически новым **Human Interface**.

Последнее исследовательское обновление: **2026-08-17**.
