# Роадмап: Fullstack JS + AI (старт)

> Теги: roadmap, роадмап, дорожная карта, план изучения, fullstack, full stack developer, фулстек, frontend, backend, devops, junior, middle, senior, чекпоинты, с чего начать, что учить и в каком порядке, путь разработчика, что должен знать fullstack разработчик, как стать фулстек разработчиком
> Основа: roadmap.sh (Full Stack, Frontend, Backend, DevOps), itbooster.ru — Ulbi TV (FullStack, Frontend и Backend с 0 до PRO) + дополнения. Проверено 2026-10-24.

## Определение

Fullstack-разработчик — специалист, который делает продукт целиком, «от пикселя до сервера»: интерфейс (frontend), серверную логику и API (backend), базу данных, развёртывание и эксплуатацию (DevOps). Он понимает систему целиком — от UI до БД, деплоя и безопасности. Этот файл — стартовая точка: порядок изучения и ссылки на роадмапы по каждой технологии.

## Зачем / когда использовать

- Увидеть маршрут целиком и не утонуть в деталях: детальные роадмапы длинные, здесь — порядок и «чего достаточно на каждом этапе».
- Стек базы: **JavaScript / TypeScript везде** — React + Next.js на фронте, Node.js на бэке, PostgreSQL, Docker, AWS. Альтернативы (Vue, Angular, Python, Go, C# …) упоминаются, но не разбираются.
- Как читать: идти по этапам сверху вниз. Каждый этап заканчивается **чекпоинтом** — проектом, который закрепляет материал. Без проектов знания не держатся.

### Обозначения (во всех роадмапах)

| Метка | Значение |
|---|---|
| `- [ ]` | тема — отмечать `[x]` по мере освоения |
| **J** / **M** / **S** | к какому уровню тема нужна: Junior / Middle / Senior |
| *(опц.)* | опционально — знать, что это и когда применять, глубоко учить по необходимости |
| *(позже)* | можно вернуться после остальных тем роадмапа |

## Основное

### Маршрут — цепочка роадмапов

```text
Основы WEB → HTML → CSS → JavaScript → Git → TypeScript → React → Frontend PRO → Next.js
  → Node.js → Базы данных → Backend → Паттерны и архитектура
  → DevOps → Docker → AWS → Terraform
AI-разработка — параллельно: с первого дня как ментор, в полную силу — после JS и TS
```

| № | Роадмап | Что даёт |
|---|---|---|
| 1 | [Основы WEB](roadmap.web-basics.md) | как работает интернет, HTTP, браузер, клиент-сервер, рабочее окружение |
| 2 | [HTML](roadmap.html.md) | разметка, формы, семантика, доступность, SEO |
| 3 | [CSS](roadmap.css.md) | стили, Flexbox, Grid, адаптивность, анимации |
| 4 | [JavaScript](roadmap.javascript.md) | язык, DOM, асинхронность, event loop, ООП |
| 5 | [Git и GitHub](roadmap.git.md) | контроль версий, ветки, PR, code review, хуки |
| 6 | [TypeScript](roadmap.typescript.md) | статическая типизация, generics, utility types |
| 7 | [React](roadmap.react.md) | компоненты, хуки, состояние, роутинг, паттерны |
| 8 | [Frontend PRO](roadmap.frontend.md) | инструменты, тестирование, производительность, безопасность, деплой фронта |
| 9 | [Next.js](roadmap.nextjs.md) | SSR/SSG, App Router, Server Components — fullstack на React |
| 10 | [Node.js](roadmap.nodejs.md) | серверный JS, модули, fs, HTTP, Express/NestJS |
| 11 | [Базы данных и SQL](roadmap.databases.md) | SQL, PostgreSQL, индексы, транзакции, NoSQL, ORM |
| 12 | [Backend](roadmap.backend.md) | API, auth, кэш, очереди, безопасность, масштабирование |
| 13 | [Паттерны и архитектура](roadmap.patterns.md) | ООП, SOLID, GoF, архитектура frontend и backend |
| 14 | [DevOps](roadmap.devops.md) | Linux, сети, web-серверы, CI/CD, мониторинг, Kubernetes |
| 15 | [Docker](roadmap.docker.md) | контейнеры, Dockerfile, Compose, registry |
| 16 | [AWS](roadmap.aws.md) | облако: IAM, VPC, EC2, S3, RDS, Lambda |
| 17 | [Terraform](roadmap.terraform.md) | инфраструктура как код (IaC) |
| — | [AI-разработка](roadmap.ai.md) | AI-ассистенты, LLM, prompt и context engineering, RAG, агенты, MCP |

### Этап 1. Frontend — основы (→ Junior frontend)

- [ ] **J** [Основы WEB](roadmap.web-basics.md) — сначала понять, что происходит между браузером и сервером.
- [ ] **J** [HTML](roadmap.html.md) → [CSS](roadmap.css.md).
- [ ] **Чекпоинт — статические страницы:** лендинг, резюме, вёрстка макета из Figma, адаптив.
- [ ] **J** [JavaScript](roadmap.javascript.md) — темы уровня Beginner и Intermediate.
- [ ] **Чекпоинт — интерактивность:** todo-лист, калькулятор, галерея, получение данных из публичного API через `fetch`.
- [ ] **J** [Git и GitHub](roadmap.git.md) — с этого момента каждый проект в своём репозитории.
- [ ] **J** npm / pnpm — [npm](../b.tools/tools.npm.md), [pnpm](../b.tools/tools.pnpm.md).
- [ ] **Чекпоинт — внешние пакеты:** подключить библиотеку (например, для дат или графиков), собрать проект через Vite.

### Этап 2. Frontend — приложения (→ Middle frontend)

- [ ] **J** [TypeScript](roadmap.typescript.md) — параллельно с React или сразу после его базы.
- [ ] **J** [React](roadmap.react.md) — для первого фреймворка выбирать между React и Vue; в этой базе — React.
- [ ] **J** Tailwind CSS — стандарт стилизации в новых проектах (см. [CSS](roadmap.css.md)).
- [ ] **Чекпоинт — командная работа:** проект через ветки и Pull Request, code review друга, CI с линтером.
- [ ] **M** [Frontend PRO](roadmap.frontend.md) — state management, тестирование, производительность, безопасность.
- [ ] **M** [Next.js](roadmap.nextjs.md) — можно отложить до изучения backend.
- [ ] **Чекпоинт — frontend-приложение:** SPA с роутингом, формами, работой с API, тестами, задеплоенное на Vercel / Netlify.

### Этап 3. Backend (→ Junior/Middle fullstack)

- [ ] **J** [Node.js](roadmap.nodejs.md) — язык уже знаком, поэтому рекомендуемый первый backend.
- [ ] **Чекпоинт — CLI-приложения:** утилита для работы с файлами, парсер, генератор отчётов.
- [ ] **J** REST API — Express, затем NestJS (см. [Backend](roadmap.backend.md)).
- [ ] **J** [Базы данных и SQL](roadmap.databases.md) — PostgreSQL, ORM (Prisma / Drizzle).
- [ ] **Чекпоинт — простое CRUD-приложение:** REST API + PostgreSQL + валидация (Zod).
- [ ] **J** Аутентификация — JWT, cookie-сессии, OAuth (см. [Backend](roadmap.backend.md)).
- [ ] **M** Кэширование — Redis.
- [ ] **J** Основы Linux (см. [DevOps](roadmap.devops.md)).
- [ ] **Чекпоинт — законченное приложение:** frontend + backend + БД + авторизация + кэш, например блог, трекер задач, мини-магазин.
- [ ] **M** [Паттерны и архитектура](roadmap.patterns.md) — SOLID, слои, DI, архитектура frontend.

### Этап 4. DevOps и облако (→ самостоятельный fullstack)

- [ ] **J** [DevOps](roadmap.devops.md): сети, Nginx, SSH.
- [ ] **J** [Docker](roadmap.docker.md) — упаковать своё приложение и БД в Docker Compose.
- [ ] **M** [AWS](roadmap.aws.md) — EC2, VPC, Route 53, SES, S3, затем RDS.
- [ ] **Чекпоинт — деплой:** приложение на сервере / в облаке, домен, HTTPS.
- [ ] **M** Мониторинг — для старта хватит Monit или Uptime Kuma, далее Prometheus + Grafana.
- [ ] **Чекпоинт — мониторинг:** алерты о падении сервиса и нагрузке.
- [ ] **M** CI/CD — GitHub Actions ([GitHub-проверки](../b.tools/tools.github-checks.md)).
- [ ] **Чекпоинт — CI/CD:** push в `main` → тесты → сборка Docker-образа → деплой.
- [ ] **S** Ansible — автоматизация настройки серверов *(опц.)*.
- [ ] **Чекпоинт — автоматизация:** скрипт бэкапа БД, настройка сервера одним плейбуком.
- [ ] **S** [Terraform](roadmap.terraform.md) — пересоздать всю инфраструктуру из кода.
- [ ] **Чекпоинт — инфраструктура:** удалить созданное руками в AWS и поднять то же самое через Terraform.

### Сквозные темы — на всём пути

- [ ] **J** Алгоритмы и структуры данных — основа сразу, углубляться позже ([все темы](../e.algorithms/algorithms.0-topics.md): Big O, структуры, сортировки, приёмы, деревья и графы; [вопросы](../e.algorithms/algorithms.basics-interview.md)).
- [ ] **J** Чистый код — [Clean Code](../c.patterns/patterns.clean-code.md), [DRY](../c.patterns/patterns.dry.md), [KISS](../c.patterns/patterns.kiss.md), [YAGNI](../c.patterns/patterns.yagni.md).
- [ ] **J** Качество кода — [настройка репозитория](../b.tools/tools.0-project-setup.md): ESLint, Prettier, Husky.
- [ ] **J→S** Тестирование — на каждом слое: unit → integration → e2e → нагрузочное.
- [ ] **J→S** Безопасность — OWASP Top 10, секреты не в коде, зависимости под контролем.
- [ ] **J** [AI-разработка](roadmap.ai.md) — AI как ментор и ревьюер, а не как автор кода на этапе обучения.
- [ ] **J** Технический английский — документация, ошибки, вопросы на GitHub и Stack Overflow.

### Минимум fullstack-разработчика (итоговый чек-лист)

Основы WEB и клиент-серверное взаимодействие · HTTP и REST API · HTML, CSS, JavaScript, TypeScript · Git · frontend-фреймворк (React) · SQL и NoSQL · ORM · аутентификация и авторизация · кэширование · тестирование · нагрузочное тестирование (на базовом уровне — прикинуть, какой RPS держит сервис) · безопасность · Linux · архитектура ПО · логирование и метрики · масштабирование · CI/CD · развёртывание сервисов · основы DevOps и облака · работа с AI-инструментами.

### Ориентиры по уровням

| Уровень | Что умеет |
|---|---|
| **Junior** | вёрстка, JS/TS, React, простой REST API на Node.js + PostgreSQL, Git-флоу с PR; задачи — с помощью старших |
| **Middle** | самостоятельно делает фичу от БД до UI: state management, тесты, auth, кэш, Docker, CI; понимает производительность и безопасность |
| **Senior** | проектирует систему: архитектура, масштабирование, наблюдаемость, облако и IaC, отказоустойчивость, SLA/SLO; менторит и ревьюит |

### Что добавлено к исходным роадмапам (актуально в 2026)

- **AI-assisted разработка** — обязательный навык: Claude Code, Cursor, Copilot, MCP, контекст-файлы (`CLAUDE.md`, `AGENTS.md`). Код от AI нужно понимать и проверять → [AI-разработка](roadmap.ai.md).
- **TypeScript по умолчанию** — и на фронте, и на бэке; валидация данных на границах — Zod.
- **Vite** — стандарт сборки SPA; **Next.js** — стандарт fullstack-React (Server Components, Server Actions).
- **Наблюдаемость (observability)** — логи, метрики, трейсы, OpenTelemetry.
- **Безопасность цепочки поставок (supply chain)** — lock-файлы, `npm ci`, Dependabot, проверка скриптов установки ([npm](../b.tools/tools.npm.md)).
- **Core Web Vitals** (LCP, INP, CLS) — метрики производительности фронта, влияют на SEO.

## Подводные камни

- **Учить всё сразу.** Детальные роадмапы roadmap.sh огромны — на старте брать только рекомендуемые темы, альтернативы оставить на потом.
- **Прыгать между фреймворками и языками.** Один стек до уровня «могу сделать проект сам», потом расширяться.
- **Tutorial hell** — бесконечные курсы без своих проектов. После каждого блока — чекпоинт-проект.
- **React до JavaScript.** Слабая база JS (замыкания, `this`, асинхронность, event loop) потом тормозит всё остальное.
- **AI пишет код за тебя на этапе обучения** — опасно: навык не формируется. AI — ментор, советчик, ревьюер.
- **Только frontend или только backend.** Senior frontend без базовых знаний Node.js и backend не считается полноценным — и наоборот.

## Ссылки

- Следующий роадмап: [Основы WEB](roadmap.web-basics.md)
- roadmap.sh: [Full Stack](https://roadmap.sh/full-stack), [Frontend](https://roadmap.sh/frontend), [Backend](https://roadmap.sh/backend), [DevOps](https://roadmap.sh/devops)
- IT Booster (Ulbi TV): [роадмапы](https://itbooster.ru/roadmap) — FullStack, Frontend с 0 до PRO, Backend с 0 до PRO
- Подготовка к собеседованию: [interview.0-preparation](../f.interview/interview.0-preparation.md)
