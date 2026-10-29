# Роадмап: AI-разработка

> Теги: roadmap, AI, ИИ, нейросети, LLM, AI engineer, AI-assisted coding, vibe coding, вайб-кодинг, Claude Code, Cursor, Copilot, Codex, prompt engineering, context engineering, CLAUDE.md, AGENTS.md, skills, subagents, hooks, MCP, Model Context Protocol, RAG, эмбеддинги, embeddings, векторная БД, pgvector, AI-агенты, function calling, tool use, structured output, evals, LangChain, Vercel AI SDK, prompt injection, как встроить ChatGPT в приложение, AI пишет плохой код
> Основа: roadmap.sh (AI Engineer, AI Agents, Claude Code, Vibe Coding, AI Product Builder, AI and Data Scientist, AI-разделы Frontend и Backend) + дополнения. Проверено 2026-10-24.

## Определение

AI-разработка в контексте fullstack JS — два навыка: **(1) AI-assisted coding** — эффективная и безопасная работа с AI-ассистентами (Claude Code, Cursor, Copilot) при написании кода; **(2) AI engineering** — встраивание LLM в продукт: вызовы API моделей, prompt и context engineering, RAG, агенты, MCP, оценка качества (evals). Обучение собственных моделей (ML / Data Science) — отдельная профессия, здесь только упоминается.

## Зачем / когда использовать

- **Часть 1** — с первого дня обучения, но в роли ментора: объяснить ошибку, сделать ревью, подсказать тему. AI не должен писать код за тебя, пока не сформирован навык — иначе навык не появится.
- **Часть 1 в полную силу** — после [JavaScript](roadmap.javascript.md) и [TypeScript](roadmap.typescript.md), когда ты можешь проверить и понять сгенерированный код.
- **Часть 2** — после [Node.js](roadmap.nodejs.md) и [Backend](roadmap.backend.md): AI-фичи — это backend-интеграция.

## Основное

### Часть 1. AI-assisted coding

#### 1.1 Основы

- [ ] **J** Как работают LLM на уровне идеи — токены, контекстное окно, вероятностная генерация, галлюцинации, knowledge cutoff.
- [ ] **J** AI vs традиционная разработка — что делегировать, что делать самому; vibe coding — что это и чем опасен.
- [ ] **J** Инструменты — агенты в терминале (Claude Code, Codex CLI, Gemini CLI), AI-редакторы (Cursor, Windsurf, Copilot в VS Code), AI app builders (v0, Lovable, Bolt, Replit) — для прототипов.
- [ ] **J** Модели и цена — семейства (Claude Opus / Sonnet / Haiku, GPT, Gemini), когда какую выбирать, подписка vs оплата API по токенам.

#### 1.2 Рабочий процесс

- [ ] **J** Сначала план, потом код — MVP, фазы, шаги; plan mode; spec-driven development (спецификация → реализация).
- [ ] **J** Популярный стек вместо нишевого — AI знает его лучше.
- [ ] **J** Стандарты с первого дня — внимательно ревьюить первые результаты: плохие паттерны AI будет повторять и умножать.
- [ ] **J** Регулярный рефакторинг — AI идёт по пути наименьшего сопротивления (дописывает, раздувает файлы); просить разбить на модули и удалить мёртвый код.
- [ ] **J** Промптинг — конкретно, одна задача за раз, примеры и макеты, что НЕ делать, «сначала подумай / предложи варианты» для сложных задач.

#### 1.3 Контекст

- [ ] **J** Контекст-файлы — `CLAUDE.md`, `AGENTS.md`, правила Cursor: стек, команды, соглашения; обновлять, когда повторяешь одно и то же.
- [ ] **J** Чистить контекст — новая задача → новая сессия (`/clear`), `/compact` для длинных сессий; если AI не справился за 3 попытки — начать заново.
- [ ] **M** Навигация по коду — LSP, поиск, repo map → [семантическая навигация для AI](../a.ai/ai.code-navigation.md).

#### 1.4 Качество, Git, безопасность

- [ ] **J** Git как страховка — чистая ветка на фичу, коммит после каждой успешной задачи, откат через Git, а не через «undo» AI → [Git](roadmap.git.md).
- [ ] **J** Тесты по умолчанию — просить тесты сразу; для бага — сначала падающий тест, потом исправление; TDD с AI работает хорошо.
- [ ] **J** Отладка — дать AI ошибку и код, но понять причину; просить логи и список гипотез; Chrome DevTools MCP / Playwright MCP для проверки в браузере ([ai.chrome-devtools](../a.ai/ai.chrome-devtools.md)).
- [ ] **J** Секреты — никогда в коде, только переменные окружения; просить AI провести аудит безопасности.
- [ ] **J** Ревью AI-кода как чужого PR — [code review](roadmap.git.md), линтеры и CI обязательны.

#### 1.5 Claude Code глубже

- [ ] **M** Запуск — `claude`, `claude "query"`, `claude -p` (headless), `-c` / `-r` (продолжить / возобновить сессию); desktop-приложение, расширения для IDE.
- [ ] **M** Команды — `/init`, `/clear`, `/compact`, `/context`, `/model`, `/permissions`, `/rewind`, `/mcp`, `/agents`, `/hooks`; префиксы `!` (shell), `@` (файл); Shift+Tab — режимы (plan, auto accept).
- [ ] **M** Расширение — skills (повторяемые инструкции), subagents (изолированный контекст под задачу), hooks (`PreToolUse`, `PostToolUse`, `SessionStart`…), plugins, MCP-серверы, output styles, status line.
- [ ] **M** Масштабирование — git worktrees для параллельных агентов, headless-режим в CI, scheduled jobs и loops.
- [ ] **M** Экономия — выбор модели под задачу (Opus — планирование, Sonnet — реализация, Haiku — простое), thinking / effort, prompt caching, осторожность с расширениями (они едят контекст).
- [ ] **M** Безопасность — режимы разрешений, sandbox, не запускать непроверенные MCP и скрипты.

### Часть 2. AI engineering — LLM в продукте

#### 2.1 Основы LLM

- [ ] **M** Термины — LLM, инференс vs обучение, pre-trained модели, токены, контекст, эмбеддинги, AI vs AGI.
- [ ] **M** Параметры генерации — temperature, top-p, top-k, max tokens, stop sequences, penalties.
- [ ] **M** Закрытые модели (Claude, GPT, Gemini) vs открытые (Llama, Qwen, Gemma, Mistral, DeepSeek); локальный запуск — Ollama, LM Studio; агрегаторы — OpenRouter; Hugging Face.
- [ ] **M** Reasoning vs обычные модели; streaming; ценообразование по токенам.

#### 2.2 Работа с API

- [ ] **M** API провайдеров — Claude Messages API, OpenAI Responses API, Gemini API; OpenAI-совместимые API.
- [ ] **M** SDK для JS — официальные SDK (`@anthropic-ai/sdk`, `openai`), **Vercel AI SDK** (единый интерфейс, streaming в React / Next.js).
- [ ] **M** Streaming ответов (SSE) в UI.
- [ ] **M** Structured outputs — JSON по схеме (Zod).
- [ ] **M** Function calling / tool use — модель вызывает твои функции.
- [ ] **M** Prompt caching, обработка ошибок и rate limit, ретраи, таймауты.

#### 2.3 Prompt и context engineering

- [ ] **M** Анатомия промпта — system prompt, роль и поведение, контекст, ограничения, формат вывода.
- [ ] **M** Техники — zero-shot, few-shot, chain of thought, ReAct.
- [ ] **M** Context engineering — что и в каком порядке класть в контекст: источники, сжатие (compaction), изоляция, история и состояние, failure modes (переполнение, «отравление» контекста).

#### 2.4 Эмбеддинги и RAG

- [ ] **M** Эмбеддинги — что это; применение: семантический поиск, рекомендации, классификация, поиск аномалий.
- [ ] **M** Модели эмбеддингов — OpenAI, Voyage, Cohere, Gemini, open source (Sentence Transformers).
- [ ] **M** Векторные БД — **pgvector** (PostgreSQL, начать с него), Qdrant, Pinecone, Chroma, Weaviate, MongoDB Atlas Vector Search.
- [ ] **M** RAG — chunking → embedding → хранение → retrieval (+ гибридный поиск, reranking) → generation; RAG vs fine-tuning; динамические фильтры.
- [ ] **S** Фреймворки *(опц.)* — LangChain.js, LlamaIndex.TS; часто достаточно SDK напрямую.

#### 2.5 AI-агенты

- [ ] **M** Что такое агент — цикл: ввод → рассуждение и план → вызов инструмента → наблюдение → повтор.
- [ ] **M** Инструменты (tools) — имя и описание, input / output schema, обработка ошибок; примеры: веб-поиск, выполнение кода, запросы к БД и API, файловая система.
- [ ] **M** Память агента — краткосрочная (в промпте) и долгосрочная (векторная / SQL), суммаризация, забывание.
- [ ] **M** Архитектуры — ReAct, planner-executor, RAG-агент, self-critique, multi-agent.
- [ ] **M** Реализация — вручную (агентный цикл на SDK) или фреймворки: Claude Agent SDK, OpenAI Agents SDK, LangGraph, Mastra; CrewAI, AutoGen — Python *(опц.)*.

#### 2.6 MCP (Model Context Protocol)

- [ ] **M** Архитектура — host, client, server; слои данных и транспорта (stdio, Streamable HTTP).
- [ ] **M** Сущности сервера — tools, resources, prompts.
- [ ] **M** Свой MCP-сервер на TypeScript SDK; подключение к Claude Code / Cursor; локальный vs удалённый деплой.

#### 2.7 Evals и наблюдаемость

- [ ] **S** Оценка качества — детерминированные проверки, LLM-as-judge, человеческая оценка; регрессионные тесты промптов; метрики RAG.
- [ ] **S** Инструменты — Langfuse, LangSmith, Helicone, Arize; DeepEval, RAGAS; promptfoo *(опц.)*.
- [ ] **S** Мониторинг в проде — трейсинг вызовов, стоимость и задержка, качество ответов.

#### 2.8 Безопасность и этика

- [ ] **M** Prompt injection (прямой и через данные — документы, веб-страницы), jailbreak.
- [ ] **M** Песочница и права для инструментов агента, human-in-the-loop для опасных действий.
- [ ] **M** Приватность — не отправлять PII и секреты в модель, маскирование; модерация контента; ограничение входа и выхода.
- [ ] **S** Bias, adversarial / red team тестирование.

#### 2.9 Мультимодальность *(опц.)*

- [ ] **S** Понимание изображений (vision), генерация изображений, speech-to-text (Whisper), text-to-speech, видео.

### Цикл AI-продукта (AI Product Builder)

- [ ] **M** Прототип (определить проблему, скоуп, стек) → генерация (AI app builder или агент) → доработка (точечные изменения vs структурные) → совместная работа (Git, CI) → тестирование (unit, интеграционные, e2e, пользовательские) → деплой (Vercel / Cloudflare / AWS, БД — Supabase / PostgreSQL) → повторять цикл.

### Дальше *(опц.)*

- [ ] Data Science и ML — математика, статистика, Python, классический ML, deep learning, MLOps (roadmap.sh: AI and Data Scientist) — отдельная профессия.
- [ ] Fine-tuning моделей, inference engineering.

### Чекпоинты

- [ ] **AI-assisted:** проект в Claude Code с `CLAUDE.md`, тестами, хуком на линтер и чистой историей коммитов.
- [ ] **AI-фича:** чат по своим документам — Next.js + Vercel AI SDK + streaming + RAG на pgvector + structured output.
- [ ] **Агент / MCP:** свой MCP-сервер к своему API, подключённый к Claude Code.

## Подводные камни

- Принимать код от AI без понимания — накапливается долг, который никто не может поддерживать.
- AI на этапе обучения пишет вместо тебя — навык не формируется.
- Длинная сессия со всем подряд в контексте — качество падает; чистить контекст.
- Доверять ответу модели как источнику истины — проверять версии API и факты по документации (у модели knowledge cutoff).
- Отдавать агенту права без ограничений (`rm`, деплой, прод-БД) и непроверенные MCP-серверы.
- Строить RAG / агента там, где хватит одного хорошего промпта.
- Нет evals — любое изменение промпта или модели ломает поведение незаметно.

## Ссылки

- Предыдущий: [Terraform](roadmap.terraform.md) (или с любого этапа — роадмап параллельный) · Старт: [Fullstack](roadmap.0-fullstack.md)
- Файлы базы: [семантическая навигация по коду для AI](../a.ai/ai.code-navigation.md), паттерны: [LLM-приложения](../c.patterns/patterns.ai-llm.md), [AI-агенты](../c.patterns/patterns.ai-agents.md), [AI-friendly код](../c.patterns/patterns.ai-friendly-code.md), [вопросы к собеседованию](../c.patterns/patterns.ai-interview.md)
- roadmap.sh: [AI Engineer](https://roadmap.sh/ai-engineer), [AI Agents](https://roadmap.sh/ai-agents), [Claude Code](https://roadmap.sh/claude-code), [Vibe Coding](https://roadmap.sh/vibe-coding), [AI and Data Scientist](https://roadmap.sh/ai-data-scientist)
- [Claude Code docs](https://code.claude.com/docs), [Anthropic docs](https://docs.claude.com/), [MCP](https://modelcontextprotocol.io/), [Vercel AI SDK](https://ai-sdk.dev/)
