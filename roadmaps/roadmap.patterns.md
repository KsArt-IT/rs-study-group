# Роадмап: Паттерны и архитектура (+ AI)

> Теги: roadmap, паттерны проектирования, design patterns, GoF, ООП, OOP, SOLID, GRASP, DRY, KISS, YAGNI, cohesion, coupling, закон Деметры, dependency injection, UML, C4, ADR, порождающие, структурные, поведенческие, антипаттерны, рефакторинг, архитектура ПО, clean architecture, hexagonal, DDD, модульный монолит, микросервисы, CQRS, Saga, outbox, идемпотентность, React паттерны, Feature-Sliced Design, backend паттерны, AI паттерны, LLM patterns, RAG, guardrails, evals, агенты, agentic workflows, MCP, context engineering, AI-friendly code, какие паттерны нужно знать, что учить по архитектуре, как писать поддерживаемый код
> Основа: itbooster.ru — Ulbi TV (Паттерны проектирования, Backend, React), roadmap.sh (Software Design and Architecture), Anthropic «Building effective agents», Fowler «Emerging Patterns in Building GenAI Products» + дополнения. Проверено 2026-10-25.

## Определение

**Паттерн проектирования** — типовое проверенное решение часто встречающейся задачи проектирования кода. **Архитектура ПО** — высокоуровневая структура системы: из каких частей она состоит, как они взаимодействуют и какие решения трудно изменить потом. **Принципы** (SOLID, DRY, KISS) — правила, помогающие принимать эти решения. **AI-паттерны** — те же идеи для систем с LLM: модель как внешняя зависимость, RAG, guardrails, агентные workflow.

## Зачем / когда использовать

- **Принципы и чистый код** — с первых проектов. **GoF и архитектура** — когда написано несколько приложений и видны проблемы, которые паттерны решают (обычно после [React](roadmap.react.md) и [Backend](roadmap.backend.md)). **AI-паттерны** — параллельно с [роадмапом AI](roadmap.ai.md), после backend-основ.
- Паттерн — инструмент, а не цель: применять, когда есть проблема.
- **Как читать:** пункт без пометки — **нужно fullstack JS + AI разработчику точно**; *(кругозор)* — для общего образования: знать, что это и когда применяют, глубоко — по необходимости. Уровни: **J** — junior, **M** — middle, **S** — senior.

## Основное

### 1. Основы ООП

- [ ] **J** Инкапсуляция, наследование, полиморфизм, абстракция; `#private`, классы как сахар над прототипами → [ООП](../c.patterns/patterns.oop.md), [вопросы](../2.js/js.oop-interview.md).
- [ ] **J** Композиция вместо наследования; is-a vs has-a; когда ООП, а когда функции.

### 2. Принципы качественного кода

- [ ] **J** [DRY](../c.patterns/patterns.dry.md), [KISS](../c.patterns/patterns.kiss.md), [YAGNI](../c.patterns/patterns.yagni.md) — и когда они вредят (ложное DRY, правило трёх).
- [ ] **J** [Clean Code](../c.patterns/patterns.clean-code.md) — имена, функции, комментарии, обработка ошибок, организация кода, TS-типы как документация.
- [ ] **J** [Code review](../c.patterns/patterns.code-review.md) — что смотреть, пирамида ревью, как писать замечания, Conventional Comments, чек-лист перед PR.
- [ ] **J** [SOLID](../c.patterns/patterns.solid.md) — с примерами в Node и React; DIP ≠ DI ≠ IoC.
- [ ] **J** [Принципы](../c.patterns/patterns.principles.md) — SoC, закон Деметры, CQS, fail fast и валидация на границе, POLA.
- [ ] **M** Coupling и cohesion; группировка кода по фичам → [GRASP](../c.patterns/patterns.grasp.md).
- [ ] **M** GRASP целиком — Information Expert, Creator, Controller, Pure Fabrication, Protected Variations *(кругозор)*.

### 3. Рефакторинг и антипаттерны

- [ ] **J** Code smells и базовые приёмы — Rename, Extract Function, guard clauses, объект параметров → [рефакторинг](../c.patterns/patterns.refactoring.md).
- [ ] **M** Безопасный рефакторинг — тесты, маленькие шаги, правило двух шляп; легаси без тестов (characterization tests, seam).
- [ ] **M** [Антипаттерны](../c.patterns/patterns.antipatterns.md) — God Object, спагетти, Golden Hammer, Cargo Cult, over-engineering, Big Ball of Mud.
- [ ] **M** Технический долг — квадрант Фаулера, как объяснить бизнесу; Strangler Fig, Branch by Abstraction.

### 4. Паттерны GoF

Сначала — [что такое паттерн, классификация и критика](../c.patterns/patterns.gof.md). Нужно точно — те, что каждый день встречаются в JS-коде и библиотеках:

| Группа | Нужно точно | *(кругозор)* |
|---|---|---|
| [Порождающие](../c.patterns/patterns.gof-creational.md) | Simple Factory, Factory Method, Builder (vs объект опций), Singleton — и почему его заменяют DI | Abstract Factory, Prototype, Object Pool |
| [Структурные](../c.patterns/patterns.gof-structural.md) | Adapter, Decorator, Facade, Proxy, Composite | Bridge, Flyweight |
| [Поведенческие](../c.patterns/patterns.gof-behavioral.md) | Strategy, Observer, Command, State (конечный автомат), Chain of Responsibility (middleware), Iterator | Mediator, Memento, Template Method, Visitor, Interpreter |

- [ ] **J** Strategy, Observer, Decorator / middleware, Factory — узнавать в своём коде и в библиотеках (EventEmitter, Express, HOC).
- [ ] **M** Остальные паттерны колонки «нужно точно» + различия похожих пар: Adapter / Facade, Decorator / Proxy, Strategy / State.
- [ ] **S** Колонка *(кругозор)* — знать идею и пример применения.

### 5. Паттерны и идиомы JS / TS

- [ ] **J** Замыкания, модули, debounce / throttle, `Promise.all` / `allSettled` / `race` / `any`, отмена через `AbortController` → [паттерны JS/TS](../c.patterns/patterns.js-ts.md).
- [ ] **M** Ограничение конкурентности, мемоизация с лимитом, каррирование и композиция функций.
- [ ] **M** Паттерны типизации — discriminated unions, branded types, type guards, `satisfies`, схема как источник типа (Zod).

### 6. Тестирование

- [ ] **J** Пирамида / трофей, AAA, тестовые дублёры (stub, mock, fake), тестируемость через DI → [стратегия тестирования](../c.patterns/patterns.testing.md).
- [ ] **M** TDD для доменной логики, интеграционные тесты с настоящей БД, MSW → [node.testing](../6.node.js/node.testing.md), [react.testing](../4.react/react.testing.md).
- [ ] **S** Мутационное и property-based тестирование, contract testing *(кругозор)*.

### 7. Проектирование и документирование

- [ ] **M** [Архитектура vs проектирование](../c.patterns/patterns.0-architecture-vs-design.md) — нефункциональные требования, компромиссы.
- [ ] **M** [UML](../c.patterns/patterns.uml.md) — диаграмма классов (связи, кратность) и последовательности; Mermaid.
- [ ] **M** C4 (Context + Container) и ADR — нарисовать систему и записать решение.
- [ ] **S** Контроль архитектуры — линтер границ (dependency-cruiser, eslint-plugin-boundaries), fitness functions.

### 8. Frontend-паттерны и архитектура

- [ ] **J** Композиция, `children`, слоты, кастомные хуки, хук + презентационный компонент → [React-паттерны](../c.patterns/patterns.react.md).
- [ ] **M** Compound Components, headless-компоненты, controlled / uncontrolled, Provider, Error Boundary; HOC и Render Props — читать в библиотеках.
- [ ] **M** Состояние по типам — серверное (TanStack Query), глобальное клиентское (Zustand), URL, формы, конечные автоматы → подробно в [React](roadmap.react.md).
- [ ] **M** Структура проекта — группировка по фичам, API-слой, монорепо с общими схемами → [frontend-архитектура](../c.patterns/patterns.frontend-architecture.md).
- [ ] **S** Feature-Sliced Design с линтером границ.
- [ ] **M** MVC, MVP, MVVM, MVI, Flux — чем отличаются *(кругозор)*.
- [ ] **S** Микрофронтенды, Atomic Design *(кругозор)*.

### 9. Backend-паттерны и архитектура

- [ ] **J** Controller → service → repository, тонкий контроллер, middleware, централизованная обработка ошибок, валидация на границе, конфиг из env → [backend-паттерны](../c.patterns/patterns.backend.md).
- [ ] **M** [Dependency Injection](../c.patterns/patterns.dependency-injection.md) — composition root, ручная сборка, DI в NestJS; Service Locator как антипаттерн.
- [ ] **J** [Проектирование API](../c.patterns/patterns.api-design.md) — REST, коды ответов, ошибки (Problem Details), пагинация, версионирование, идемпотентность.
- [ ] **M** [Доступ к данным](../c.patterns/patterns.data-access.md) — Repository, Unit of Work, N+1, оптимистичная блокировка, cache-aside.
- [ ] **M** Graceful shutdown, `AsyncLocalStorage`, фоновые задачи в очереди.
- [ ] **M** [Clean Architecture / Hexagonal](../c.patterns/patterns.clean-architecture.md) — Dependency Rule, порты и адаптеры, прагматичная лестница, vertical slices.
- [ ] **M** [Модульный монолит](../c.patterns/patterns.architecture-styles.md) как дефолт; синхронное vs асинхронное взаимодействие.
- [ ] **M** Идемпотентность, retry с backoff и jitter, timeout, Transactional Outbox → [распределённые паттерны](../c.patterns/patterns.distributed.md).
- [ ] **S** [DDD](../c.patterns/patterns.ddd.md) стратегический — bounded context, ubiquitous language, context map, anti-corruption layer.
- [ ] **S** Микросервисы — когда переходить, distributed monolith; Saga, CQRS, circuit breaker, Strangler Fig.
- [ ] **S** Тактический DDD (агрегаты, value objects, доменные события), Event Sourcing, CAP / PACELC *(кругозор)*.

### 10. AI-паттерны

- [ ] **J** Код, удобный для AI-агентов — локальные изменения, явные границы, строгие типы, быстрые тесты, `CLAUDE.md` / `AGENTS.md`, ADR → [AI-friendly код](../c.patterns/patterns.ai-friendly-code.md).
- [ ] **M** LLM как внешняя зависимость — порт + адаптер, timeout, retry, fallback, streaming → [паттерны LLM](../c.patterns/patterns.ai-llm.md).
- [ ] **M** Structured Output по Zod-схеме.
- [ ] **M** RAG — chunking, embeddings, pgvector, гибридный поиск, reranker, query rewriting, фильтр по правам.
- [ ] **M** Guardrails и prompt injection — проверки на входе, данных, инструментах и выходе; минимальные права.
- [ ] **M** Стоимость — prompt caching, роутинг моделей, кэш ответов; LLM gateway.
- [ ] **M** Evals — детерминированные проверки, LLM-as-judge, запуск в CI; промпт как код.
- [ ] **M** Агентные workflow — prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer → [AI-агенты](../c.patterns/patterns.ai-agents.md).
- [ ] **M** Агенты — ReAct, tool use, дизайн инструментов, bounded execution, human-in-the-loop, MCP-сервер.
- [ ] **S** Context engineering — write / select / compress / isolate, субагенты, память агента; durable execution.
- [ ] **S** Multi-agent, A2A, semantic cache, contextual retrieval *(кругозор)*.

### 11. Собеседование

- [ ] **J** [Чистый код и ревью](../c.patterns/patterns.clean-code-interview.md) — имена, функции, комментарии, DRY / KISS / YAGNI, code smells, ревью; инструменты — [линтеры и хуки](../b.tools/tools.code-quality-interview.md).
- [ ] **J** [Принципы](../c.patterns/patterns.principles-interview.md) — SOLID, GRASP, DRY / KISS / YAGNI, DI, рефакторинг, антипаттерны.
- [ ] **M** [GoF и JS/TS](../c.patterns/patterns.gof-interview.md) — паттерны, различия, live coding: EventEmitter, middleware, debounce, `mapLimit`.
- [ ] **M** [Frontend](../c.patterns/patterns.frontend-interview.md) — React-паттерны, состояние, FSD, MV\*.
- [ ] **M** [Архитектура](../c.patterns/patterns.architecture-interview.md) — Clean, DDD, стили, распределённые паттерны, backend, доступ к данным.
- [ ] **M** [AI](../c.patterns/patterns.ai-interview.md) — RAG, guardrails, evals, агенты, MCP.

### Чекпоинты

- [ ] **Принципы + GoF:** найти в своём проекте 5 паттернов (Strategy, Observer, Decorator, Factory, Adapter) и 3 нарушения SOLID; исправить одно рефакторингом с тестами.
- [ ] **Backend:** API на Node — модули по фичам, тонкие контроллеры, Zod на границе, Repository + Unit of Work, единый error handler, DI в `main.ts`, юнит-тесты use case на фейках.
- [ ] **Frontend:** приложение по фичам (или FSD) — Compound Component, кастомные хуки, TanStack Query, общий пакет схем с бэкендом.
- [ ] **Надёжность:** внешний API (платёжка или LLM) за адаптером — timeout, retry с jitter, идемпотентность, outbox для событий.
- [ ] **AI:** чат по документам — RAG на pgvector с гибридным поиском, structured output, guardrails, eval-набор в CI; плюс агент с 2–3 инструментами и лимитом шагов, MCP-сервер к своему API.

## Подводные камни

- Учить паттерны по списку без задач — забываются; лучше находить их в коде фреймворков (Observer в EventEmitter, Decorator в NestJS, Chain of Responsibility в Express, Adapter в Vercel AI SDK).
- Singleton как глобальная переменная — усложняет тестирование и даёт утечки данных в SSR.
- Clean Architecture и микросервисы в CRUD-приложении на три таблицы — overengineering ([YAGNI](../c.patterns/patterns.yagni.md)).
- Ложное DRY — объединять код, который совпадает случайно.
- Агент там, где хватает одного вызова LLM или обычного кода; AI-фича без evals.
- Принимать AI-код без чтения — агент копирует плохие паттерны проекта в новые места.

## Ссылки

- Предыдущий: [Backend](roadmap.backend.md) · Следующий: [DevOps](roadmap.devops.md) · Параллельно: [AI-разработка](roadmap.ai.md)
- Файлы базы: [раздел C. Паттерны](../INDEX.md#c-паттерны-архитектура--cpatterns)
- IT Booster: [роадмапы](https://itbooster.ru/roadmap) · roadmap.sh: [Software Design and Architecture](https://roadmap.sh/software-design-architecture)
- [refactoring.guru — паттерны](https://refactoring.guru/ru/design-patterns), [patterns.dev](https://www.patterns.dev/), [microservices.io](https://microservices.io/patterns/)
- Anthropic — [Building effective agents](https://www.anthropic.com/research/building-effective-agents); Martin Fowler — [Emerging Patterns in Building GenAI Products](https://martinfowler.com/articles/gen-ai-patterns/)
