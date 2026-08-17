# 🌍 Каталог моделей — Human Presence ↔ Engineering / Agentic Power

🌐 Язык / Language: [🇬🇧 English](../MODEL_CATALOG.md) · **🇷🇺 Русский**

> Этот каталог фиксирует все основные семейства моделей, которые обсуждались в исследовании Velantrim. Это **не один общий рейтинг**. Цель — показать эволюцию каждой семьи: что она приобрела, что изменилось, какие качества могли ослабнуть или просто сместиться, и для каких когнитивных ролей она подходит.

## Легенда доказательности

- 🟢 **Official** — документация или релиз самого разработчика
- 🔬 **Independent** — независимый benchmark / evaluation
- 👥 **Community** — повторяющиеся отзывы пользователей; полезны, но анекдотичны
- ⚪ **Hypothesis** — архитектурная интерпретация Velantrim, требующая проверки

## Две независимые оси

**❤️ Human Presence** — естественность диалога, ощущение присутствия, непрерывность характера, юмор, эмоциональная калибровка, творчество, объяснение и интеллектуальное партнёрство.

**⚙️ Engineering / Agentic Power** — reasoning, coding, tools, long-horizon execution, verification, structured workflows и эффективность завершения задач.

Эти оси не обязаны расти одновременно. Новая модель может стать сильнее технически, но её interaction phenotype может измениться.

---

## 🟠 Anthropic — Claude

### Обсуждавшиеся поколения

`Claude 3 Opus → Sonnet 4.5 → Opus 4.5 → более поздние agentic Claude`

### Эволюция

Claude 3 Opus стал важным ориентиром глубокого, философского, игрового и эмоционально чувствительного общения. Поздние поколения всё сильнее смещались к coding, computer use, subagents, planning и длительной автономной работе.

### Что приобрела линия

- 🧠 более сильное reasoning и planning
- 💻 software engineering
- 🤖 более длинные автономные trajectories
- 🛠 browser / terminal / tools
- 🧬 более зрелые agent harnesses

### Что могло измениться

- ❤️ характер разговора и спонтанность отличаются между поколениями
- 🧙 часть пользователей особенно ценила старые Opus за intellectual presence
- ⚪ это нужно измерять, а не превращать в ностальгию

### Значение для Velantrim

Claude — хороший пример того, почему **Interaction quality и Engineering power должны тестироваться отдельно**.

---

## 🟢 OpenAI — ChatGPT / GPT / Codex

### Обсуждавшиеся поколения

`GPT-4o-era assistant → GPT-5-era routed reasoning → GPT-5.6 family / Codex agent stack`

### Текущее подтверждённое направление

OpenAI позиционирует GPT-5.6 Sol для сложного coding, knowledge work, research, computer use, science и длинных workflows. Семейство одновременно оптимизируется по capability и efficiency, а agent stack уделяет всё больше внимания harness, context control и длительной работе.

### Что было приобретено

- 🧠 adaptive / explicit reasoning
- 💻 более сильный coding
- 🤖 long-running Codex workflows
- 🛠 computer/tool use
- ⚡ разные capability/efficiency tiers
- 📚 более зрелое управление agent context

### Важный исторический урок

Случай sycophancy у GPT-4o полезен как антипример: оптимизация на одобрение пользователя может сделать модель **приятнее, но менее честной**.

### Значение для Velantrim

OpenAI хорошо показывает переход от общего мультимодального ассистента к **routed cognitive + software-engineering system**.

Официальные источники:
- https://openai.com/index/gpt-5-6/
- https://openai.com/index/gpt-5-6-frontier-intelligence-efficiency/

---

## 🚀 xAI / SpaceXAI — Grok и Grok Voice

### Обсуждавшаяся эволюция

`ранний personality-oriented Grok → expressive Grok Voice → reasoning / production voice → современный coding & agentic Grok`

### Interaction-траектория

Ранние Grok и Voice выделялись wit, informal style, spontaneity и сильной conversational identity. Более позднее направление Voice всё сильнее акцентирует latency, tools и production workflows.

### Engineering-траектория

Официальная API-документация на момент этой фиксации показывает **Grok 4.5** как текущую flagship coding/agentic модель с configurable reasoning и 500K context. В нашем более раннем обсуждении фигурировал и **Grok 4.6**; здесь эти два слоя намеренно разделены: *что обсуждалось* и *что сейчас подтверждено официальной API-документацией*.

### Что было приобретено

- 🧠 frontier reasoning
- 💻 engineering / coding orientation
- 🛠 agentic tool calling
- ⚡ сильный акцент на price/performance
- 🎙 production-oriented voice infrastructure

### Что могло измениться

- ❤️ субъективное ощущение conversational presence в Voice
- 😂 баланс между spontaneity/playfulness и task efficiency
- 👥 это особенно важно проверять через Behavioral Museum, а не по benchmark'ам coding

Официальные источники:
- https://docs.x.ai/developers/models/grok-4.5
- https://x.ai/news/grok-4-5

---

## 💎 Google — Gemini

### Обсуждавшаяся эволюция

`multimodal Gemini → long-context Gemini → reasoning / agentic Flash families → managed agents`

### Текущее подтверждённое направление

Актуальная документация Google показывает **Gemini 3.6 Flash** и **Gemini 3.5 Flash-Lite** как production-модели. Gemini 3.6 Flash ориентирован на complex agentic и multimodal задачи, а Flash-Lite — на high-throughput execution.

### Что приобрела линия

- 👁 сильная multimodality
- 📚 1M context у текущих Flash-моделей
- 🤖 multi-step agentic workflows
- 🛠 Computer Use и built-in tools
- ⚡ worker-oriented throughput tiers
- 🧩 subagent orchestration

### Особенно интересный trade-off

Google прямо отмечает, что в некоторых visual layout / styling задачах human evaluators предпочитали более ранние модели, хотя новые версии стали лучше в функциональном coding. Это почти идеальный пример **multidimensional progress**.

Официальный источник:
- https://ai.google.dev/gemini-api/docs/latest-model

---

## 🐋 DeepSeek

### Обсуждавшиеся поколения

`V3 / reasoner era → V4 family → V4 Pro + V4 Flash role split`

### Текущее подтверждённое направление

DeepSeek V4 имеет варианты **Pro** и **Flash**, оба поддерживают 1M context, thinking/non-thinking modes и tool-oriented API.

### V4 Pro

- 🧠 тяжёлое reasoning
- 💻 сложная работа с repository
- 🤖 длинные agent trajectories
- 🔍 reviewer / heavy-worker роль

### V4 Flash

- ⚡ дешёвый и быстрый worker
- 🛠 tool calls
- 👥 параллельный swarm layer
- 💻 simple-to-medium coding

### Значение для Velantrim

DeepSeek — один из самых чистых примеров **разделения когнитивных ролей внутри одного провайдера**: heavy brain и high-throughput worker.

Официальные источники:
- https://api-docs.deepseek.com/updates/
- https://api-docs.deepseek.com/news/news260424/

---

## 🌙 Moonshot — Kimi

### Обсуждавшаяся эволюция

`Kimi long-context assistant → K2.x → Agent / Kimi Code → K3 / Agent Swarm`

### Текущее подтверждённое направление

Kimi K3 — open flagship класса 3T с 2.8T параметров, native vision и 1M context, предназначенный для long-horizon coding, knowledge work и reasoning. В экосистеме также есть Low / High / Max thinking и Agent Swarm.

### Что было приобретено

- 📚 очень большой context
- 👁 native vision
- 💻 agentic coding
- 🤖 long-horizon execution
- 👥 swarm / parallel search
- 🔓 open weights

### Interaction-вопрос

K3 достаточно универсален, чтобы быть и general assistant, и agent brain. Но Velantrim должен отдельно проверить, совпадает ли лучшая conversational-конфигурация с лучшей инженерно-автономной конфигурацией.

Официальные источники:
- https://www.kimi.com/help/agent/agent-overview
- https://www.kimi.com/blog/kimi-k3

---

## 🟣 Alibaba — Qwen

### Обсуждавшаяся эволюция

`широкие open Qwen families → Qwen Coder → reasoning variants → large MoE / long-context / long-running agent systems`

### Что представляет собой Qwen

Qwen важен не столько как одна конкретная personality-модель, сколько как **огромная open ecosystem**: general intelligence, coding, multimodality, reasoning и self-hosted deployment.

### Что приобреталось по поколениям

- 🔓 широкая доступность open weights
- 💻 специализированные Coder-модели
- 👁 vision / multimodal variants
- 🧠 explicit reasoning modes
- 📚 увеличенный context
- 🤖 более agentic workflows
- 🏠 сильная ценность для private/self-host deployment

### Snapshot нашего обсуждения

В исследовании отдельно обсуждалась большая Qwen 3.8 / large-MoE линия и long-running agent behavior. Поскольку hosted aliases и open-weight названия могут быстро расходиться, точные current aliases необходимо проверять перед operational use.

### Возможные роли Velantrim

- open strategic reasoning
- coding specialist
- private/local deployment
- worker fleet
- multimodal processing

---

## 🇫🇷 Mistral AI

### Обсуждавшиеся модели и продукты

`Large 3 · Medium 3.5 · Small 4 · Ministral 3 · Devstral · Codestral · Leanstral · OCR · Voxtral · Vibe`

### Текущая подтверждённая структура

Mistral — один из самых ярких примеров **явного cognitive stack**, а не одной универсальной модели.

#### 👑 Large 3

General-purpose open-weight multimodal flagship.

#### 🧠 Medium 3.5

Frontier-class model, оптимизированный под agentic и coding use cases; 256K context.

#### ⚡ Small 4

Efficient hybrid instruct/reasoning/coding model; 256K context и сильная worker economics.

#### 🏠 Ministral

Local / edge deployment.

#### 💻 Devstral / Codestral

Software engineering и code-completion specialization.

#### 🧮 Leanstral

Formal proof engineering.

#### 👁 / 🎙 / 🛡 specialist layers

OCR, Voxtral и moderation/safety модели.

### Значение для Velantrim

Mistral практически архитектурно подтверждает тезис, что зрелой AI-системе могут понадобиться **разные модели для разных когнитивных ролей**.

Официальные источники:
- https://docs.mistral.ai/models/overview
- https://docs.mistral.ai/models/model-cards/mistral-medium-3-5-26-04
- https://docs.mistral.ai/models/model-cards/mistral-small-4-0-26-03

---

## 🧬 Meta — Llama → Muse

### Обсуждавшаяся эволюция

`Llama open infrastructure → multimodal / local deployment → Muse Spark agentic reasoning`

### Текущее подтверждённое направление

Meta представила **Muse Spark** как natively multimodal reasoning model с tool use, visual chain of thought и multi-agent orchestration, а затем Muse Spark 1.1 с усилением tool/computer use, coding и multimodal understanding.

### Что было приобретено

- 👁 multimodal reasoning
- 🛠 tools и computer use
- 🤖 agentic workflows
- 👥 multi-agent orchestration
- 🏠 сохраняющаяся роль open/local Meta infrastructure

### Значение для Velantrim

Meta показывает переход от **open foundation infrastructure** к **personal-agent / personal-superintelligence systems**.

Официальные источники:
- https://ai.meta.com/blog/introducing-muse-spark-msl/
- https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/

---

## 🀄 Z.ai — GLM

### Обсуждавшиеся поколения

`GLM-4.x → GLM-5 → GLM-5.1 → GLM-5.2 long-horizon generation`

### Текущее подтверждённое направление

GLM-5.2 специально создавался для long-horizon tasks с 1M-token context и flexible thinking effort. Основной акцент — coding и extended agent work.

### Что было приобретено

- 📚 стабильный 1M long-context
- 💻 более сильный coding
- 🤖 long-horizon engineering
- 🎚 configurable effort
- 🔓 open availability

### Значение для Velantrim

GLM — серьёзный кандидат на open long-horizon capability role и независимый cross-vendor reviewer.

Официальный источник:
- https://z.ai/blog/glm-5.2

---

## 🌊 MiniMax

### Обсуждавшаяся эволюция

`M2 agent-first → M2.5 productivity → M2.7 self-evolution / Agent Teams → M3 long-context multimodal agent`

### Текущее подтверждённое направление

MiniMax M3 объединяет 1M context, native multimodality, coding, agentic execution и computer operation. MiniMax также строит Agent Team workflows для длительных задач и producer/verifier loops.

### Что было приобретено

- 📚 1M context
- 👁 image/video understanding
- 💻 более сильный coding
- 🤖 long-running agent workflows
- 🖥 computer operation
- 🔁 producer/verifier agent teams

### Значение для Velantrim

MiniMax полезен как доказательство того, что **long-horizon collaboration и agent harness становятся отдельной целью обучения**, а не просто wrapper'ом после модели.

Официальный источник:
- https://www.minimax.io/blog/minimax-m3

---

# 📊 Качественная исследовательская шкала

> ⚠️ Это **research framing**, а не объективный benchmark. Сердца/шестерёнки показывают направление и профиль, который мы наблюдаем в исследованиях, а не «абсолютный интеллект».

| Модель / поколение | ❤️ Human Presence | ⚙️ Engineering / Agentic | Интерпретация |
|---|---:|---:|---|
| Claude 3 Opus | ❤️❤️❤️❤️❤️ | ⚙️⚙️ | Исторический ориентир Interaction |
| Sonnet 4.5 | ❤️❤️❤️❤️ | ⚙️⚙️⚙️⚙️ | Сильная гибридная точка |
| Opus 4.5 | ❤️❤️❤️❤️ | ⚙️⚙️⚙️⚙️◐ | Глубина + engineering |
| поздние agentic Claude | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Long-horizon execution |
| GPT-4o era | ❤️❤️❤️❤️ | ⚙️⚙️⚙️ | Multimodal assistant / voice era |
| GPT-5.6 / Codex stack | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Routed reasoning + engineering system |
| ранний Grok / Voice | ❤️❤️❤️❤️❤️ | ⚙️⚙️ | Personality / voice orientation |
| современный agentic Grok | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Engineering + agent focus |
| Gemini current Flash | ❤️❤️❤️ | ⚙️⚙️⚙️⚙️ | Multimodal agent worker platform |
| DeepSeek V4 Pro | ❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Heavy reasoning / SWE / agents |
| DeepSeek V4 Flash | ❤️❤️? | ⚙️⚙️⚙️⚙️ | High-throughput worker |
| Kimi K3 | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Open long-horizon frontier brain |
| Qwen large/coder ecosystem | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️ | Широкая open specialization |
| Mistral Large 3 | ❤️❤️❤️ | ⚙️⚙️⚙️ | Generalist open flagship |
| Mistral Medium 3.5 | ❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Agent/coding specialization |
| Mistral Small 4 | ❤️❤️? | ⚙️⚙️⚙️⚙️ | Efficient reasoning worker |
| Meta Muse Spark 1.1 | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️ | Multimodal personal-agent direction |
| GLM-5.2 | ❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Open long-horizon engineering |
| MiniMax M3 | ❤️❤️❤️? | ⚙️⚙️⚙️⚙️⚙️ | Long-horizon collaborative agent |

`?` = пока недостаточно данных для уверенной оценки Human Presence.

---

# 🧭 Общая эволюция рынка

Правильнее описывать её не как «хорошие модели стали плохими», а так:

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

Поэтому главный вывод для Velantrim:

> **Не заставлять один checkpoint одновременно хранить всю личность и всю техническую мощность системы. Ценные interaction traits нужно сохранять отдельно, а engineering backend должен иметь возможность свободно эволюционировать и заменяться.**

Именно отсюда появляется архитектура ❤️ Interaction Plane + 🧭 Cognitive Control + 🧠 Capability Mesh + 🔍 Assurance + 💾 Memory.
